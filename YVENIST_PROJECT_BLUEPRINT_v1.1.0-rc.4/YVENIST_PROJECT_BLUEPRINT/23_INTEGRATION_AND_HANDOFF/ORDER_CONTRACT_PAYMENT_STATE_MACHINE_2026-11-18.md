# CICLO DE PEDIDO, CONTRATAÇÃO, PAGAMENTO E REPASSE — MODELO DE DOMÍNIO v0.1

**Data:** 2026-11-18  
**Status:** ESPECIFICAÇÃO TÉCNICA PROPOSTA / AGUARDANDO APROVAÇÃO COMERCIAL E ESPECIALIZADA  
**Decisões de origem:** PM-20 a PM-26, PAY-01, FLOW-01 e FLOW-02  
**Documento comercial:** `MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md`

## 1. Objetivo

Definir um domínio que permita ao Claude Code implementar o ciclo completo sem confundir:
- planejamento de evento;
- aceitação de disponibilidade pelo fornecedor;
- contratação;
- pagamento;
- comissão;
- repasse;
- execução;
- cancelamento;
- reembolso;
- disputa.

O estado de um pedido não pode ser representado por um único campo `status`. Um evento pode ter fornecedores em estados diferentes; um pagamento pode estar aprovado enquanto um subpedido continua em execução; um reembolso pode existir depois da conclusão. Cada dimensão precisa de seu próprio registro e transições.

## 2. Agregados e entidades

### 2.1. Party Maker

**`EventRequest`** — agregado de planejamento/solicitação de um evento. Contém consumidor, tipo de evento, data, convidados, endereço/área, observações, linhas selecionadas e estado consolidado.

**`SupplierSubOrder`** — parte da solicitação associada a exatamente um fornecedor. Contém as linhas pertencentes a esse fornecedor, configurações, snapshot de preço, data/horário e estado de resposta/execução. Um EventRequest pode ter N SupplierSubOrders.

### 2.2. Compra imediata

**`CheckoutOrder`** — agrupa a intenção de compra de itens que não exigem Party Maker.

**`SupplierSubOrder`** — entidade reutilizável para separar as linhas por fornecedor. O tipo de origem será `EVENT_REQUEST` ou `IMMEDIATE_CHECKOUT`.

### 2.3. Financeiro e contratação

- **`PaymentGroup`:** experiência de checkout de um consumidor. Agrupa os pagamentos relacionados ao conjunto de subpedidos que ele decidiu contratar.
- **`PaymentIntent`:** tentativa de pagamento vinculada a um recebedor/subpedido ou a um split nativo do PSP.
- **`PaymentTransaction`:** evento financeiro do PSP, com identificador externo, valor, taxa, método e estado.
- **`ContractRecord`:** snapshot versionado dos termos acordados para um subpedido e sua contratação.
- **`CommissionEntry`:** comissão calculada, pendente, adquirida ou revertida por subpedido.
- **`PayoutRecord`:** liquidação/repasse ao fornecedor, de acordo com o PSP.
- **`RefundRecord`:** reembolso total/parcial vinculado ao pagamento e às linhas afetadas.
- **`DisputeCase`:** ocorrência formal para reclamação, não prestação, desacordo, chargeback ou falha de qualidade.
- **`AvailabilityHold`:** reserva temporária de capacidade/data aceita pelo fornecedor enquanto o consumidor conclui o checkout.

## 3. Separação dos estados

Um registro de pedido deve expor dimensões separadas:

| Dimensão | Dono do estado |
|---|---|
| Planejamento e submissão do evento | EventRequest |
| Resposta e execução de cada fornecedor | SupplierSubOrder |
| Pagamento do consumidor | PaymentGroup / PaymentIntent |
| Obrigação contratual | ContractRecord |
| Comissão | CommissionEntry |
| Liquidação ao fornecedor | PayoutRecord |
| Reembolso | RefundRecord |
| Reclamação/disputa | DisputeCase |

O estado consolidado exibido ao consumidor é uma projeção calculada a partir dessas dimensões; não deve apagar os estados individuais.

## 4. Máquina de estados do EventRequest

Estados propostos:
- `DRAFT`: festa em edição.
- `SUBMITTED`: consumidor enviou a solicitação única.
- `AWAITING_SUPPLIERS`: existem subpedidos aguardando resposta.
- `PARTIALLY_RESPONDED`: ao menos um fornecedor respondeu, mas há pendências.
- `NEEDS_CUSTOMER_DECISION`: recusa ou alteração exige escolha do consumidor.
- `READY_FOR_CHECKOUT`: conjunto de subpedidos selecionado pelo consumidor está confirmado e apto ao checkout.
- `PARTIALLY_CONTRACTED`: parte dos subpedidos já foi paga/contratada e outra parte continua não contratada.
- `CONTRACTED`: todos os subpedidos requeridos para a composição final estão contratados.
- `IN_PROGRESS`: ao menos uma prestação começou e o evento ainda não foi concluído.
- `COMPLETED`: todas as partes contratadas foram concluídas ou resolvidas.
- `CANCELLED`: solicitação encerrada sem contratação ativa.
- `PARTIALLY_CANCELLED`: parte dos subpedidos cancelada, com outras partes preservadas.

Regras:
1. Submeter o EventRequest não cria contrato nem captura pagamento.
2. Um fornecedor nunca pode responder por outro subpedido.
3. Não transformar silêncio em confirmação.
4. Alteração material do total/composição exige apresentação clara ao consumidor.
5. O evento só passa a `CONTRACTED` quando todos os subpedidos exigidos pela composição final tiverem os requisitos de contratação cumpridos.
6. `PARTIALLY_CONTRACTED` permite que partes independentes já contratadas continuem sem esconder dependências não resolvidas.

## 5. Máquina de estados do SupplierSubOrder

Estados propostos:
- `DRAFT`
- `SUBMITTED`
- `AWAITING_SUPPLIER`
- `AVAILABILITY_CONFIRMED`
- `DECLINED`
- `CHANGE_REQUESTED`
- `CUSTOMER_CHANGE_PENDING`
- `EXPIRED`
- `AWAITING_PAYMENT`
- `CONTRACTED`
- `SCHEDULED`
- `IN_FULFILMENT`
- `FULFILLED`
- `CANCEL_REQUESTED`
- `CANCELLED`
- `REFUND_PENDING`
- `REFUNDED`
- `DISPUTED`
- `CLOSED`

### 5.1. Ações do fornecedor

- `CONFIRM_AS_REQUESTED`: confirma data, escopo e snapshot de preço atual. Criar AvailabilityHold com validade definida pela política da categoria.
- `DECLINE`: recusa com motivo obrigatório de uma lista controlada e observação opcional.
- `REQUEST_CHANGE`: propõe nova data, preço, quantidade, item ou escopo. Não alterar o preço do pedido original.

### 5.2. Regra de contratação

A confirmação do fornecedor significa que ele aceita a solicitação conforme apresentada e consegue atender à data/condições; ela não equivale, por si só, a pagamento concluído. A recomendação é criar uma reserva temporária enquanto o consumidor revisa o resumo e conclui o pagamento/aceite dos termos. Depois do pagamento confirmado pelo PSP e do registro contratual, converter o hold em contratação confirmada. Se a janela expirar sem pagamento, liberar a capacidade e informar as partes.

Se os responsáveis entenderem que a confirmação do fornecedor deve produzir imediatamente uma obrigação contratual vinculante mesmo sem pagamento, essa decisão exige parecer jurídico e alteração desta transição.

### 5.3. Alteração solicitada

1. Preservar o snapshot original.
2. Registrar uma proposta versionada com diferença de preço/data/escopo.
3. Consumidor escolhe aceitar ou rejeitar a proposta.
4. Ao aceitar, recalcular total e exigir nova confirmação do fornecedor se a alteração afetar disponibilidade.
5. Somente depois da concordância de ambas as partes atualizar o subpedido ativo.
6. Antes da contratação, a escolha pode substituir o snapshot preliminar; depois da contratação, gerar aditivo e registrar os aceites necessários.

## 6. Máquina de estados de compra imediata

`CheckoutOrder`:
- `CART`
- `VALIDATING`
- `AWAITING_PAYMENT`
- `PAYMENT_PROCESSING`
- `PAID`
- `READY_FOR_FULFILMENT`
- `IN_FULFILMENT`
- `FULFILLED`
- `CANCEL_REQUESTED`
- `CANCELLED`
- `PARTIALLY_REFUNDED`
- `REFUNDED`
- `DISPUTED`
- `CLOSED`

A confirmação V1 do Figma representa `PAID` após confirmação server-side do PSP; não usar V1 para informar que um orçamento foi apenas solicitado.

## 7. Máquina de estados do pagamento

Estados de PaymentIntent:
- `CREATED`
- `PENDING`
- `PROCESSING`
- `APPROVED`
- `AUTHORIZED` (somente se o meio/provedor suportar autorização separada de captura)
- `CAPTURED`
- `FAILED`
- `CANCELLED`
- `PARTIALLY_REFUNDED`
- `REFUNDED`
- `CHARGEBACK_OPEN`
- `CHARGEBACK_WON`
- `CHARGEBACK_LOST`

Regras técnicas:
- Webhook/consulta do PSP, não o retorno do app, é a autoridade do estado financeiro.
- Processar webhooks com idempotência e persistir o ID externo do evento.
- Eventos fora de ordem devem ser reconciliados com consulta ao PSP e regras de transição monotônicas.
- Um timeout de rede não significa pagamento recusado; manter `PENDING` e reconciliar antes de permitir novo pagamento.
- Não duplicar cobrança por retry; usar idempotency key por intento.
- Guardar histórico append-only de eventos financeiros.

## 8. PaymentGroup e multi-fornecedor

Um PaymentGroup representa uma única experiência de checkout do consumidor, mas pode ter uma ou várias PaymentIntents.

Possibilidades:
1. um split PSP nativo para vários recebedores, se o contrato e o produto do PSP suportarem o número de vendedores;
2. uma PaymentIntent por SupplierSubOrder, correlacionadas ao mesmo PaymentGroup, caso não exista split multi-recebedor disponível.

Não presumir que split 1:1 cobre uma festa com vários fornecedores. A documentação do Mercado Pago informa que o produto 1:N tem acesso condicionado a carteira assessorada/contato comercial. O PSP precisa confirmar formalmente número máximo de recebedores, taxa, reembolso parcial, chargeback, saldo insuficiente do vendedor, calendário de liquidação e disponibilidade no Brasil.

O consumidor vê o resumo global e a situação de cada fornecedor; a camada financeira mantém transações individualizadas.

## 9. Pagamento integral ou sinal e saldo

O modelo deve comportar:
- `FULL_PREPAYMENT`: total do subpedido pago de uma vez.
- `DEPOSIT_PLUS_BALANCE`: sinal pago na contratação, saldo com vencimento definido.

Compra imediata usa pagamento integral como regra proposta. Para evento futuro, permitir a alternativa de sinal e saldo apenas quando fornecedor/categoria, PSP, contrato e política aprovada permitirem. O sistema deve salvar percentuais/valores, datas, meios de pagamento, tentativas e status de cada parcela. Não definir percentual padrão até aprovação comercial.

## 10. ContractRecord

Criar ContractRecord ao concluir os requisitos de contratação do subpedido. Deve conter:
- consumer_id, supplier_id, event_id/order_id, supplier_sub_order_id;
- snapshot de item/pacote, quantidade e preço;
- endereço, data, horário e detalhes do serviço;
- termos e versão legal aceitos;
- forma e calendário de pagamento;
- política de cancelamento/reembolso aplicada;
- versão do preço e data do aceite do fornecedor;
- pagamento/PSP reference;
- timestamp, usuário, canal e evidência do aceite.

O conteúdo contratual é imutável. Alteração gera aditivo/versão nova com vínculo ao documento anterior. O consumidor e fornecedor devem poder consultar o contrato/confirmacão no histórico.

## 11. Comissão e PayoutRecord

CommissionEntry:
- `CALCULATED`
- `PENDING_COMPLETION`
- `EARNED`
- `REVERSED`
- `DISPUTED`

PayoutRecord:
- `NOT_SCHEDULED`
- `SCHEDULED`
- `PROCESSING`
- `PAID`
- `FAILED`
- `HELD_BY_PSP`
- `REVERSED`

O PSP é responsável pela liquidação segundo seu contrato e regras. O Yvenist deve conciliar registros, não representar um saldo virtual como dinheiro disponível se não houver base legal/provedor para isso.

## 12. RefundRecord e DisputeCase

Reembolso:
- `REQUESTED`
- `UNDER_REVIEW`
- `APPROVED`
- `SUBMITTED_TO_PSP`
- `PROCESSING`
- `SUCCEEDED`
- `FAILED`
- `REJECTED_WITH_REASON`

Disputa:
- `OPEN`
- `WAITING_CONSUMER_EVIDENCE`
- `WAITING_SUPPLIER_EVIDENCE`
- `UNDER_REVIEW`
- `DECIDED`
- `APPEAL_REQUESTED`
- `CLOSED`

Cada refund deve apontar para PaymentIntent, subpedido e linhas afetadas. Cada disputa mantém razão, timeline, comunicação, anexos com política de retenção, responsável, decisão, fundamento e possibilidade de revisão. Um problema em um fornecedor não deve bloquear reembolso de outro subpedido sem relação com o incidente.

## 13. Eventos de domínio mínimos

- `EventRequestSubmitted`
- `SupplierSubOrderCreated`
- `SupplierNotified`
- `SupplierAvailabilityConfirmed`
- `SupplierDeclined`
- `SupplierChangeRequested`
- `CustomerChangeAccepted`
- `CustomerChangeRejected`
- `AvailabilityHoldCreated`
- `AvailabilityHoldExpired`
- `PaymentGroupCreated`
- `PaymentIntentCreated`
- `PaymentApproved`
- `PaymentFailed`
- `ContractGenerated`
- `ContractAccepted`
- `FulfilmentStarted`
- `FulfilmentCompleted`
- `CancellationRequested`
- `CancellationApproved`
- `RefundSubmitted`
- `RefundSucceeded`
- `DisputeOpened`
- `CommissionEarned`
- `PayoutScheduled`
- `PayoutSucceeded`

Cada evento precisa de ID, agregado, versão, timestamp UTC, ator, correlation ID, idempotency key quando aplicável e origem. Não registrar dados sensíveis desnecessários no payload do evento.

## 14. Invariantes de negócio

1. Não existe pagamento capturado sem pedido/subpedido e snapshot de preço identificáveis.
2. Não existe contrato final sem fornecedor identificado, escopo, preço, data/condições e versão dos termos.
3. Não existe confirmação do consumidor sobre orçamento como etapa padrão; há revisão/aceite dos termos de contratação durante o checkout.
4. Nenhum fornecedor pode confirmar, editar ou cancelar o subpedido de outro.
5. Nunca alterar retroativamente o snapshot aceito.
6. Nenhum subpedido recusado ou expirado entra no total a cobrar.
7. Alteração material de preço/data/escopo exige consentimento de quem é afetado.
8. Uma operação de reembolso não apaga o pagamento original; cria evento/registro correlacionado.
9. Eventos financeiros e logs de aceite devem ser auditáveis.
10. Comissão adquirida é calculada apenas conforme base e regra comercial aprovadas.
11. Pedido parcialmente atendido não deve ser rotulado como integralmente concluído.
12. O cliente sempre vê valores, fornecedor, status e próximos passos antes de pagar.

## 15. Critérios de aceite para Claude Code

Claude não deve começar a construir checkout final apenas com base nas telas. Deve entregar e testar:

- diagrama de estados por agregado;
- contratos de API e payloads de evento;
- modelo de dados/migrations;
- matriz de permissões consumidor/fornecedor/admin;
- idempotência e reconciliação do PSP;
- casos de pagamento aprovado/pendente/recusado e webhook duplicado;
- confirmação/recusa/alteração/expiração de subpedido;
- aceitação parcial e dependência entre categorias;
- cancelamento total e parcial;
- reembolso total e parcial;
- comissões calculadas, adquiridas e revertidas;
- payout atrasado/falhado/retido pelo PSP;
- disputa e chargeback;
- testes automatizados e trilha de auditoria;
- fluxo completo no sandbox antes de habilitar produção.

Este documento é modelo proposto. A aprovação comercial e o parecer especializado devem anteceder a configuração de produção e qualquer cobrança real.

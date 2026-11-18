# FOLHA DE APROVAÇÃO — POLÍTICAS COMERCIAIS E DE CONTRATAÇÃO

**Data:** 2026-11-18  
**Status:** COM-01 E COM-02 APROVADAS CONJUNTAMENTE / DEMAIS ITENS PENDENTES  
**Aprovadores:** Keven e Rafael  
**Documentos-base:**  
- `MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md`
- `ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md`
- `COMMISSIONABLE_BASE_AND_DISCOUNT_POLICY_COM-02_2026-11-18.md`

Esta folha registra decisões comerciais já aprovadas conjuntamente e itens que ainda precisam de deliberação. Recomendações técnicas e de pesquisa não substituem a aprovação de Keven e Rafael. Cada item conserva seu próprio status.

## A. Comissão e receita

| ID | Decisão necessária | Recomendação para começar | Resposta dos responsáveis |
|---|---|---|---|
| COM-01 | Comissão progressiva e programa de lançamento | 3% para Parceiro Fundador nos primeiros 12 meses a partir da primeira contratação concluída; 5% após prazo + gate de expansão por categoria/área; 10% após gate de maturidade. Comissão paga pelo fornecedor por subpedido concluído; aviso de 60 dias e aceite expresso para nova taxa | APROVADO CONJUNTAMENTE — 2026-11-18 |
| COM-02 | Base comissionável e descontos | Remuneração do fornecedor pela parte concluída, antes da comissão Yvenist e da taxa PSP; descontos reduzem a base conforme a parcela economicamente suportada pelo fornecedor; subsídio da plataforma só preserva a base quando efetivamente compensa o fornecedor; repasses genuínos e documentados de terceiros ficam separados | APROVADO CONJUNTAMENTE — 2026-11-18 |
| COM-03 | Taxa do PSP | Deduzir do repasse do fornecedor, separada da comissão e claramente exibida, se a viabilidade econômica e o contrato permitirem | PENDENTE |
| COM-04 | Comissão em reembolso parcial | Recalcular e reverter proporcionalmente à parcela reembolsada/não concluída | PENDENTE |
| ADS-01 | Exposição patrocinada | Poucas posições por categoria/região, etiqueta Patrocinado, elegibilidade e relevância antes do pagamento | PENDENTE |
| SUB-01 | Assinatura do consumidor | Fora do lançamento; definir benefícios, preço e prioridade apenas após acordo com fornecedores | PENDENTE / FUTURO |

### COM-01 — regra aprovada

A política COM-01 v0.2 foi aprovada conjuntamente: 3% para Parceiros Fundadores nos primeiros 12 meses desde a primeira contratação concluída; 5% somente após o prazo mínimo e o gate de Expansão por categoria/área; 10% somente após gate de Maturidade e revisão conjunta. A cobrança é do fornecedor, por subpedido concluído. Aviso de 60 dias, lembretes em 30 e 7 dias, aceite expresso e não retroatividade são obrigatórios.

Documento normativo: `COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md`.

### COM-01 — registro das decisões conjuntas

Os sócios confirmaram:
- 20 fornecedores fundadores ativos e distintos;
- quatro famílias prioritárias, meta de cinco fornecedores por família: espaços/salões; buffet/alimentação; decoração/locação; confeitaria/doces/kits;
- região inicial Campo Grande / Zona Oeste, com Campo Grande como núcleo e cobertura progressiva conforme a área realmente atendida;
- 3% por 12 meses desde a primeira contratação concluída do fornecedor fundador;
- passagem para 5% apenas após prazo mínimo e gate de expansão por categoria/área;
- passagem para 10% apenas após gate de maturidade e revisão conjunta;
- comunicação prévia de 60 dias, lembretes em 30 e 7 dias, aceite expresso e nenhuma aplicação retroativa.

O detalhamento, métricas, critérios de amostra e regras de implementação estão em:
- `COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md`;
- `LOCAL_MARKET_LAUNCH_PLAN_CAMPO_GRANDE_ZONA_OESTE_2026-11-18.md`.

COM-02 também foi aprovada conjuntamente como regra comercial interna. Permanecem pendentes COM-03, COM-04 e outras regras de pagamento, cancelamento e contratação. As aprovações de COM-01 e COM-02 não liberam cobranças reais antes de parecer jurídico/contábil e homologação do PSP.

### COM-02 — regra aprovada

Keven e Rafael aprovaram conjuntamente a COM-02 v1.0. A base é calculada por fornecedor/subpedido e parte concluída, sobre a remuneração efetiva devida ao fornecedor antes da comissão Yvenist e dos custos PSP. Desconto financiado pelo fornecedor reduz a remuneração; parcela financiada pela plataforma só deixa de reduzir a base quando for efetivamente compensada ao fornecedor; promoções cofinanciadas são separadas por parcela. Entrega/montagem/deslocamento do próprio fornecedor integram sua remuneração quando contratados; repasses a terceiros só ficam fora com discriminação e comprovação. Tributos não são automaticamente excluídos. COM-03 (taxa PSP) e COM-04 (tratamento detalhado de reembolso parcial) permanecem pendentes.

Documento normativo: `COMMISSIONABLE_BASE_AND_DISCOUNT_POLICY_COM-02_2026-11-18.md`.

## B. Confirmação, contratação e pagamento

| ID | Decisão necessária | Recomendação para começar | Resposta dos responsáveis |
|---|---|---|---|
| PAY-02 | Momento de cobrança do Party Maker | Primeiro fornecedor confirma cada subpedido; consumidor revisa a composição confirmada; checkout então cobra apenas as partes escolhidas e confirmadas | PENDENTE |
| PAY-03 | Pagamento de evento futuro | Suportar pagamento integral ou sinal + saldo conforme categoria/fornecedor; não fixar percentual padrão antes do piloto | PENDENTE |
| PAY-04 | Janela de reserva temporária | Criar hold com validade por categoria após a confirmação do fornecedor; expirar automaticamente sem pagamento | PENDENTE |
| PAY-05 | Checkout de vários fornecedores | Uma única revisão/experiência de checkout; usar split 1:N se PSP contratado suportar, ou cobranças correlacionadas por subpedido | PENDENTE |
| OPS-01 | Prazo de resposta do fornecedor | SLA configurável por categoria, antecedência e urgência; nenhum silêncio equivale a aceite | PENDENTE |
| OPS-02 | Contrato | Gerar ContractRecord por fornecedor/subpedido; snapshot imutável; mudanças materiais por aditivo/novo aceite | PENDENTE |

## C. Cancelamentos e conclusão

| ID | Decisão necessária | Recomendação para começar | Resposta dos responsáveis |
|---|---|---|---|
| OPS-03 | Cancelamento antes da confirmação do fornecedor | Cancelamento sem cobrança; se houve captura indevida, iniciar reembolso integral | PENDENTE |
| OPS-04 | Cancelamento após confirmação, antes de contratar/pagar | Cancelar hold e encerrar o subpedido sem multa | PENDENTE |
| OPS-05 | Cancelamento pelo consumidor após contratar | Regras específicas por categoria e estágio, exibidas antes do pagamento e compatíveis com direitos legais; sem percentual universal | PENDENTE |
| OPS-06 | Cancelamento pelo fornecedor | Reembolso da parte não prestada, alternativa de substituição, registro de confiabilidade e consequência proporcional/revisável | PENDENTE |
| OPS-07 | Atraso/no-show do fornecedor | Evidências, alerta, opções ao consumidor, análise do subpedido e possível reembolso/medida operacional | PENDENTE |
| OPS-08 | Confirmação de conclusão | Evidência de entrega/prestação + confirmação do consumidor ou timeout operacional definido por categoria; disputa pausa a parte contestada quando o PSP permitir | PENDENTE |
| PAY-06 | Momento de repasse | Conforme settlement do PSP e regra aprovada; não prometer custódia/escrow próprio | PENDENTE |
| OPS-09 | No-show do consumidor | Regras por categoria, pré-disclosure e revisão jurídica; sem transferência automática integral ao fornecedor | PENDENTE |

## D. Critérios para aprovar

Para cada item, responder com:
- **APROVAR RECOMENDAÇÃO**
- **APROVAR COM ALTERAÇÃO:** escrever a regra completa.
- **PENDENTE:** registrar o que falta para decidir.

A aprovação só ocorre quando Keven e Rafael concordarem com a mesma versão. A aprovação desta folha não substitui parecer de advogado, contador ou PSP para os assuntos que dependem deles.

## E. Dependências externas obrigatórias antes de transações reais

1. Advogado brasileiro: CDC, contratação eletrônica, arrependimento, contratos de fornecedores, cancelamentos, responsabilidades e publicidade patrocinada.
2. Contador: emissão fiscal, tributos, comissão, descontos, repasse e conciliação.
3. PSP: split multi-recebedor, KYC, OAuth, taxa, reembolso parcial, chargeback, liquidação e disponibilidade de produto no Brasil.
4. Segurança/privacidade: dados compartilhados, controle de acesso, antifraude, retenção e registros de auditoria.

Não habilitar cobrança em produção enquanto as dependências críticas não estiverem aprovadas e testadas em sandbox.

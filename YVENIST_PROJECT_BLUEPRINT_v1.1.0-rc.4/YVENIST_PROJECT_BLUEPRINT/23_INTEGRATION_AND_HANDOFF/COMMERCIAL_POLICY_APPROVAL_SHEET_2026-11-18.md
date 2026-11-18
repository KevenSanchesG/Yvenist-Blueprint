# FOLHA DE APROVAÇÃO — POLÍTICAS COMERCIAIS E DE CONTRATAÇÃO

**Data:** 2026-11-18  
**Status:** AGUARDANDO APROVAÇÃO CONJUNTA  
**Aprovadores:** Keven e Rafael  
**Documentos-base:**  
- `MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md`
- `ORDER_CONTRACT_PAYMENT_STATE_MACHINE_2026-11-18.md`

Esta folha contém somente decisões que ainda precisam dos dois responsáveis. As recomendações do ChatGPT são propostas de trabalho e não substituem a aprovação de Keven e Rafael. Vocês podem aprovar uma recomendação, alterá-la ou deixar um item pendente.

## A. Comissão e receita

| ID | Decisão necessária | Recomendação para começar | Resposta dos responsáveis |
|---|---|---|---|
| COM-01 | Comissão progressiva e programa de lançamento | Modelo híbrido proposto: 3% para Parceiros Fundadores no lançamento; 5% na fase de expansão; 10% como taxa-alvo de maturidade. Comissão paga pelo fornecedor, somente sobre subpedido concluído. Critérios, duração, transição e elegibilidade sujeitos à aprovação conjunta | PROPOSTA DE KEVEN PARA APROVAÇÃO DE KEVEN + RAFAEL |
| COM-02 | Base comissionável | Valor das linhas concluídas após descontos financiados pelo fornecedor; frete, tributos, montagem/deslocamento e terceiros discriminados para análise contábil | PENDENTE |
| COM-03 | Taxa do PSP | Deduzir do repasse do fornecedor, separada da comissão e claramente exibida, se a viabilidade econômica e o contrato permitirem | PENDENTE |
| COM-04 | Comissão em reembolso parcial | Recalcular e reverter proporcionalmente à parcela reembolsada/não concluída | PENDENTE |
| ADS-01 | Exposição patrocinada | Poucas posições por categoria/região, etiqueta Patrocinado, elegibilidade e relevância antes do pagamento | PENDENTE |
| SUB-01 | Assinatura do consumidor | Fora do lançamento; definir benefícios, preço e prioridade apenas após acordo com fornecedores | PENDENTE / FUTURO |

### COM-01 — proposta detalhada para deliberação conjunta

A proposta submetida por Keven é um modelo híbrido de entrada e maturidade: **3% na fase de lançamento para Parceiros Fundadores; 5% na fase de expansão; 10% como taxa-alvo na operação madura**. A cobrança é do fornecedor, por subpedido concluído. Não há aprovação final até Rafael confirmar a mesma versão.

Documento normativo proposto: `COMMISSION_POLICY_AND_FOUNDING_PARTNER_LAUNCH_2026-11-18.md`. Ele define elegibilidade, benefícios não financeiros, coorte, prazo, transição, comunicação, métricas e salvaguardas. Os critérios quantitativos de expansão e maturidade continuam deliberadamente sujeitos à validação dos dois sócios, para não criar gatilhos automáticos sem dados do piloto.

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

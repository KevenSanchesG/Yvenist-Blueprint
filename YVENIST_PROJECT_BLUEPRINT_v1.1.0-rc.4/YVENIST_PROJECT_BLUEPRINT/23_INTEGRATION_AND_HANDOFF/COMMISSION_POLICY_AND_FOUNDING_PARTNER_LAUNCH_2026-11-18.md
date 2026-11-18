# COM-01 — POLÍTICA DE COMISSÃO PROGRESSIVA E PROGRAMA DE PARCEIROS FUNDADORES

**Versão:** 0.2 — regra comercial aprovada conjuntamente / ativação condicionada  
**Data:** 2026-11-18  
**Aprovadores:** Keven e Rafael  
**Status:** APPROVED_AS_JOINT_BUSINESS_RULE / PRODUCTION_ACTIVATION_BLOCKED_PENDING_SPECIALIST_GATES  
**Documentos relacionados:**
- `LOCAL_MARKET_LAUNCH_PLAN_CAMPO_GRANDE_ZONA_OESTE_2026-11-18.md`
- `MARKETPLACE_COMMERCIAL_AND_OPERATING_MODEL_PROPOSAL_2026-11-18.md`
- `COMMERCIAL_POLICY_APPROVAL_SHEET_2026-11-18.md`

> Keven informou expressamente que Rafael concorda com as definições que estão sendo documentadas. Esta versão registra a aprovação conjunta da estrutura comercial e dos parâmetros de lançamento aqui descritos. Isso não substitui contrato final, aprovação jurídica/contábil, definição da base COM-02, alocação de tarifa PSP COM-03 ou validação técnica do fluxo financeiro. Não ativar cobrança real antes dessas dependências.

## 1. Objetivo

Reduzir a barreira de entrada dos primeiros fornecedores, formar uma oferta local densa e confiável e aumentar a comissão somente quando o Yvenist comprovar que entrega valor comercial e operacional.

A política combina uma taxa de aquisição de oferta, uma etapa de expansão e uma taxa-alvo de maturidade. Tempo é um limite de proteção do fornecedor fundador, não justificativa isolada para elevar a comissão.

## 2. Estrutura aprovada

| Fase | Comissão do fornecedor | Aplicação |
|---|---:|---|
| Lançamento — Parceiro Fundador | **3%** | Condição inicial dos parceiros da coorte de lançamento |
| Expansão | **5%** | Quando a categoria/região demonstrar liquidez e passar os critérios desta política |
| Maturidade | **10%** | Taxa-alvo, somente após a plataforma demonstrar valor, qualidade operacional e sustentabilidade |

Regras gerais:
- Comissão paga pelo fornecedor.
- Cálculo e registro separados por `SupplierSubOrder`; nunca aplicar uma comissão única sobre o total de um evento com vários fornecedores.
- A comissão é adquirida somente sobre a parcela elegível efetivamente concluída, conforme a base COM-02 ainda sujeita à aprovação específica.
- Não há mensalidade obrigatória de entrada proposta para o MVP.
- Não há comissão por cadastro, exposição orgânica, orçamento sem contratação, solicitação recusada ou parte cancelada/não concluída.
- Tarifa do PSP, tributos, reembolsos e demais ajustes aparecem separados da comissão; a alocação financeira ainda depende de COM-03 e revisão especializada.
- Não transferir ao consumidor taxa vinculada a esta comissão sem decisão conjunta separada e divulgação prévia.

## 3. Programa Parceiro Fundador

### 3.1. Tamanho e composição da primeira coorte

A primeira coorte terá **meta de 20 fornecedores fundadores ativos e distintos**, distribuídos em quatro famílias de categoria, com meta de cinco fornecedores qualificados por família. A quantidade é uma meta de densidade e capacidade de onboarding, não uma regra universal nem limite permanente de fornecedores.

A seleção detalhada, subcategorias e cobertura estão em `LOCAL_MARKET_LAUNCH_PLAN_CAMPO_GRANDE_ZONA_OESTE_2026-11-18.md`.

Um fornecedor só conta como ativo quando:
1. concluiu cadastro e verificações aplicáveis;
2. aceitou a versão vigente dos termos comerciais;
3. publicou ao menos uma oferta real, com preço, escopo, área atendida e condições compreensíveis;
4. informou disponibilidade ou regra de disponibilidade atualizada;
5. concluiu a configuração necessária para responder e, quando habilitado, receber pedidos;
6. respondeu ao teste de contato/onboarding;
7. não está suspenso, duplicado ou com anúncio fictício/incompleto.

Cadastro sem oferta contratável ou sem disponibilidade não conta para a meta de 20. Um mesmo negócio conta uma vez no total de fornecedores distintos, ainda que atue em mais de uma categoria. A categoria pode contar esse parceiro em sua cobertura, mas o painel também deve sinalizar concentração e sobreposição.

### 3.2. Condição de 3% e prazo do Parceiro Fundador

O fornecedor fundador recebe **3% durante os primeiros 12 meses contados da sua primeira contratação concluída no Yvenist**.

Por que contar da primeira contratação concluída: evita consumir o período de benefício enquanto o fornecedor ainda não recebeu valor comprovado da plataforma. Se não houver contratação concluída, não existe comissão a cobrar e o relógio dos 12 meses ainda não começa.

Ao completar os 12 meses, o parceiro **não muda automaticamente para 5%**. A mudança só poderá ocorrer quando as duas condições forem verdadeiras:
- a categoria e a região relevantes tiverem atingido os critérios objetivos da fase de Expansão da seção 4.1; e
- o fornecedor tiver recebido aviso prévio e aceitado expressamente a nova condição, conforme a seção 5.

Se a categoria/região não tiver liquidez suficiente, o parceiro permanece em 3% até que os critérios sejam atingidos e a alteração seja validamente aceita. O prazo de 12 meses é uma proteção mínima, não uma data automática de aumento.

### 3.3. Benefícios do programa

Benefícios não financeiros propostos para a coorte:
- selo informativo “Parceiro Fundador”, com significado e período claramente explicados;
- onboarding assistido para catálogo, kits, preços e disponibilidade;
- canal prioritário de feedback durante o piloto;
- acesso antecipado a melhorias relevantes para fornecedores;
- painel/relatório básico de visualizações, solicitações, respostas, contratações e conclusões, conforme instrumentação disponível;
- participação em entrevistas e pilotos de produto.

O selo não representa avaliação superior, certificação legal, garantia de qualidade, endosso do Yvenist ou preferência algorítmica automática. Não vender o selo e não prometer vendas garantidas.

## 4. Indicadores e gatilhos para mudança de fase

### 4.0. Unidade de análise e regra de medição

Os indicadores devem ser segmentados por **categoria × área geográfica × coorte**, e não somente por um número geral do aplicativo. Uma média global pode esconder uma categoria sem oferta ou uma região sem atendimento.

Definições:
- **Solicitação qualificada:** EventRequest ou SupplierSubOrder real, enviado por consumidor com intenção de contratação e com os dados obrigatórios para aquela categoria; excluir testes internos, bots, duplicatas e simples visualizações.
- **Taxa de atendimento (fill rate):** solicitações qualificadas em que ao menos um fornecedor elegível confirma que pode atender data, local, escopo e preço, divididas pelo total de solicitações qualificadas daquela categoria/área.
- **Taxa de resposta no prazo:** subpedidos válidos respondidos com confirmação, recusa ou pedido de esclarecimento dentro de um dia útil, divididos pelo total de subpedidos válidos atribuídos.
- **Fornecedor ativo:** possui oferta publicada e contratável, preço e área atualizados, disponibilidade configurada e responde às oportunidades recebidas; login isolado não conta como atividade.
- **Cancelamento originado pelo fornecedor:** subpedido aceito/contratado e depois cancelado por iniciativa do fornecedor, separado por motivo e com exclusões somente quando justificadas e auditadas.
- **Margem de contribuição:** receita de comissão efetivamente adquirida menos custos variáveis atribuídos ao Yvenist (incluindo PSP, reembolsos/perdas e suporte variável, conforme alocação contábil aprovada).

O painel deve registrar denominadores, período, categoria, área e motivo de falha. Nunca misturar solicitações sem intenção, testes e visitas de catálogo na taxa de atendimento.

### 4.1. Gatilho de Lançamento → Expansão (3% → 5%)

A taxa de 5% poderá ser disponibilizada na categoria/área somente quando todos os seguintes critérios forem satisfeitos:

| Indicador | Critério interno proposto |
|---|---|
| Profundidade mínima de amostra | Pelo menos 10 solicitações qualificadas na categoria/área em cada janela móvel de 90 dias; se não houver amostra, não declarar a fase pronta |
| Taxa de atendimento | **≥70%** das solicitações qualificadas recebem ao menos uma confirmação viável dentro de até 2 dias úteis |
| Resposta dos fornecedores | **≥80%** dos subpedidos válidos recebem resposta em até 1 dia útil |
| Saúde da oferta | **≥70%** dos fundadores da categoria continuam ativos, com oferta e disponibilidade atualizadas |
| Cancelamento do fornecedor | **≤10%** dos subpedidos aceitos/contratados, quando houver pelo menos 20 casos observáveis; abaixo disso, análise qualitativa e acompanhamento, sem declarar aprovação automática |
| Sustentabilidade | Margem de contribuição não negativa na categoria por 2 meses consecutivos, ou subsídio de lançamento limitado, com valor e prazo expressamente aprovados pelos sócios |
| Estabilidade | Todos os critérios aplicáveis aprovados em **duas avaliações mensais consecutivas**, cada uma usando janela móvel de 90 dias |

A avaliação é feita por categoria/área. Uma categoria aprovada pode avançar sem obrigar todas as demais; as outras permanecem em 3%.

Para os fornecedores fundadores, a taxa de 5% somente se aplica a novos subpedidos aceitos depois que: (a) o período individual mínimo de 12 meses terminou; (b) o gate da categoria/área foi aprovado; (c) houve aviso de 60 dias; e (d) o fornecedor aceitou expressamente. A aprovação do gate não aumenta taxa retroativamente nem altera contrato existente.

### 4.2. Gatilho de Expansão → Maturidade (5% → 10%)

A taxa-alvo de 10% não terá aumento automático por tempo de calendário. Exige demonstração de que o produto e a operação entregam valor adicional suficiente para sustentá-la.

Critérios internos propostos por categoria/área:

| Indicador | Critério interno proposto |
|---|---|
| Tempo mínimo na expansão | Pelo menos 6 meses operando na fase de 5% |
| Volume observável | Pelo menos 30 solicitações qualificadas nos últimos 180 dias |
| Taxa de atendimento | **≥80%** dentro de até 2 dias úteis |
| Resposta dos fornecedores | **≥90%** dos subpedidos válidos respondidos em até 1 dia útil |
| Retenção da oferta | **≥75%** dos fornecedores ativos no início da janela permanecem ativos ao final de 6 meses |
| Cancelamento do fornecedor | **≤5%** dos subpedidos aceitos/contratados, quando houver pelo menos 30 casos observáveis |
| Sustentabilidade | Margem de contribuição positiva por 3 meses consecutivos na categoria/área |
| Estabilidade | Gates aprovados em duas revisões trimestrais consecutivas |
| Qualidade | Nenhuma falha crítica recorrente de segurança, fraude, suporte ou entrega sem plano corretivo concluído |

Atingir os números não ativa 10% automaticamente. Os sócios devem revisar o relatório, verificar se a plataforma realmente passou a entregar valor proporcional (demanda, conversão, suporte, pagamentos, confiança e operação) e autorizar a proposta de alteração. Categoria sem amostra suficiente ou com margem insustentável não avança.

### 4.3. Natureza dos limites

Os percentuais, períodos e volumes acima são **metas operacionais internas do Yvenist**, construídas a partir das métricas recomendadas para marketplaces e da escala inicial definida para o piloto. Não são benchmarks universais nem promessa de desempenho do mercado. Serão revistos após os primeiros 90 dias de dados reais, sem reduzir retroativamente direitos ou taxas já contratadas.

A referência a16z explica que match rate, market depth e time-to-match devem ser avaliados conforme o tipo de marketplace; não estabelece um patamar universal que todas as empresas devam atingir. Portanto, os valores acima são hipóteses gerenciais explícitas, não estatísticas atribuídas à a16z.

## 5. Aviso, aceite e entrada em vigor de nova comissão

### 5.1. Padrão de comunicação

Adotar **60 dias corridos de aviso prévio** como padrão contratual e operacional do Yvenist. Esse prazo é uma política de previsibilidade escolhida pela empresa; não deve ser apresentado como prazo legal geral obrigatório. A legislação civil brasileira determina parâmetros contratuais objetivos e boa-fé, mas não fixa nesses dispositivos um aviso universal de 60 dias para toda alteração de comissão. O contrato deverá ser revisado por advogado brasileiro.

O aviso deve ocorrer:
- 60 dias antes da data proposta: comunicação formal no painel do fornecedor e por e-mail;
- 30 dias antes: lembrete com resumo da mudança e simulação de impacto;
- 7 dias antes: último lembrete para fornecedor que ainda não decidiu.

A notificação deve informar: taxa atual e proposta, justificativa e indicadores agregados que fundamentam a fase, data de vigência, exemplos monetários, tratamento de pedidos em andamento, tarifas PSP separadas, como aceitar e como deixar de receber novas solicitações.

### 5.2. Aceite e recusa

- Exigir aceite expresso e auditável da nova versão dos termos, com usuário, data/hora, versão, taxa e evidência.
- Silêncio, login, recebimento de mensagem ou continuidade passiva de uso não equivalem a aceite.
- Sem aceite até a data efetiva, o fornecedor não recebe novos subpedidos sujeitos à nova taxa; poderá pausar/desativar sua oferta ou encerrar a participação, respeitando os contratos existentes.
- Não aplicar penalidade por recusar uma nova taxa ainda não aceita.
- Pedidos/contratos já aceitos antes da data efetiva mantêm a taxa e a versão vigentes no momento do aceite daquele subpedido, mesmo que a execução ocorra depois.

### 5.3. Conteúdo mínimo da comunicação

O fornecedor deve receber uma tela comparativa simples, por exemplo: “Sua taxa atual é 3%. A partir de DD/MM/AAAA, novas contratações poderão ter taxa de 5%. Em uma base comissionável hipotética de R$ 1.000, a comissão passaria de R$ 30 para R$ 50, antes de tarifas PSP e ajustes.” O exemplo não deve confundir comissão com líquido final.

## 6. Exemplo monetário

Para uma base comissionável hipotética de R$ 1.000,00:

| Fase | Comissão | Saldo antes de PSP, tributos e ajustes |
|---|---:|---:|
| Fundador — 3% | R$ 30,00 | R$ 970,00 |
| Expansão — 5% | R$ 50,00 | R$ 950,00 |
| Maturidade — 10% | R$ 100,00 | R$ 900,00 |

A base final depende da COM-02. O exemplo não representa promessa de repasse líquido.

## 7. Métricas obrigatórias no painel interno

Instrumentar, no mínimo:
- fornecedores prospectados, qualificados, cadastrados, ativos e transacionando;
- cobertura por categoria e subcategoria;
- cobertura geográfica por bairro/área de atendimento;
- disponibilidade atualizada;
- solicitações qualificadas e subpedidos por categoria/área;
- respostas em prazo, confirmações, recusas e motivos;
- fill rate e tempo até primeira resposta/primeira confirmação;
- conversão de solicitação em pagamento e em conclusão;
- GMV contratado e concluído, comissão adquirida e receita líquida;
- taxa efetiva realizada (receita de comissão / GMV comissionável concluído);
- cancelamentos por origem e etapa, reembolsos, disputas e chargebacks;
- retenção de fornecedores por coorte e concentração de receita por fornecedor;
- custos variáveis, margem de contribuição e subsídio aprovado;
- aceite de termos e histórico de avisos de mudança de taxa.

Métricas devem ser auditáveis por período e categoria/área; o sistema não pode produzir mudança de taxa por conta própria.

## 8. Regras imutáveis para o produto e para Claude Code

- Percentuais e fases devem ser dados versionados/configuráveis, nunca hard-coded em tela ou regra de negócio.
- Registrar `commission_policy_version`, `supplier_cohort`, `category_id`, `service_area_id`, `rate_applied`, `commissionable_amount`, `commission_amount`, moeda, `supplier_sub_order_id`, data de aceite do fornecedor e timestamps.
- Congelar taxa no snapshot comercial do subpedido quando o fornecedor aceita a contratação.
- Mostrar taxa, valor estimado da comissão, tarifas PSP separadas e líquido estimado antes do aceite.
- Manter registro de notificação, entrega, leitura quando disponível, aceite ou recusa.
- Criar avaliação de gates e relatório administrativo; não ativar taxa por cron, data ou regra algorítmica.
- Exigir autorização administrativa de dois sócios para mudar a fase/taxa em cada categoria/área.
- Testar arredondamento, reembolso parcial, cancelamento, chargeback, idempotência e pedidos aceitos na fronteira de vigência.
- Não permitir que Claude Code invente critérios, altere percentuais, defina avisos ou ative uma nova fase.
- Não ativar cobrança em produção antes da base COM-02, custo PSP COM-03, contratos, parecer jurídico/contábil e homologação do fluxo de pagamento.

## 9. Fontes e limites da pesquisa

- a16z, *13 Metrics for Marketplace Companies* (21/02/2020): match rate e market depth precisam ser definidos conforme o modelo e o mercado. https://a16z.com/13-metrics-for-marketplace-companies/
- a16z, *The Marketplace Glossary* (18/02/2020): liquidez como facilidade/probabilidade de compradores e vendedores encontrarem uma contraparte adequada; fill rate, market depth e time-to-match são medidas úteis. https://a16z.com/the-marketplace-glossary/
- Código Civil, Lei 10.406/2002, arts. 421-A e 422, texto consolidado no Senado Federal: parâmetros objetivos, excepcionalidade de revisão e boa-fé. https://legis.senado.gov.br/norma/552282/publicacao/34620807
- A pesquisa não encontrou prazo legal único aplicável a toda alteração de comissão entre marketplace e fornecedor; por isso os 60 dias são regra comercial contratual proposta, sujeita a parecer jurídico.
- Referências externas não determinam os thresholds internos de 70%, 80%, 90%, 12 meses ou 60 dias. Esses são parâmetros de gestão escolhidos para o piloto e devem ser reavaliados com dados.

## 10. Registro de aprovação

- Estrutura progressiva 3% / 5% / 10%: **APROVADA CONJUNTAMENTE**.
- Comissão paga pelo fornecedor e vinculada a subpedido concluído: **APROVADA COMO DIREÇÃO COMERCIAL**; base e taxas do PSP permanecem em decisões próprias.
- Prazo mínimo fundador de 12 meses a partir da primeira contratação concluída: **APROVADO COMO REGRA DE PROGRAMA**.
- Transição condicionada a gates, aviso de 60 dias e aceite expresso: **APROVADA COMO REGRA DE PROGRAMA**.
- Ativação financeira em produção: **BLOQUEADA** até validações jurídicas, contábeis, PSP e COM-02/COM-03.

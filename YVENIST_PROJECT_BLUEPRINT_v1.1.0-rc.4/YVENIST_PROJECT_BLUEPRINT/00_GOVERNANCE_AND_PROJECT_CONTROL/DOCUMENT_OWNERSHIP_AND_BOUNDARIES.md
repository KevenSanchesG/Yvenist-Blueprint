# DOCUMENT OWNERSHIP AND BOUNDARIES
**Release do Blueprint:** `1.0.0`

**Versão:** 0.4  
**Status:** `PROPOSAL`  
**Responsável de manutenção:** responsável de governança documental a designar  
**Objetivo:** estabelecer uma única fonte de verdade por assunto e impedir duplicidade entre os domínios do Blueprint.

## 1. Regras obrigatórias

1. Cada assunto normativo deve ter um único documento proprietário.
2. Outros documentos podem resumir ou referenciar a fonte proprietária, mas não copiar regras completas.
3. Se um assunto tiver dimensão estratégica, operacional, jurídica e técnica, cada documento deve cobrir apenas sua própria dimensão e apontar para os demais.
4. Em caso de conflito entre documentos, não escolher silenciosamente. Registrar a divergência, identificar as fontes, avaliar autoridade e atualidade e encaminhar para decisão humana.
5. O `YVENIST/` é contexto e índice; não é fonte normativa de regras detalhadas.
6. Templates descrevem formato; não definem política de negócio.
7. Sistemas transversais explicam relações e dependências entre áreas; não duplicam documentos de domínio.
8. Toda fonte proprietária deve registrar status, responsável, fontes, data de revisão e histórico.

## 2. Matriz de propriedade documental

| Assunto | Documento proprietário | Documentos consumidores / limites |
|---|---|---|
| Framework de criação, fases e gates | `00/.../PRODUCT_CREATION_FRAMEWORK.md` | Todos os domínios seguem o método; não repetem o framework. |
| Responsabilidades e papéis humanos | `00/.../DECISION_AUTHORITY_AND_RACI.md` | `ORGANIZATION_AND_RESPONSIBILITIES.md` descreve estrutura operacional, sem redefinir poderes de aprovação. |
| Autoridade e aprovação de decisões | `00/.../DECISION_AUTHORITY_AND_RACI.md` + `APPROVAL_GATES.md` | `DECISION_LOG.md` registra decisões tomadas; não estabelece por si só quem pode aprová-las. |
| Significado dos status e escopo | `BLUEPRINT_ARCHITECTURE.md` (taxonomia mestre) | Cada documento aplica os status sem criar variantes locais. |
| Glossário | `00/.../GLOSSARY.md` | Outros documentos usam termos do glossário; podem propor novos termos ao proprietário. |
| Registro de fontes/evidências | `00/.../SOURCE_REGISTER.md` | Documentos especializados citam IDs de fonte; não replicam cadastro bibliográfico. |
| Baseline factual da empresa | `YVENIST/CURRENT_STATE_BASELINE.md` | Auditorias técnicas, Figma e documentos específicos complementam com evidências próprias. Baseline registra observação, não decisão. |
| Visão geral do ecossistema | `YVENIST/ECOSYSTEM_OVERVIEW.md` | `ECOSYSTEM_AND_ACTOR_MAP.md` detalha papéis, relações e hipóteses de produto; não reescreve a visão geral. |
| Catálogo de superfícies | `YVENIST/PRODUCT_SURFACES_CATALOG.md` como índice; detalhe em `05/...` | `PRODUCT_SURFACES_OVERVIEW.md` descreve o portfólio e suas relações; catálogo YVENIST é índice factual e status de existência. Cada superfície tem especificação proprietária em `05`. |
| Estrutura e funcionamento organizacional | `01/.../ORGANIZATION_AND_RESPONSIBILITIES.md` | Descreve estrutura/capacidades; `00/.../OPERATING_MODEL_AND_RESPONSIBILITIES.md` descreve cadência, ritos e execução; autoridade de aprovação pertence ao RACI. |
| Estratégia empresarial | `01/.../STRATEGIC_POSITIONING.md` | `COMPANY_OVERVIEW.md` resume; `BUSINESS_MODEL.md` detalha criação/entrega/captura de valor. |
| Modelo de receita e monetização | `01/.../REVENUE_AND_MONETIZATION.md` | `PRICING_AND_COMMISSION_PRINCIPLES.md` detalha princípios de preço/comissão; `FINANCIAL_MODEL_AND_UNIT_ECONOMICS.md` modela cenários. Valores só são aprovados por responsável humano. |
| Fundamentos da marca | `02/.../BRAND_FOUNDATION.md` | Guarda propósito, essência, posicionamento, personalidade e promessa aprovados; fonte de entrada do sistema de marca. |
| Estratégia de expressão da marca | `07/.../BRAND_STRATEGY.md` | Traduz os fundamentos em estratégia de experiência, expressão e governança; não reabre posicionamento sem decisão registrada. |
| Pesquisa e jornadas atuais | `03/.../CURRENT_USER_JOURNEYS.md` | Descreve o comportamento atual observado com fonte e evidência; não é fluxo futuro de produto. |
| Jornadas e fluxos futuros | `06/.../USER_JOURNEYS_AND_FLOWS.md` | Especifica a experiência proposta; cita pesquisa atual e validações. |
| Regras de negócio do marketplace | `04/.../BUSINESS_RULES.md` | Políticas comerciais, transações e operações especializam as regras e referenciam IDs; não criam regras contraditórias. |
| Modelo de domínio e estados | `04/.../DOMAIN_MODEL.md` e `STATE_MACHINES.md` | APIs implementam contratos derivados; UI exibe estados definidos, não cria estados de negócio independentes. |
| Políticas comerciais gerais | `04/.../COMMERCIAL_POLICIES.md` | Finanças/jurídico valida obrigações; suporte comunica e executa casos conforme essas políticas. |
| Operação do fornecedor | `11/.../OPERATIONS_MODEL.md` e procedimentos especializados | `21/SUPPLIER_OPERATIONS_SYSTEM.md` resume as dependências transversais, não replica SOPs. |
| Execução de serviço no evento | `11/.../SERVICE_FULFILLMENT_AND_EVENT_INCIDENT_OPERATIONS.md` | Cobre a prestação do serviço físico e incidentes do evento; logística cobre transporte/entrega. |
| Logística e entrega | `17/.../FULFILLMENT_MODEL.md` | `DELIVERY_EXCEPTIONS_AND_INCIDENTS.md` cobre exceções logísticas; para incidentes de serviço prestado, referenciar 11. |
| Atendimento e gestão de casos | `13/.../SUPPORT_CHANNELS_AND_CASE_MANAGEMENT.md` | Define tickets, comunicação, triagem, SLA e escalonamento; `COMMUNICATION_TEMPLATES.md` mantém modelos reutilizáveis aprovados; reembolso/estorno financeiro segue 14 e políticas de 04/16. |
| Notificações transacionais | `06/.../NOTIFICATIONS_AND_COMMUNICATION_FLOWS.md` | Define eventos e lógica de comunicação de produto; mensagens de atendimento ficam em 13; campanhas/CRM em 15. |
| Reembolsos, estornos e disputas transacionais | `14/.../CANCELLATIONS_REFUNDS_AND_DISPUTES.md` | Define estados e regras transacionais; 13 define como o atendimento acompanha e comunica o caso. |
| Pagamentos, repasses e conciliação | `14/.../PAYMENT_AND_SETTLEMENT_FLOWS.md` | `COMMISSIONS_FEES_AND_RECONCILIATION.md` aprofunda taxas e conciliação; 16 valida obrigações legais, fiscais e contábeis. |
| Moderação e enforcement | `12/.../MODERATION_AND_ENFORCEMENT.md` | Trust & Safety define princípios e risco; catálogo e suporte referenciam procedimentos. |
| Dados: propriedade, qualidade e acesso | `18/.../DATA_GOVERNANCE_AND_OWNERSHIP.md` | `09/.../DATA_ARCHITECTURE_AND_LIFECYCLE.md` descreve estruturas e implementação técnica. |
| Arquitetura técnica de dados | `09/.../DATA_ARCHITECTURE_AND_LIFECYCLE.md` | `18` define governança de uso/qualidade; privacidade define obrigações e retenção conforme avaliação legal. |
| LGPD e políticas de privacidade | `16/.../PRIVACY_AND_DATA_PROTECTION_LGPD.md` | Documento jurídico de políticas e papéis; `PRIVACY_OPERATIONS_AND_DATA_SUBJECT_RIGHTS.md` é fonte do processo operacional; 09 e 18 implementam controles técnicos/governança. |
| Direitos dos titulares | `16/.../PRIVACY_OPERATIONS_AND_DATA_SUBJECT_RIGHTS.md` | Suporte pode receber e encaminhar solicitações; sistemas implementam mecanismos; decisões jurídicas precisam de revisão profissional. |
| Segurança e threat model | `09/.../SECURITY_PRIVACY_AND_THREAT_MODEL.md` | `SECURE_SDLC_AND_SECURITY_STANDARDS.md` define práticas ao longo do ciclo; 19 contém plano/relatórios de teste. |
| Segurança no ciclo de desenvolvimento | `09/.../SECURE_SDLC_AND_SECURITY_STANDARDS.md` | `10` integra ao fluxo de desenvolvimento; `19/SECURITY_TESTING.md` executa e reporta testes. |
| Testes e critérios de qualidade | `19/.../TEST_STRATEGY.md` | Relatórios de testes e QA registram evidências; não redefinem estratégia. |
| Confiabilidade e SLOs | `19/.../SERVICE_RELIABILITY_AND_OPERATIONS.md` | Monitoramento/alertas e incidentes operacionalizam os objetivos; 20 revisa desempenho pós-lançamento. |
| Métricas e definições de KPI | `18/.../KPI_DICTIONARY.md` | Dashboards consomem definições; business/product/growth podem ter visões próprias sem mudar a fórmula oficial. |
| Personalização e recomendações | `18/.../PERSONALIZATION_AND_DISCOVERY.md` | `RECOMMENDATION_SYSTEM_PRINCIPLES.md` define princípios e limites algorítmicos; superfícies UX implementam a apresentação. Conteúdo patrocinado segue documento próprio. |
| Governança de conteúdo patrocinado | `18/.../SPONSORED_CONTENT_GOVERNANCE.md` | Growth/marketing define campanhas dentro dos limites aprovados; recomendações orgânicas não devem ser confundidas com patrocínio. |
| Roadmap e priorização | `02/.../PRODUCT_ROADMAP.md` e `FEATURE_PRIORITIZATION.md` | Define direção temporal e critérios de prioridade; backlog em 10 organiza execução e não altera prioridade estratégica sozinho. |
| Métricas de produto | `02/.../PRODUCT_SUCCESS_METRICS.md` | Define resultados e perguntas de sucesso do produto; fórmulas oficiais ficam no KPI Dictionary de 18 e métricas de negócio em 01. |
| Dashboards e relatórios | `18/.../OPERATIONAL_AND_EXECUTIVE_DASHBOARDS.md` | Apresenta métricas derivadas do KPI Dictionary; não redefine cálculos nem objetivos. |
| Backoffice administrativo | `05/.../ADMIN_BACKOFFICE.md` | Documento de produto/superfície; requisitos operacionais detalhados ficam em `12/.../ADMIN_BACKOFFICE_REQUIREMENTS.md`. |
| Backlog de implementação | `10/.../DELIVERY_BACKLOG.md` | Registra unidades de entrega; prioridade de produto referenciada a 02. |
| Integração com projeto existente | `23/.../INTEGRATION_README.md` + `TARGET_REPOSITORY_AUDIT_INSTRUCTIONS.md` | Plano de migração em 00; checklist de compatibilidade em 23. Nenhum arquivo é alterado sem aprovação. |

Os caminhos usam abreviações `00/...` para facilitar leitura; os arquivos finais devem usar os caminhos completos da árvore oficial.

## 3. Resolução de duplicidade ou conflito

Quando o Claude encontrar duas fontes sobre o mesmo tema:

1. Registrar os dois caminhos e as versões/datas.
2. Verificar se uma fonte é explicitamente proprietária na matriz.
3. Comparar status, autoridade de aprovação, evidências e atualidade.
4. Não inferir que documento mais novo vence automaticamente: pode ser um rascunho.
5. Se houver decisão já aprovada, preservá-la até revisão formal.
6. Se não houver fonte proprietária ou se houver conflito entre decisões aprovadas, abrir questão em `ASSUMPTIONS_AND_OPEN_QUESTIONS.md` e decisão em `DECISION_LOG.md`.
7. Atualizar este mapa somente após aprovação da alteração.

## 4. Regra de manutenção

- Revisar este mapa sempre que a árvore mudar.
- Um documento novo exige definição de proprietário, consumidores, entradas, saídas e limites.
- Não criar um arquivo separado se a responsabilidade puder ser coberta claramente por uma fonte existente sem excesso de escopo.
- Registrar fusões, renomes e depreciações no changelog; preservar histórico no `ARCHIVE/` quando aplicável.

# YVENIST PROJECT BLUEPRINT

**Documento:** Arquitetura geral do Blueprint  
**Versão:** 1.0.0 — arquitetura-base final aprovada para orientar a construção progressiva do Blueprint  
**Status:** `APPROVED_AS_WORKING_ARCHITECTURE` — arquitetura-base aprovada em 17/11/2026; addendum multi-sessão e registro das fontes do projeto em revisão  
**Escopo:** direcionamento integral para planejar, estruturar, construir, operar, lançar e evoluir a Yvenist como negócio, marketplace e ecossistema de produtos digitais.  
**Princípio:** o Blueprint orienta o Claude; não substitui a análise, as decisões humanas, a validação de mercado, o projeto existente nem especialistas profissionais.

---

## 1. Objetivo e escopo

O `YVENIST_PROJECT_BLUEPRINT` é o pacote independente de conhecimento, planejamento, governança e instruções que será entregue ao Claude Code para orientar o trabalho sobre a Yvenist.

O objetivo não é apenas desenvolver telas ou aplicativos. O Claude deverá compreender e ajudar a estruturar o negócio e seu ecossistema de ponta a ponta, incluindo:

- estratégia empresarial e estratégia de produto;
- consumidores, fornecedores, profissionais, parceiros e entregadores;
- marketplace, catálogo, descoberta, oferta, demanda e liquidez;
- aplicativos, interfaces administrativas, ferramentas internas e canais digitais;
- regras comerciais, solicitações, orçamentos, propostas, contratações e transações;
- operação de fornecedores, atendimento, suporte, moderação e administração da plataforma;
- marca, experiência, design, conteúdo e comunicação;
- arquitetura de software, dados, integrações, segurança e infraestrutura;
- aquisição, ativação, retenção, relacionamento e crescimento;
- finanças, métricas, conformidade, riscos e governança;
- testes, lançamento, operação contínua e evolução.

O Blueprint será construído antes de sua integração ao repositório que Rafael utiliza. Na integração, o Claude deverá primeiro auditar o ambiente real e propor um plano de adaptação. Não deverá presumir que todos os sistemas, aplicativos, processos ou recursos descritos como possibilidades já existem ou fazem parte do MVP.

## 1.1. Fontes oficiais do projeto declaradas pelos responsáveis

Os responsáveis indicaram como fontes primárias pretendidas:

- GitHub — repositório do projeto: https://github.com/KevenSanchesG/Yvenist
- Figma — arquivo `Yvenist_v0`: https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1

Essas fontes estão registradas em `00_GOVERNANCE_AND_PROJECT_CONTROL/SOURCE_REGISTER.md`. Sua designação pelos responsáveis não significa que o acesso já foi testado ou que o conteúdo tenha sido auditado. A aquisição, o versionamento histórico do Figma e a integração com o GitHub seguem `23_INTEGRATION_AND_HANDOFF/PROJECT_SOURCE_ACQUISITION_PROTOCOL.md`.

O GitHub é evidência do estado de implementação em um commit/branch identificável; não substitui decisões aprovadas de produto ou negócio. O Figma é evidência do estado e da história do design por versão/página/frame; não prova implementação nem aprovação automática. Conflitos entre fontes devem ser registrados e submetidos aos responsáveis.

## 2. O que o Blueprint é — e o que não é

### É

- um mapa de trabalho para o Claude;
- uma arquitetura de conhecimento e documentação;
- um método de execução por etapas, entregáveis e critérios verificáveis;
- uma referência para manter coerência entre negócio, produto, operação, design e engenharia;
- um mecanismo de rastreabilidade de decisões, requisitos, evidências e alterações;
- um pacote de integração controlada com o projeto existente.

### Não é

- uma declaração de que todas as funcionalidades listadas serão desenvolvidas;
- uma especificação técnica baseada em suposições sobre o backend atual;
- uma autorização para alterar o repositório do Rafael;
- um substituto para entrevistas, validação comercial, testes com usuários ou assessoria jurídica, contábil e de segurança;
- uma ordem para criar todos os documentos e sistemas simultaneamente.

## 3. Princípios estruturais obrigatórios

1. **Compreender antes de construir:** negócio, usuários, regras, dados e operação precedem decisões de interface e implementação.
2. **Preservar antes de migrar:** nenhum arquivo, histórico, código ou decisão existente será descartado ou sobrescrito sem inventário, justificativa e autorização.
3. **Distinguir realidade de intenção:** separar o que existe hoje, o que foi aprovado, o que é proposta, o que é hipótese e o que é visão futura.
4. **Uma fonte de verdade por assunto:** documentos especializados podem referenciar outros; não devem duplicar regras com risco de divergência.
5. **Não presumir escopo:** identificar explicitamente `MVP`, `PÓS-MVP`, `VISÃO FUTURA`, `FORA DE ESCOPO` e `A VALIDAR`.
6. **Não inventar capacidades:** backend, APIs, pagamentos, disponibilidade, fornecedores, dados, integrações e operações só serão tratados como existentes após verificação.
7. **Projetar o serviço completo:** considerar consumidor, fornecedor, entregador, administração, suporte e processos internos quando aplicáveis.
8. **Executar por entregáveis verificáveis:** cada atividade deve declarar objetivo, entradas, método, saída, dependências, responsável, evidência e critério de aceite.
9. **Construir por fluxos completos:** priorizar fatias verticais de valor, e não telas isoladas sem operação funcional.
10. **Aprovação humana nos pontos críticos:** estratégia, modelo comercial, políticas, identidade, arquitetura e ações de alto impacto exigem revisão dos responsáveis.
11. **Eficiência sem superficialidade:** reutilizar padrões, automatizar verificações seguras, evitar documentos redundantes e trabalhar em lotes coerentes; não pular descoberta, validação ou qualidade para aparentar velocidade.
12. **Segurança desde o início:** dados pessoais, pagamentos, permissões, fraudes, registros e ações administrativas devem ser considerados desde o desenho.
13. **Rastreabilidade ponta a ponta:** conectar necessidades e objetivos a requisitos, regras, fluxos, telas, APIs, implementação, testes e métricas.
14. **Iteração controlada:** fases podem voltar e evoluir; mudanças devem registrar impacto e preservar histórico.

## 4. Modelo de trabalho do Claude

O Claude deverá atuar como coordenador de execução e colaborador especializado, não como autoridade unilateral sobre a empresa.

Para cada demanda relevante, deverá:

1. identificar o objetivo de negócio e o usuário afetado;
2. consultar a documentação e as decisões aplicáveis;
3. verificar o estado atual do projeto e das capacidades técnicas, quando necessário;
4. identificar evidências, lacunas, premissas, riscos e dependências;
5. propor a menor solução completa que atenda ao objetivo;
6. definir entregáveis e critérios de aceite antes de executar;
7. produzir ou alterar os artefatos autorizados;
8. validar o resultado com evidências e testes proporcionais ao risco;
9. atualizar documentação, decisões, rastreabilidade e progresso;
10. apresentar pendências e pontos que exigem decisão humana.

O Claude não deve transformar uma solicitação pontual em expansão de escopo sem justificar o benefício e obter aprovação quando necessário.

### 4.1. Trabalho com duas sessões Claude Code no mesmo computador

O Blueprint prevê um protocolo multi-sessão aditivo para duas sessões independentes na aba Code do mesmo Claude Desktop. A proposta utiliza:

- Session A — Coordinator: distribui tarefas, mantém o `WORKSTREAM_REGISTRY.md`, acompanha dependências e integra entregas.
- Session B — Specialist/Worker: executa workstreams delimitados e entrega handoff verificável.
- Sessões independentes do Claude Desktop Code podem executar trabalho paralelo; a documentação atual descreve cópias isoladas por Git worktree em repositórios Git. O coordenador deve confirmar o caminho/branch efetivo de cada sessão antes de permitir escrita.
- Mensagens nativas cross-session são documentadas para Claude Code compatível: Windows nativo `v2.1.234+`; macOS/Linux/WSL 2 `v2.1.224+`. `@menção` de sessão requer `v2.1.232+`. A disponibilidade real será confirmada no piloto; o fallback é brief transferido pelo operador.
- No Desktop, o controle `Worktree` precisa ser ativado antes de iniciar cada sessão que deve ter cópia isolada; vem desativado por padrão. Confirmar path/branch de cada sessão antes de permitir escrita paralela.
- Um único escritor por arquivo e uma única sessão coordenadora por ciclo.
- `WORKSTREAM_REGISTRY.md`, Git, commits e handoffs são fontes persistentes de estado; mensagens cross-session são canal rápido de coordenação e não substituem registros, arquivos ou decisões humanas.

Se não houver Git ou isolamento verificável, limitar a colaboração a leitura/pesquisa paralela ou serializar as alterações. O repositório GitHub declarado e o arquivo Figma de referência estão registrados em `00_GOVERNANCE_AND_PROJECT_CONTROL/SOURCE_REGISTER.md`; a aquisição deve seguir `23_INTEGRATION_AND_HANDOFF/PROJECT_SOURCE_ACQUISITION_PROTOCOL.md`. O protocolo detalhado está em `00_GOVERNANCE_AND_PROJECT_CONTROL/MULTI_SESSION_COLLABORATION/`. O addendum multi-sessão `0.3` permanece `PROPOSAL` até teste-piloto e aprovação humana específica; a aprovação da arquitetura-base `1.0.0` permanece intacta.

## 5. Status e classificação padronizados

### Status de decisões e informações

- `APPROVED`: decisão aprovada pelos responsáveis.
- `PROPOSAL`: proposta ainda não aprovada.
- `ASSUMPTION`: hipótese que precisa de validação.
- `UNVERIFIED`: informação ainda não verificada.
- `BACKEND_DEPENDENCY`: depende de capacidade ou decisão técnica ainda não confirmada.
- `SUPERSEDED`: substituída por decisão posterior, preservando histórico.
- `REJECTED`: rejeitada formalmente, com justificativa.

### Classificação de escopo

- `MVP`: necessário para o primeiro lançamento definido.
- `POST_MVP`: planejado para uma etapa posterior.
- `FUTURE_VISION`: possibilidade ou direção de longo prazo.
- `OUT_OF_SCOPE`: explicitamente fora do escopo atual.
- `TO_VALIDATE`: depende de pesquisa, teste ou decisão.

### Estado de execução documental

- `NOT_STARTED`, `IN_PROGRESS`, `IN_REVIEW`, `APPROVED`, `BLOCKED`, `SUPERSEDED`.

Não misturar status de decisão, escopo e execução. Um recurso pode, por exemplo, ser `PROPOSAL` e `POST_MVP` ao mesmo tempo.

## 6. Árvore proposta do Blueprint

### 6.1. Núcleo de contexto YVENIST

A pasta `YVENIST/` é o ponto de entrada para o conhecimento específico e relativamente estável da empresa e do ecossistema. Ela responde: o que é a Yvenist, quais elementos compõem seu ecossistema, quais superfícies de produto estão consideradas e qual é o estado atual conhecido.

Ela **não** substitui as áreas numeradas nem deve duplicar especificações detalhadas. A regra é:

- `YVENIST/`: contexto consolidado, visão de conjunto, baseline factual e índice de navegação;
- `00_...` a `23_...`: estratégia, políticas, requisitos, processos, especificações e planos de trabalho por domínio;
- `.claude/`: instruções operacionais e mecanismos de execução do Claude Code;
- `ASSETS/`: arquivos de referência e materiais de marca/design;
- `ARCHIVE/`: versões históricas e materiais superados preservados.

O `YVENIST_MASTER_CONTEXT.md` deverá ser breve e apontar para fontes especializadas, em vez de repetir seu conteúdo. A `CURRENT_STATE_BASELINE.md` deverá conter apenas fatos observados, com data, fonte e nível de confiança. Até a auditoria do projeto existente, campos desconhecidos permanecem `UNVERIFIED`.

### 6.2. Árvore aprovada — release 1.0.0


A estrutura abaixo é a arquitetura aprovada para o Blueprint. Os diretórios desta release foram materializados com arquivos README de orientação. Os documentos especializados continuam sendo produzidos progressivamente; não criar arquivos vazios nem presumir que um documento planejado já esteja concluído.

```text
YVENIST_PROJECT_BLUEPRINT/
│
├── README.md
├── BLUEPRINT_ARCHITECTURE.md
├── BLUEPRINT_PROGRESS.md
├── BLUEPRINT_CHANGELOG.md
├── BLUEPRINT_RELEASE_MANIFEST.md
├── .gitignore
│
├── CLAUDE.md
├── .mcp.json.example
│
├── YVENIST/
│   ├── README.md
│   ├── YVENIST_MASTER_CONTEXT.md
│   ├── ECOSYSTEM_OVERVIEW.md
│   ├── PRODUCT_SURFACES_CATALOG.md
│   └── CURRENT_STATE_BASELINE.md
│
├── .claude/
│   ├── settings.json [artefato futuro; criar após auditoria e aprovação]
│   ├── MCP_CONFIGURATION_POLICY.md
│   ├── CLAUDE_DESKTOP_CODE_INTEGRATION_GUIDE.md
│   ├── AGENT_AND_SKILL_CATALOG.md
│   ├── rules/
│   │   ├── 00_global_principles.md
│   │   ├── documentation_and_sources.md
│   │   ├── decision_and_scope_control.md
│   │   ├── product_and_business.md
│   │   ├── marketplace_operations.md
│   │   ├── ux_content_and_accessibility.md
│   │   ├── brand_and_visual_design.md
│   │   ├── figma_and_design_system.md
│   │   ├── flutter_and_software_architecture.md
│   │   ├── backend_api_and_integrations.md
│   │   ├── data_ai_and_analytics.md
│   │   ├── security_privacy_and_compliance.md
│   │   ├── testing_release_and_operations.md
│   │   └── non_destructive_repository_work.md
│   │
│   ├── skills/
│   │   ├── project-discovery-audit/
│   │   │   └── SKILL.md
│   │   ├── blueprint-documentation/
│   │   │   └── SKILL.md
│   │   ├── evidence-based-research/
│   │   │   └── SKILL.md
│   │   ├── product-and-business-strategy/
│   │   │   └── SKILL.md
│   │   ├── define-and-prioritize-feature/
│   │   │   └── SKILL.md
│   │   ├── service-blueprint-and-domain-model/
│   │   │   └── SKILL.md
│   │   ├── map-user-journey-and-state-machine/
│   │   │   └── SKILL.md
│   │   ├── marketplace-operations-design/
│   │   │   └── SKILL.md
│   │   ├── brand-and-visual-exploration/
│   │   │   └── SKILL.md
│   │   ├── figma-and-design-system-workflow/
│   │   │   └── SKILL.md
│   │   ├── technical-architecture-review/
│   │   │   └── SKILL.md
│   │   ├── implement-vertical-slice/
│   │   │   └── SKILL.md
│   │   ├── test-and-quality-review/
│   │   │   └── SKILL.md
│   │   ├── analytics-and-metrics-design/
│   │   │   └── SKILL.md
│   │   ├── release-and-operations-readiness/
│   │   │   └── SKILL.md
│   │   └── approval-gate-review/
│   │       └── SKILL.md
│   │
│   ├── agents/
│   │   ├── product-strategy-lead.md
│   │   ├── research-analyst.md
│   │   ├── business-service-domain-analyst.md
│   │   ├── marketplace-operations-analyst.md
│   │   ├── brand-ux-design-lead.md
│   │   ├── design-system-specialist.md
│   │   ├── technical-architect-developer.md
│   │   ├── data-analytics-specialist.md
│   │   ├── trust-risk-compliance-analyst.md
│   │   └── qa-release-operations-reviewer.md
│   │
│   └── hooks/
│       ├── README.md
│       └── scripts/
│
├── 00_GOVERNANCE_AND_PROJECT_CONTROL/
│   ├── PRODUCT_CREATION_FRAMEWORK.md
│   ├── DOCUMENT_OWNERSHIP_AND_BOUNDARIES.md
│   ├── DECISION_AUTHORITY_AND_RACI.md
│   ├── ARCHITECTURE_REVIEW_CHECKLIST.md
│   ├── ARCHITECTURE_APPROVAL_RECORD.md
│   ├── PROJECT_CHARTER.md
│   ├── OPERATING_MODEL_AND_RESPONSIBILITIES.md
│   ├── KNOWLEDGE_ARCHITECTURE.md
│   ├── DECISION_LOG.md
│   ├── GLOSSARY.md
│   ├── SOURCE_REGISTER.md
│   ├── ASSUMPTIONS_AND_OPEN_QUESTIONS.md
│   ├── RISK_AND_DEPENDENCY_REGISTER.md
│   ├── APPROVAL_GATES.md
│   ├── CHANGE_CONTROL.md
│   ├── DOCUMENTATION_STANDARDS.md
│   ├── EXISTING_PROJECT_AUDIT_PLAN.md
│   ├── DOCUMENT_MIGRATION_PLAN.md
│   ├── NON_DESTRUCTIVE_MIGRATION_RULES.md
│   ├── EXTERNAL_STANDARDS_AND_REFERENCE_BASELINE.md
│   └── MULTI_SESSION_COLLABORATION/
│       ├── README.md
│       ├── MULTI_SESSION_ORCHESTRATION.md
│       ├── PARALLEL_WORK_PROTOCOL.md
│       ├── WORKSTREAM_REGISTRY.md
│       ├── SESSION_HANDOFF_PROTOCOL.md
│       ├── CROSS_SESSION_COMMUNICATION.md
│       ├── WORKSPACE_OWNERSHIP_RULES.md
│       ├── CONFLICT_RESOLUTION_PROTOCOL.md
│       └── SESSION_STARTUP_CHECKLIST.md
│
├── 01_COMPANY_AND_BUSINESS_STRATEGY/
│   ├── COMPANY_OVERVIEW.md
│   ├── MISSION_VISION_AND_VALUES.md
│   ├── STRATEGIC_POSITIONING.md
│   ├── MARKET_AND_SEGMENT_STRATEGY.md
│   ├── BUSINESS_MODEL.md
│   ├── REVENUE_AND_MONETIZATION.md
│   ├── PRICING_AND_COMMISSION_PRINCIPLES.md
│   ├── FINANCIAL_MODEL_AND_UNIT_ECONOMICS.md
│   ├── PARTNERSHIPS_AND_CHANNELS.md
│   ├── ORGANIZATION_AND_RESPONSIBILITIES.md
│   ├── PEOPLE_AND_ORGANIZATION_OPERATIONS.md
│   ├── SALES_AND_BUSINESS_DEVELOPMENT.md
│   ├── GEOGRAPHIC_EXPANSION_STRATEGY.md
│   └── BUSINESS_KPIS_AND_OBJECTIVES.md
│
├── 02_PRODUCT_STRATEGY_AND_PORTFOLIO/
│   ├── BRAND_FOUNDATION.md
│   ├── PRODUCT_VISION.md
│   ├── ECOSYSTEM_AND_ACTOR_MAP.md
│   ├── VALUE_PROPOSITION.md
│   ├── PRODUCT_PRINCIPLES.md
│   ├── PRODUCT_PORTFOLIO.md
│   ├── MVP_AND_RELEASE_SCOPE.md
│   ├── PRODUCT_ROADMAP.md
│   ├── FEATURE_PRIORITIZATION.md
│   └── PRODUCT_SUCCESS_METRICS.md
│
├── 03_RESEARCH_AND_VALIDATION/
│   ├── MARKET_RESEARCH.md
│   ├── CONSUMER_RESEARCH.md
│   ├── SUPPLIER_AND_PROFESSIONAL_RESEARCH.md
│   ├── DELIVERY_AND_OPERATIONS_RESEARCH.md
│   ├── COMPETITOR_AND_ALTERNATIVE_ANALYSIS.md
│   ├── USER_PERSONAS_AND_SEGMENTS.md
│   ├── CURRENT_USER_JOURNEYS.md
│   ├── HYPOTHESIS_BACKLOG.md
│   ├── RESEARCH_FINDINGS.md
│   └── VALIDATION_REPORT.md
│
├── 04_MARKETPLACE_AND_SERVICE_ARCHITECTURE/
│   ├── MARKETPLACE_SERVICE_MODEL.md
│   ├── SERVICE_BLUEPRINTS.md
│   ├── BUSINESS_RULES.md
│   ├── DOMAIN_MODEL.md
│   ├── CATALOG_AND_TAXONOMY.md
│   ├── REQUEST_QUOTE_BOOKING_LIFECYCLE.md
│   ├── STATE_MACHINES.md
│   ├── ROLES_PERMISSIONS_AND_RESPONSIBILITIES.md
│   ├── COMMERCIAL_POLICIES.md
│   ├── SERVICE_LEVELS_AND_EXPECTATIONS.md
│   └── OPERATIONAL_REQUIREMENTS.md
│
├── 05_PRODUCT_SURFACES_AND_APP_PORTFOLIO/
│   ├── PRODUCT_SURFACES_OVERVIEW.md
│   ├── CONSUMER_APP.md
│   ├── SUPPLIER_PARTNER_APP.md
│   ├── DELIVERY_APP.md
│   ├── ADMIN_BACKOFFICE.md
│   ├── INTERNAL_OPERATIONS_TOOLS.md
│   ├── WEB_AND_PUBLIC_CHANNELS.md
│   └── CROSS_PRODUCT_CAPABILITIES.md
│
├── 06_UX_SERVICE_EXPERIENCE_AND_CONTENT/
│   ├── EXPERIENCE_STRATEGY.md
│   ├── INFORMATION_ARCHITECTURE.md
│   ├── USER_JOURNEYS_AND_FLOWS.md
│   ├── SCREEN_AND_COMPONENT_INVENTORY.md
│   ├── UI_STATE_MATRIX.md
│   ├── INTERACTION_SPECIFICATIONS.md
│   ├── CONTENT_DESIGN.md
│   ├── NOTIFICATIONS_AND_COMMUNICATION_FLOWS.md
│   └── UX_RESEARCH_AND_USABILITY_TESTS.md
│
├── 07_BRAND_AND_EXPERIENCE_SYSTEM/
│   ├── BRAND_STRATEGY.md
│   ├── EXPERIENCE_PRINCIPLES.md
│   ├── VISUAL_IDENTITY_SYSTEM.md
│   ├── VERBAL_IDENTITY_SYSTEM.md
│   ├── ILLUSTRATION_GUIDE.md
│   ├── ICONOGRAPHY_SYSTEM.md
│   ├── GRAPHIC_LANGUAGE.md
│   ├── PHOTOGRAPHY_AND_ART_DIRECTION.md
│   ├── MOTION_AND_INTERACTION_LANGUAGE.md
│   └── BRAND_APPLICATIONS_AND_GOVERNANCE.md
│
├── 08_PRODUCT_DESIGN_SYSTEM/
│   ├── DESIGN_FOUNDATIONS.md
│   ├── DESIGN_TOKENS.md
│   ├── COMPONENT_LIBRARY.md
│   ├── DOMAIN_COMPONENTS.md
│   ├── INTERACTION_PATTERNS.md
│   ├── THEMING_AND_PLATFORM_ADAPTATION.md
│   ├── ACCESSIBILITY_STANDARDS.md
│   ├── FIGMA_LIBRARY_AND_INTEGRATION.md
│   ├── DESIGN_HANDOFF.md
│   └── DESIGN_QA.md
│
├── 09_TECHNICAL_AND_DATA_ARCHITECTURE/
│   ├── EXISTING_TECHNICAL_AUDIT.md
│   ├── SYSTEM_ARCHITECTURE.md
│   ├── FLUTTER_AND_CLIENT_ARCHITECTURE.md
│   ├── BACKEND_AND_SERVICE_ARCHITECTURE.md
│   ├── MULTI_APP_AND_CODE_SHARING.md
│   ├── API_AND_INTEGRATION_CONTRACTS.md
│   ├── DATA_ARCHITECTURE_AND_LIFECYCLE.md
│   ├── IDENTITY_AUTHENTICATION_AND_AUTHORIZATION.md
│   ├── SECURITY_PRIVACY_AND_THREAT_MODEL.md
│   ├── SECURE_SDLC_AND_SECURITY_STANDARDS.md
│   ├── INFRASTRUCTURE_ENVIRONMENTS_AND_DEPLOYMENT.md
│   └── TECHNICAL_DECISION_RECORDS.md
│
├── 10_IMPLEMENTATION_AND_DELIVERY/
│   ├── DEVELOPMENT_STANDARDS.md
│   ├── DELIVERY_WORKFLOW.md
│   ├── VERTICAL_SLICE_METHOD.md
│   ├── FEATURE_SPECIFICATION_AND_IMPLEMENTATION.md
│   ├── REPOSITORY_AND_BRANCHING_STRATEGY.md
│   ├── CODE_REVIEW_STANDARDS.md
│   ├── CI_CD_AND_AUTOMATION.md
│   └── DELIVERY_BACKLOG.md
│
├── 11_MARKETPLACE_OPERATIONS_AND_SUPPLY/
│   ├── OPERATIONS_MODEL.md
│   ├── SUPPLIER_ONBOARDING_AND_VERIFICATION.md
│   ├── SUPPLIER_LIFECYCLE_AND_QUALITY.md
│   ├── CATALOG_LISTING_AND_CONTENT_MODERATION.md
│   ├── AVAILABILITY_CAPACITY_AND_COVERAGE.md
│   ├── PRICING_AND_CATALOG_MAINTENANCE.md
│   ├── SUPPLIER_COMMUNICATION_AND_RESPONSE.md
│   ├── MARKETPLACE_LIQUIDITY_AND_MATCHING.md
│   ├── SERVICE_FULFILLMENT_AND_EVENT_INCIDENT_OPERATIONS.md
│   └── OPERATIONS_PLAYBOOKS.md
│
├── 12_ADMINISTRATION_AND_PLATFORM_OPERATIONS/
│   ├── ADMINISTRATION_MODEL.md
│   ├── ADMIN_BACKOFFICE_REQUIREMENTS.md
│   ├── USER_AND_SUPPLIER_ACCOUNT_OPERATIONS.md
│   ├── MODERATION_AND_ENFORCEMENT.md
│   ├── PLATFORM_CONFIGURATION_AND_CONTENT.md
│   ├── INTERNAL_ROLES_AND_ACCESS_CONTROL.md
│   ├── AUDIT_TRAILS_AND_ADMIN_ACTIONS.md
│   └── INTERNAL_WORKFLOWS_AND_APPROVALS.md
│
├── 13_CUSTOMER_EXPERIENCE_AND_SUPPORT/
│   ├── CUSTOMER_EXPERIENCE_OPERATING_MODEL.md
│   ├── SUPPORT_CHANNELS_AND_CASE_MANAGEMENT.md
│   ├── SERVICE_LEVELS_AND_ESCALATION.md
│   ├── COMPLAINTS_REFUNDS_AND_RESOLUTION.md
│   ├── CUSTOMER_AND_SUPPLIER_KNOWLEDGE_BASE.md
│   ├── COMMUNICATION_TEMPLATES.md
│   └── SUPPORT_QUALITY_METRICS.md
│
├── 14_TRUST_SAFETY_AND_TRANSACTIONS/
│   ├── TRUST_AND_SAFETY_FRAMEWORK.md
│   ├── REPUTATION_RATINGS_AND_REVIEWS.md
│   ├── PAYMENT_AND_SETTLEMENT_FLOWS.md
│   ├── COMMISSIONS_FEES_AND_RECONCILIATION.md
│   ├── CANCELLATIONS_REFUNDS_AND_DISPUTES.md
│   ├── FRAUD_AND_ABUSE_PREVENTION.md
│   ├── TRANSACTIONAL_RESPONSIBILITIES.md
│   └── TRUST_METRICS_AND_CONTROLS.md
│
├── 15_GROWTH_MARKETING_AND_LIFECYCLE/
│   ├── GO_TO_MARKET_STRATEGY.md
│   ├── ACQUISITION_CHANNELS.md
│   ├── ACTIVATION_AND_ONBOARDING.md
│   ├── RETENTION_AND_LIFECYCLE.md
│   ├── REFERRAL_AND_RECOMMENDATION_PROGRAMS.md
│   ├── CAMPAIGNS_AND_PROMOTIONS.md
│   ├── CRM_AND_MARKETING_AUTOMATION.md
│   ├── CONTENT_COMMUNITY_AND_SOCIAL.md
│   ├── BRAND_COMMUNICATION_AND_PR.md
│   └── GROWTH_EXPERIMENTS_AND_METRICS.md
│
├── 16_FINANCE_LEGAL_AND_COMPLIANCE/
│   ├── FINANCIAL_OPERATIONS.md
│   ├── BUDGET_AND_CASH_FLOW.md
│   ├── INVOICING_TAX_AND_ACCOUNTING_REQUIREMENTS.md
│   ├── CONTRACTS_AND_COMMERCIAL_TERMS.md
│   ├── CORPORATE_AND_FOUNDER_GOVERNANCE.md
│   ├── PRIVACY_AND_DATA_PROTECTION_LGPD.md
│   ├── PRIVACY_OPERATIONS_AND_DATA_SUBJECT_RIGHTS.md
│   ├── TERMS_POLICIES_AND_CONSUMER_RIGHTS.md
│   ├── INTELLECTUAL_PROPERTY_AND_BRAND_PROTECTION.md
│   ├── THIRD_PARTY_AND_VENDOR_DUE_DILIGENCE.md
│   └── LEGAL_AND_COMPLIANCE_REVIEW_REGISTER.md
│
├── 17_LOGISTICS_AND_FULFILLMENT/
│   ├── FULFILLMENT_MODEL.md
│   ├── DELIVERY_PARTNER_OPERATIONS.md
│   ├── DELIVERY_ZONES_AND_CAPACITY.md
│   ├── PICKUP_HANDOFF_AND_TRACKING.md
│   ├── DELIVERY_EXCEPTIONS_AND_INCIDENTS.md
│   └── LOGISTICS_METRICS_AND_COSTS.md
│
├── 18_DATA_ANALYTICS_AND_INTELLIGENCE/
│   ├── DATA_GOVERNANCE_AND_OWNERSHIP.md
│   ├── EVENT_TAXONOMY.md
│   ├── KPI_DICTIONARY.md
│   ├── OPERATIONAL_AND_EXECUTIVE_DASHBOARDS.md
│   ├── EXPERIMENTATION_AND_MEASUREMENT.md
│   ├── PERSONALIZATION_AND_DISCOVERY.md
│   ├── RECOMMENDATION_SYSTEM_PRINCIPLES.md
│   ├── SPONSORED_CONTENT_GOVERNANCE.md
│   ├── AI_USAGE_AND_HUMAN_OVERSIGHT.md
│   └── DATA_QUALITY_AND_RETENTION.md
│
├── 19_QUALITY_SECURITY_AND_RELIABILITY/
│   ├── TEST_STRATEGY.md
│   ├── API_CONTRACT_AND_INTEGRATION_TESTS.md
│   ├── END_TO_END_AND_DEVICE_TESTS.md
│   ├── VISUAL_REGRESSION_AND_DESIGN_QA.md
│   ├── ACCESSIBILITY_VALIDATION.md
│   ├── PERFORMANCE_AND_COMPATIBILITY.md
│   ├── SECURITY_TESTING.md
│   ├── MONITORING_LOGGING_AND_ALERTING.md
│   ├── SERVICE_RELIABILITY_AND_OPERATIONS.md
│   ├── INCIDENT_RESPONSE_AND_DISASTER_RECOVERY.md
│   └── BACKUP_AND_BUSINESS_CONTINUITY.md
│
├── 20_LAUNCH_EVOLUTION_AND_GOVERNANCE/
│   ├── RELEASE_AND_ROLLOUT_STRATEGY.md
│   ├── APP_STORE_AND_DISTRIBUTION_CHECKLIST.md
│   ├── LAUNCH_READINESS_REVIEW.md
│   ├── POST_LAUNCH_OPERATING_CADENCE.md
│   ├── PRODUCT_PERFORMANCE_REVIEW.md
│   ├── FEEDBACK_AND_IMPROVEMENT_LOOP.md
│   └── SUNSETTING_AND_DEPRECATION_POLICY.md
│
├── 21_CROSS_CUTTING_SYSTEMS/
│   ├── MARKETPLACE_LIQUIDITY_SYSTEM.md
│   ├── SUPPLIER_OPERATIONS_SYSTEM.md
│   ├── TRUST_AND_TRANSACTION_SYSTEM.md
│   ├── PERSONALIZATION_AND_DISCOVERY_SYSTEM.md
│   ├── CUSTOMER_AND_SUPPLIER_LIFECYCLE_SYSTEM.md
│   └── CROSS_SYSTEM_DEPENDENCIES.md
│
├── 22_TEMPLATES/
│   ├── DECISION_RECORD_TEMPLATE.md
│   ├── FEATURE_BRIEF_TEMPLATE.md
│   ├── FEATURE_SPECIFICATION_TEMPLATE.md
│   ├── RESEARCH_PLAN_TEMPLATE.md
│   ├── RESEARCH_FINDINGS_TEMPLATE.md
│   ├── USER_FLOW_TEMPLATE.md
│   ├── SERVICE_BLUEPRINT_TEMPLATE.md
│   ├── BUSINESS_RULE_TEMPLATE.md
│   ├── TECHNICAL_DECISION_RECORD_TEMPLATE.md
│   ├── TEST_REPORT_TEMPLATE.md
│   ├── OPERATING_PROCEDURE_TEMPLATE.md
│   ├── KPI_DEFINITION_TEMPLATE.md
│   └── APPROVAL_GATE_REVIEW_TEMPLATE.md
│
├── 23_INTEGRATION_AND_HANDOFF/
│   ├── INTEGRATION_README.md
│   ├── TARGET_REPOSITORY_AUDIT_INSTRUCTIONS.md
│   ├── SOURCE_TO_TARGET_DOCUMENT_MAPPING.md
│   ├── CLAUDE_CODE_INSTALLATION_GUIDE.md
│   ├── SETTINGS_AND_HOOKS_COMPATIBILITY.md
│   ├── INTEGRATION_VALIDATION_CHECKLIST.md
│   ├── FINAL_HANDOFF_CHECKLIST.md
│   └── TARGET_REPOSITORY_COMPATIBILITY_CHECKLIST.md
│
├── ASSETS/
│   ├── BRAND/
│   ├── ILLUSTRATIONS/
│   ├── ICONS_2D/
│   ├── ICONS_3D/
│   ├── TYPOGRAPHY/
│   ├── PHOTOGRAPHY/
│   ├── VIDEO_AND_MOTION/
│   ├── DIAGRAMS/
│   └── REFERENCES/
│
└── ARCHIVE/
    ├── README.md
    ├── SUPERSEDED_DOCUMENTS/
    └── HISTORICAL_DECISIONS/
```


### 6.3. Regras específicas para a estrutura do Claude Code

**Distinção entre Blueprint e projeto-alvo:** este pacote é preparado fora do repositório de Rafael. O `CLAUDE.md` incluído nesta release é ativo somente como orientação deste workspace independente do Blueprint; ele não é o `CLAUDE.md` do aplicativo nem deve ser copiado automaticamente para o repositório-alvo. O `CLAUDE.md` do projeto real deverá ser auditado, consolidado e adaptado após a inspeção da raiz do repositório, preservando instruções preexistentes pertinentes. `.claude/settings.json`, regras operacionais, Skills, subagentes, hooks e `.mcp.json` efetivos do projeto-alvo continuam sendo artefatos de integração futura: não há permissões amplas, servidores MCP, hooks ou automações de produção ativados por esta release.


Cada diretório de Skill mostrado na árvore deverá conter seu próprio `SKILL.md`. Os diretórios são nomes propostos para procedimentos reutilizáveis; não devem ser criados vazios nem implementados antes de definir objetivo, gatilho, entradas, saídas, permissões e critérios de conclusão.

- `CLAUDE.md` é o índice de contexto e orientação central; deve permanecer enxuto e apontar para documentação especializada. Não é substituto de controles técnicos.
- `.claude/rules/` contém instruções aplicáveis por domínio ou caminhos.
- Cada Skill fica em uma pasta própria, com `SKILL.md` como arquivo de entrada; materiais auxiliares podem ficar na mesma pasta. Preferir Skills ao formato legado de comandos avulsos.
- `.claude/agents/` contém definições de subagentes com escopo, ferramentas, limites e formato de entrega explícitos.
- Hooks devem executar verificações ou controles determinísticos; os scripts ficam versionados em `.claude/hooks/scripts/` e são chamados pela configuração apropriada.
- `.claude/settings.json` contém configuração compartilhada e revisada do projeto. Configurações locais, como `settings.local.json`, devem ser tratadas como locais e excluídas do controle de versão quando contiverem preferências ou permissões específicas do computador.
- `.mcp.json.example` documenta a estrutura de conexão MCP sem credenciais. A configuração efetiva só será criada após selecionar servidores, validar permissões e definir como os segredos serão fornecidos por variáveis de ambiente ou mecanismo seguro.
- No Claude Code local, o Desktop e a CLI compartilham os arquivos de projeto e usuário documentados pela Anthropic. Configurações MCP do aplicativo Claude Desktop (chat) não devem ser presumidas como disponíveis na aba Code: para o Code, verificar `.mcp.json` do projeto ou a configuração de usuário `~/.claude.json`. O `.claude/settings.json` é compartilhável; `.claude/settings.local.json` é local por máquina e não deve ser incluído no pacote versionado. Confirmar o comportamento na documentação da versão instalada.
- Não criar `settings.json` com permissões amplas por padrão. Começar com configuração mínima, revisar `allow`/`ask`/`deny`, testar em cópia ou branch e registrar a aprovação dos responsáveis. O modo de permissão escolhido no Desktop não substitui a revisão das regras de projeto.
- Cada definição de subagente deverá usar o formato de frontmatter exigido pela versão instalada, declarar propósito, ferramentas autorizadas, limites, contexto e formato de entrega. Não presumir que todos os agentes sugeridos precisam ser ativados.
- Cada Skill deverá ter `SKILL.md` com descrição objetiva, gatilhos, entradas, procedimento, saídas, restrições e critérios de conclusão. Só incluir Skills com procedimento reutilizável; não transformar cada tarefa simples em uma Skill.
- Hooks deverão ser poucos, determinísticos, versionados, revisados e testados. Não usar hooks como única barreira de segurança nem executar scripts recebidos de fontes não confiáveis.
- Não presumir que um servidor MCP, hook ou permissão é compatível com qualquer versão: validar contra a versão instalada do Claude Code no momento da integração.
- Para duas sessões Desktop Code no mesmo computador, seguir `MULTI_SESSION_COLLABORATION/`: verificar versão e alcance de mensagens, nomear sessões, ativar `Worktree` antes de cada início de sessão de escrita, verificar paths/branches efetivos, manter um coordenador e um único escritor por caminho. Se mensagens não estiverem disponíveis, usar fallback manual. Se não houver Git ou isolamento verificável, serializar a escrita.

## 7. Como evitar sobreposição entre áreas

A árvore é ampla, mas não significa que toda informação será repetida em vários documentos.

- **Estratégia empresarial** registra como a empresa pretende criar, entregar e capturar valor.
- **Estratégia de produto** registra quais produtos e capacidades serão priorizados e para quem.
- **Arquitetura do marketplace** registra entidades, regras e ciclo das operações entre participantes.
- **Portfólio de superfícies** identifica quais interfaces e ferramentas existem ou poderão existir; não aprova automaticamente sua construção.
- **UX e experiência** descreve como pessoas executam tarefas nas diferentes superfícies.
- **Marca e Design System** definem linguagem e padrões de expressão, sem reescrever regras de negócio.
- **Arquitetura técnica** descreve como capacidades serão implementadas e integradas, com base em auditoria.
- **Operações** descreve como a empresa executa, monitora e resolve o serviço no cotidiano.
- **Administração** descreve ferramentas, permissões e processos internos da plataforma.
- **Suporte** descreve relacionamento, atendimento e resolução de casos.
- **Trust & Transactions** define controles e fluxos de transação, risco e confiança; documentos financeiros e jurídicos registram obrigações e validações específicas.
- **Dados e inteligência** define eventos, indicadores, governança e uso responsável de personalização; os sistemas consumidores referenciam esse documento.
- **YVENIST/** mantém o contexto consolidado e o baseline factual da empresa. Não se torna uma segunda pasta de especificações nem reescreve decisões, regras ou políticas registradas nos domínios especializados. O conteúdo inicial deve ser tratado como rascunho contextual até reconciliado com as fontes atuais do projeto.
- **Sistemas transversais** consolidam visões e dependências de várias áreas. Não duplicam a fonte de verdade de cada domínio.

Quando dois documentos parecerem cobrir o mesmo assunto, o Claude deverá definir um documento proprietário e fazer os demais referenciarem-no.

O documento `00_GOVERNANCE_AND_PROJECT_CONTROL/DOCUMENT_OWNERSHIP_AND_BOUNDARIES.md` será a matriz normativa dessa separação. Ele identifica o documento proprietário por assunto, os documentos consumidores, os limites de escopo e a regra para resolver conflitos. Se houver conflito não resolvido entre fontes, o Claude deverá interromper a consolidação daquela decisão, registrar a divergência e solicitar validação humana — não escolher silenciosamente a versão que parecer mais conveniente.

## 8. Governança de responsabilidades e autoridade de decisão

A matriz `00_GOVERNANCE_AND_PROJECT_CONTROL/DECISION_AUTHORITY_AND_RACI.md` define responsabilidades por PAPEL, não presume a distribuição efetiva entre Keven e Rafael. Os nomes dos responsáveis e seus poderes de aprovação deverão ser confirmados pelos próprios envolvidos e, quando aplicável, formalizados por instrumentos societários ou profissionais competentes.

Regras obrigatórias:

1. Toda decisão relevante deverá ter um responsável humano identificado como autoridade final (`A` / Accountable).
2. Claude poderá pesquisar, analisar, redigir, implementar e verificar dentro do escopo autorizado; Claude nunca será autoridade final (`A`) nem poderá aprovar em nome dos fundadores.
3. Se o responsável humano não estiver identificado, a decisão fica `UNASSIGNED` e não poderá ser tratada como aprovada.
4. Decisões empresariais, comerciais, financeiras, societárias, jurídicas, de privacidade, segurança, identidade e arquitetura exigem a revisão humana indicada na matriz.
5. Questões sujeitas a lei, contabilidade, tributação, pagamentos regulados ou segurança especializada devem ser validadas por profissional qualificado antes de serem tratadas como orientação definitiva.
6. Em caso de divergência entre responsáveis, registrar posições, impacto e opções; não presumir voto de desempate nem autoridade unilateral. A decisão fica bloqueada até resolução pelos meios acordados.
7. Permissões técnicas do Claude não equivalem a autoridade de negócio. A possibilidade de executar uma ação não significa autorização para decidir que ela deve ser executada.

## 9. Propriedade documental, limites e prevenção de duplicidades

A propriedade de conteúdo é definida por assunto e não pela equipe que primeiro escreveu o arquivo. Cada requisito, regra, política, definição ou especificação deve ter uma fonte de verdade designada na matriz de propriedade documental. Documentos de visão geral, templates, dashboards e sistemas transversais podem resumir ou referenciar, mas não manter cópias concorrentes.

Quando um mesmo tema atravessar negócio, operação, jurídico e tecnologia, separar a decisão normativa, o procedimento operacional e a implementação técnica. Exemplo: a política de reembolso é definida no domínio transacional/comercial; o fluxo de atendimento é definido no domínio de suporte; a execução de estorno é especificada tecnicamente no contrato/integração de pagamento. Cada documento deve linkar os outros.

## 10. Modelo de documento obrigatório

Documentos relevantes deverão seguir um cabeçalho comum, adaptado quando necessário:

- título e identificador;
- propósito e escopo;
- status de decisão, status de execução e classificação de escopo;
- responsável pela manutenção;
- fontes e evidências;
- contexto e situação atual verificada;
- decisões e regras;
- propostas e questões em aberto;
- dependências, riscos e impactos;
- critérios de aceite;
- documentos relacionados;
- histórico de alterações.

O Claude não deverá preencher lacunas com suposições silenciosas. Deve registrar `UNVERIFIED`, `ASSUMPTION` ou `TO_VALIDATE`, conforme aplicável.

## 11. Portões de aprovação

Os portões são revisões de prontidão, não uma sequência rígida que proíbe toda iteração.

- **Gate 0 — Contexto e governança:** projeto existente compreendido, fontes inventariadas, papéis e processo definidos.
- **Gate 1 — Negócio e produto:** estratégia, públicos, proposta de valor, modelo e escopo inicial revisados.
- **Gate 2 — Serviço e operação:** jornadas operacionais, regras, responsabilidades, estados e exceções especificados.
- **Gate 3 — Experiência:** arquitetura de informação, jornadas, conteúdo, protótipos e testes com usuários avaliados.
- **Gate 4 — Marca e sistema visual:** direção de marca, identidade, linguagem, tokens e componentes revisados.
- **Gate 5 — Arquitetura técnica:** auditoria, arquitetura, dados, integrações, segurança e plano de implementação revisados.
- **Gate 6 — Prontidão de lançamento:** fluxos prioritários operacionais, qualidade, atendimento, observabilidade, políticas e distribuição avaliados.

Cada gate deverá apresentar evidências, pendências, riscos aceitos, decisões solicitadas e recomendação. O Claude não aprova sozinho decisões reservadas aos responsáveis humanos.

## 12. Diretrizes de priorização e eficiência

Para entregar valor com eficiência, o Claude deverá:

1. primeiro identificar o que já existe e pode ser reaproveitado;
2. separar MVP, pós-MVP e visão futura;
3. priorizar riscos e dependências que podem bloquear o fluxo de valor;
4. trabalhar em entregas pequenas, completas e demonstráveis;
5. criar documentos detalhados somente quando forem necessários para decisão, execução, conformidade ou manutenção;
6. automatizar tarefas repetitivas e verificações determinísticas, após revisar seus efeitos;
7. evitar múltiplas ferramentas para a mesma finalidade sem benefício comprovado;
8. apresentar alternativas com custo, risco, dependências e recomendação técnica, sem ocultar incertezas;
9. manter backlog priorizado e critérios de pronto;
10. atualizar o progresso e a documentação ao concluir cada unidade de trabalho.

Rapidez não significa gerar a maior quantidade de código ou documentos. Significa reduzir retrabalho, esclarecer dependências e entregar primeiro os fluxos de maior valor com qualidade suficiente.

## 13. Coberturas adicionais incorporadas na versão 0.3 e preservadas na 0.4

A versão 0.3 acrescenta explicitamente domínios que podem ficar escondidos em estruturas centradas apenas em produto e tecnologia:

1. **Pessoas e organização:** papéis, capacidades, contratação, onboarding, treinamento, continuidade de conhecimento e responsabilidades — sem presumir tamanho atual da equipe.
2. **Vendas e desenvolvimento comercial:** prospecção e aquisição de fornecedores, pipeline B2B, negociação, CRM comercial e gestão de canais.
3. **Prestação do serviço e incidentes no evento:** atrasos, ausência de prestador, serviço incompleto, alterações de última hora, falhas de entrega, incidentes presenciais, evidências, comunicação e resolução.
4. **Governança societária e dos fundadores:** estrutura, direitos, obrigações, propriedade intelectual, aprovações e registros; tudo sujeito a confirmação e assessoria jurídica.
5. **Operação de privacidade e direitos dos titulares:** atendimento a solicitações, retenção, eliminação, correção, registro de tratamento, incidentes e interação com operadores, conforme avaliação jurídica e da LGPD.
6. **Desenvolvimento seguro:** práticas de segurança no ciclo de software, revisão de dependências, threat modeling, gestão de vulnerabilidades e verificações para aplicativos móveis e APIs.
7. **Confiabilidade de serviços:** indicadores de confiabilidade, objetivos de serviço, monitoramento, alertas, incidentes, recuperação e aprendizado operacional.

Esses documentos não significam que a Yvenist precise contratar uma grande equipe ou implementar todos os processos imediatamente. O Claude deverá propor níveis proporcionais à fase, ao risco, ao volume operacional e ao orçamento.

## 14. Integração futura com o projeto do Rafael

A integração será uma etapa própria e só começará após revisão do Blueprint.

O Claude deverá:

1. verificar a raiz correta do repositório, branch, remotos e estado de trabalho;
2. inventariar código, documentos, configurações, Figma e integrações acessíveis;
3. classificar cada fonte por autoridade, atualidade e confiabilidade;
4. mapear documentos existentes para os novos domínios;
5. apontar conflitos, duplicidades, lacunas e decisões divergentes;
6. elaborar um plano de migração e uma proposta de instalação do Claude Code;
7. identificar compatibilidade das regras, Skills, agentes, hooks e configurações com a versão instalada;
8. solicitar aprovação antes de mover, renomear, substituir, apagar ou alterar arquivos existentes;
9. integrar em branch e commits revisáveis, conforme processo aprovado;
10. validar links, referências, configurações, testes e funcionamento após integração.

Consultar `00_GOVERNANCE_AND_PROJECT_CONTROL/SOURCE_REGISTER.md` e `23_INTEGRATION_AND_HANDOFF/PROJECT_SOURCE_ACQUISITION_PROTOCOL.md` para as fontes declaradas do projeto. Não presumir acesso ao GitHub, Figma, backend, serviços externos ou credenciais. A ausência de acesso deverá ser registrada como bloqueio ou dependência, nunca contornada por invenção.

## 15. Ferramentas: princípio de seleção

A arquitetura não impõe a compra ou adoção imediata de todas as ferramentas citadas ao longo do planejamento.

Para cada necessidade, o Claude deverá registrar:

- responsabilidade atendida;
- ferramenta principal existente ou proposta;
- alternativa gratuita ou já disponível, quando relevante;
- custo e limitações conhecidos;
- integração necessária;
- dados e permissões envolvidos;
- razão para adoção;
- momento em que a ferramenta passa a ser necessária.

GitHub, Claude Code, Figma e Flutter são elementos já associados ao contexto do projeto. Ferramentas complementares — por exemplo, documentação de APIs, testes, analytics, automação, design vetorial, 3D ou motion — deverão ser avaliadas conforme necessidade real e compatibilidade.

## 16. O que ainda precisa ser decidido

Esta versão amplia o escopo, mas não transforma todas as possibilidades em decisões aprovadas. Permanecem para validação:

- forma jurídica, estrutura societária e responsabilidades formais da empresa;
- modelo financeiro, comissões, cobrança, pagamentos e repasses;
- escopo e cronograma de cada aplicativo e ferramenta interna;
- necessidade e momento de desenvolver backoffice próprio;
- logística própria, terceirizada ou híbrida;
- provedores de pagamento, identidade, notificações, mapas e analytics;
- política de moderação, reputação, cancelamentos e disputas;
- arquitetura de dados e uso de modelos de recomendação;
- regiões e categorias iniciais de lançamento;
- requisitos jurídicos, fiscais, contábeis e regulatórios aplicáveis.

Temas jurídicos, contábeis, fiscais, financeiros regulados e de segurança deverão ser preparados pelo Claude como material de análise e verificação, mas submetidos aos profissionais competentes antes de serem tratados como orientação definitiva.

## 17. Resultado da aprovação da arquitetura — release 1.0.0

**Decisão:** `APPROVED_AS_WORKING_ARCHITECTURE`  
**Versão aprovada como baseline:** `1.0.0`  
**Data da aprovação humana:** `17/11/2026`  
**Registro:** `00_GOVERNANCE_AND_PROJECT_CONTROL/ARCHITECTURE_APPROVAL_RECORD.md`

A arquitetura foi aprovada explicitamente pelo responsável solicitante nesta conversa, tendo a versão 0.4 como base. Esta release 1.0.0 consolida a aprovação, materializa a árvore de diretórios e atualiza os registros de controle, sem alterar o escopo estrutural aprovado.

A aprovação cobre:

- cobertura do negócio, da operação e dos produtos digitais da Yvenist;
- os 24 domínios numerados, o núcleo de contexto `YVENIST/`, a área `.claude/`, `ASSETS/` e `ARCHIVE/`;
- princípios de propriedade documental, prevenção de duplicidades e rastreabilidade;
- o modelo de autoridade humana e RACI como estrutura, mantendo nomes e alçadas pessoais `UNASSIGNED` até confirmação;
- a arquitetura operacional pretendida para Claude Code/Desktop Code, Skills, subagentes, hooks e MCP, sujeita a validação técnica no ambiente real;
- integração futura não destrutiva com o repositório existente;
- produção progressiva de documentos, sem criação indiscriminada de arquivos vazios.

### Limites explícitos da aprovação

A aprovação da arquitetura **não** significa que:

- todos os documentos de domínio estejam escritos ou aprovados;
- a estratégia, o modelo financeiro, as políticas, o MVP ou as funcionalidades estejam decididos;
- os nomes, papéis societários, poderes ou alçadas de Keven e Rafael estejam formalmente definidos;
- o código, backend, Figma, APIs ou repositório de Rafael tenham sido auditados nesta etapa;
- as configurações, Skills, agentes, hooks ou MCP estejam instalados ou testados;
- exista conformidade legal, fiscal, de privacidade ou certificação de segurança.

Esses itens continuam sujeitos às fases, gates, evidências e aprovações correspondentes. A arquitetura está aprovada como **estrutura de trabalho**, não como aprovação antecipada de todas as decisões e entregas futuras.

Não instalar nem mesclar este pacote no repositório de Rafael sem executar o processo definido em `23_INTEGRATION_AND_HANDOFF/`.


## 18. Base externa de referência consultada e revisada para a versão 0.4 (referências preservadas no release 1.0.0)

As referências abaixo foram conferidas em 17/11/2026. São fontes de orientação e não equivalem a adoção formal, certificação, parecer jurídico ou prova de conformidade da Yvenist. O documento `00_GOVERNANCE_AND_PROJECT_CONTROL/EXTERNAL_STANDARDS_AND_REFERENCE_BASELINE.md` contém o registro, estado, aplicabilidade e regras de atualização.

### Claude Code e Desktop Code

- Claude Code — Settings files and precedence: https://code.claude.com/docs/en/settings
- Claude Code — Desktop app: https://code.claude.com/docs/pt/desktop
- Anthropic Help Center — FAQ do Claude Code: https://support.claude.com/pt/articles/14554922-faq-do-claude-code

Aplicação: distinguir configurações compartilhadas do projeto, configurações locais por máquina, instruções CLAUDE.md, Skills, subagentes, hooks e MCP. O Desktop Code e CLI compartilham configurações de Claude Code; servidores MCP do aplicativo de chat Claude Desktop são distintos dos configurados para Claude Code. Validar o comportamento com a versão instalada.

### Desenvolvimento seguro, aplicativos móveis e APIs

- NIST SP 800-218 (SSDF) v1.1 — versão final: https://csrc.nist.gov/pubs/sp/800/218/final
- NIST SP 800-218 Rev. 1 / SSDF v1.2 — Initial Public Draft de 17/12/2025; prazo de comentários encerrado em 30/01/2026; não tratar como versão final enquanto o NIST não publicar status final: https://csrc.nist.gov/pubs/sp/800/218/r1/ipd
- OWASP ASVS 5.0.0 — versão estável publicada em 30/05/2025: https://asvs.owasp.org/
- OWASP MASVS: https://mas.owasp.org/MASVS/ (v2 em desenvolvimento; v1.5.0 identificada como versão v1 mais recente no projeto)
- OWASP MASTG v2.0.0: https://mas.owasp.org/MASTG/
- OWASP MASWE v1.0.0: https://mas.owasp.org/MASWE/
- OWASP ASVS 5.0.0: https://asvs.owasp.org/
- OWASP Web Application Top 10:2025: https://owasp.org/www-project-top-ten/
- OWASP API Security Top 10 2023: https://owasp.org/API-Security/editions/2023/en/0x11-t10/

Aplicação: escolher controles proporcionais ao risco e à arquitetura efetiva. MASVS/MASTG/MASWE apoiam a segurança móvel (acompanhar a transição entre MASVS v1 e v2, MASTG v2.0.0 e MASWE v1.0.0); ASVS e OWASP Top 10:2025 são referências para aplicações web e serviços; o catálogo OWASP API Security Top 10 2023 complementa a análise de APIs. Não declarar conformidade apenas por citar esses padrões.

### Privacidade e proteção de dados no Brasil

- ANPD — Guia orientativo para definições dos agentes de tratamento e do encarregado: https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-para-definicoes-dos-agentes-de-tratamento-de-dados-pessoais-e-do-encarregado
- ANPD — Direitos dos titulares: https://www.gov.br/anpd/pt-br/assuntos/titular-de-dados/direito-dos-titulares

Aplicação: mapear papéis reais de controlador e operador, processos para atender direitos dos titulares, bases legais, retenção e incidentes. O enquadramento depende das atividades reais e exige revisão jurídica especializada.

### Confiabilidade e operação de serviços

- Google SRE Books and Resources: https://sre.google/books/
- Google SRE resources: https://sre.google/resources/book-update/

Aplicação: orientar SLI, SLO, alertas, incidentes, recuperação, postmortems e continuidade de serviço em nível proporcional ao porte e risco.

### Regra de atualização

1. Registrar título, organização mantenedora, versão/estado (final, draft, estável, experimental), data de publicação ou atualização, URL, data de consulta e áreas afetadas.
2. Revalidar referências externas antes de transformar uma recomendação em requisito.
3. Dar preferência a fontes primárias e oficiais.
4. Manter drafts e rascunhos identificados como tais; não promovê-los a padrão final.
5. Distinguir referência, requisito interno adotado, obrigação legal e certificação formal.
6. Se uma fonte mudar, registrar a alteração no changelog e avaliar impacto nos documentos que a utilizam.

---

**Histórico resumido:** v0.1 — primeira estrutura; v0.2 — ampliação para negócio e operação; v0.3 — núcleo `YVENIST/` e domínios operacionais; v0.4 — propriedade documental, autoridade RACI, integração Claude Desktop Code, base técnica atualizada e checklist; v1.0.0 — aprovação humana da arquitetura, registro formal e materialização da árvore.


## 19. Addendum de colaboração multi-sessão — proposta 0.3

Em 17/11/2026 foi revisado o protocolo para duas sessões independentes Claude Code na aba Code do mesmo computador. A documentação oficial atual documenta cross-session messaging: sessões compatíveis podem listar, consultar e enviar mensagens de texto a outras sessões alcançáveis. Requisitos publicados: Claude Code `v2.1.234+` no Windows nativo e `v2.1.224+` em macOS/Linux/WSL 2; `@menção` de sessão requer `v2.1.232+`.

O addendum acrescenta coordenação, workstreams, ownership de arquivos, mensagens nativas como canal auxiliar, handoffs versionados, isolamento Git e resolução de conflitos. Mensagens não transferem arquivos/histórico, não aprovam permissões nem substituem registro, Git ou autorização humana. O fallback é brief transferido pelo operador.

No Claude Desktop, `Worktree` precisa ser ativado antes de iniciar cada sessão que deverá ter cópia isolada; por padrão está desativado. Confirmar caminho, branch, versão e alcance de cada sessão antes da escrita paralela. Agent Teams é um recurso distinto, não utilizado neste fluxo Desktop.

O addendum não altera a decisão `BP-ARCH-001` nem reclassifica a arquitetura-base `1.0.0` aprovada. Permanece `PROPOSAL / PILOT_REQUIRED` até teste real das duas sessões e aprovação humana. Consulte `MULTI_SESSION_COLLABORATION/SESSION_STARTUP_CHECKLIST.md` e `MULTI_SESSION_COLLABORATION/MULTI_SESSION_PILOT_TEST_PLAN.md`.

Fontes oficiais verificadas em 17/11/2026:
- https://code.claude.com/docs/pt/cross-session-messaging
- https://code.claude.com/docs/pt/desktop
- https://git-scm.com/docs/git-worktree

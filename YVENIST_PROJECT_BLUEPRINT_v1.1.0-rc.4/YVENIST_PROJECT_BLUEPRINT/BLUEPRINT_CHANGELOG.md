# BLUEPRINT CHANGELOG

## Main update — commercial model and transaction lifecycle (2026-11-18)

### Added and expanded directly in main
- Expanded the commercial and operating model to proposal v0.2, including commission base, per-supplier commission, paid placements, future consumer subscription, supplier onboarding, supplier-specific sub-orders, payment/split options, payout, cancellation, refunds, disputes and specialist launch gates.
- Added transaction domain and state machine for EventRequest, SupplierSubOrder, CheckoutOrder, PaymentGroup, PaymentIntent, ContractRecord, CommissionEntry, PayoutRecord, RefundRecord and DisputeCase.
- Added the joint approval sheet for remaining commission, payment, SLA, cancellation, completion and payout decisions.
- Updated owner register, decision record, customer flow document, progress, release manifest and integration index.

### Key technical conclusion
- Maintain one consumer checkout experience where possible, but support either a PSP-native multi-receiver split or separate correlated PaymentIntents for supplier sub-orders. Do not assume a provider's 1:1 split product supports a multi-supplier event.
- Supplier availability confirmation, payment success and final contract are separate states.
- No new commission percentage or cancellation penalty was approved in this update.

### Not approved / not performed
- No payment provider selected.
- No live payment, split, wallet, escrow or payout system activated.
- No legal/contractual terms approved for production.
- No target app source code changed.
- No Figma frames edited.
- No ZIP release or merge from a feature branch; documentation was committed directly to main.

---

# BLUEPRINT CHANGELOG

## Working-branch update — joint owner decisions and product-flow clarification (2026-11-18)

### Confirmed by both owners
- Primary brand color changed to #FF5637, superseding the previous #FF6B00 direction.
- Three-screen hybrid direction and Plus Jakarta Sans confirmed.
- Material Icons/current mapping approved, with future revision permitted.
- New app-icon explorations requested; no existing icon is selected.
- Foundation tokens accepted as baseline for iterative refinement.
- Listing-card rating defined as customer rating.
- Motion/performance evaluation requested as a design approval gate.
- Party Maker rules PM-20–PM-26 clarified; supplier-specific sub-orders/notifications and supplier availability confirmation replace consumer quote acceptance.
- Immediate purchase cart/checkout is distinct from Party Maker; V1/V2 confirmation semantics clarified.
- Payments/contracting and previously listed functional capabilities retained in intended MVP scope.
- Product Creation Framework v0.1 approved as official working basis.
- Strategic/commercial decisions require both owners; technical/operational decisions go through designated accountable owners.

### Added/updated
- Dated owner decision record and refreshed owner confirmation register.
- Party Maker and immediate checkout flow specification.
- Proposal for commission, paid placements, cancellations/refunds, supplier fulfilment and disputes; still awaiting joint commercial approval and specialist review.
- Visual asset and motion production pipeline; Rive, Lottie and Blender toolchain recommendations with an Android device quality gate.
- Baseline, progress, release manifest, audit report and integration index updated.

### Not approved by this update
- Specific commission rate, cancellation penalties, refund windows, supplier SLAs, payment-provider choice, consumer membership benefits or any final legal/contractual text.
- Actual Figma edits, target-app code changes, local environment changes, package release or merge to main.

---

# BLUEPRINT CHANGELOG

## v1.1.0-rc.3 — revisão técnica e teste do addendum multi-sessão (17/11/2026)

### Corrigido
- Padronizada a versão do addendum multi-sessão em `0.2` nos documentos e registros.
- Removida a recomendação de depender de comunicação nativa entre sessões; a documentação atual do Claude Desktop descreve sessões independentes e worktrees, mas não documenta um canal geral de chat sessão-a-sessão.
- Definida transferência de brief pelo operador humano, handoff commitado na branch do worker e revisão/integração pela sessão coordenadora.
- Esclarecido que alterações não commitadas em um worktree não aparecem automaticamente no outro; branches/commits e handoffs são o transporte durável.
- Diferenciado o uso de duas sessões independentes do recurso Agent Teams, não disponível na interface Desktop conforme a documentação consultada.

### Testes executados
- ZIP CRC/integridade: `PASS`.
- Estrutura: 24 diretórios numerados, todos com README; sem caminhos de arquivo duplicados.
- `.mcp.json.example`: JSON válido e sem servidores ativos/credenciais.
- Simulação Git em repositório temporário: dois worktrees isolados, commits em branches distintas e integração de arquivos não conflitantes: `PASS`.
- Simulação de duas branches alterando o mesmo arquivo: Git detectou conflito: `PASS`.
- Documentos Skill/Agent: pastas existentes são placeholders/documentação de planejamento; nenhum `SKILL.md` ou agente executável foi declarado como instalado.

### Pendências de ambiente
- Piloto em duas sessões reais da interface Claude Desktop Code: `PENDING`.
- Acesso autenticado e auditoria do repositório GitHub: `PENDING`. A tentativa de acesso público sem autenticação nesta revisão retornou 404; isso não permite concluir se o repositório é privado, inexistente ou inacessível à conta dos responsáveis.
- Acesso autenticado ao Figma e histórico de versões: `PENDING`; o navegador desta revisão não conseguiu abrir o arquivo, não sendo possível inferir permissões da conta dos responsáveis.

### Resultado
O pacote `1.1.0-rc.3` está pronto para piloto controlado, não para ativação automática. A arquitetura-base `1.0.0` permanece aprovada; o addendum multi-sessão `0.2` continua `PROPOSAL` até o piloto real e aprovação humana.

---

## v1.1.0-rc.2 — registro das fontes oficiais e aquisição controlada (17/11/2026)

### Adicionado
- `00_GOVERNANCE_AND_PROJECT_CONTROL/SOURCE_REGISTER.md`: registra GitHub `https://github.com/KevenSanchesG/Yvenist` e Figma `Yvenist_v0` como fontes declaradas pelos responsáveis, com domínio de autoridade, limites e estado de acesso pendente.
- `23_INTEGRATION_AND_HANDOFF/PROJECT_SOURCE_ACQUISITION_PROTOCOL.md`: define verificação read-only do repositório, inspeção atual/histórica do Figma, reconciliação de fontes, evidências exigidas e ações proibidas sem autorização.
- URLs oficiais declaradas acrescentadas ao `YVENIST/YVENIST_MASTER_CONTEXT.md`, `CLAUDE.md`, arquitetura, integração e governança.

### Corrigido
- Comunicação direta entre sessões passou a `CAPABILITY_TO_VERIFY`; não é assumida como disponível. Workstream registry, handoffs e Git são mecanismos duráveis.
- Orientação sobre Git worktrees atualizada conforme documentação atual do Claude Desktop: sessões paralelas em repositórios Git recebem cópias isoladas/worktrees; a versão instalada, caminho e branch efetivos devem ser verificados.
- A integração reconhece o repositório GitHub já declarado: não inicializar um novo Git ou substituir remotes automaticamente; inspecionar primeiro e solicitar autorização para clone/integração quando necessário.

### Pendências explícitas
- Acesso ao GitHub ainda não auditado.
- Acesso ao Figma e permissões ainda não auditados.
- Histórico de versões Figma ainda não inventariado.
- Addendum multi-sessão permanece `PROPOSAL` até teste-piloto e aprovação humana.

### Referências oficiais consultadas
- Claude Code Desktop: https://code.claude.com/docs/pt/desktop
- Figma version history API: https://developers.figma.com/docs/rest-api/version-history-endpoints/
- Figma file API: https://developers.figma.com/docs/rest-api/file-endpoints/

---

# BLUEPRINT CHANGELOG

## Addendum multi-sessão 0.2 — revisão de comunicação e handoff (17/11/2026)

### Revisado
- Atualizados todos os documentos operacionais para a versão 0.2.
- Definido que não se deve depender de mensagens nativas entre sessões locais, pois o recurso não está documentado na referência atual do Claude Desktop.
- Estabelecida transferência do brief pelo operador humano, handoff commitado na branch da Session B e revisão pela Session A.
- Esclarecido que o registro central da Session A não é automaticamente visível no worktree da Session B.
- Diferenciado o modelo de duas sessões independentes do recurso Agent Teams.
- Criado plano de piloto de baixo risco e relatório de revisão/testes.

### Estado
- `READY_FOR_CONTROLLED_PILOT` — não aprovado para ativação operacional até o piloto real no Claude Desktop e aceite humano.

## Addendum multi-sessão 0.1 — proposta (17/11/2026)

### Adicionado
- Criada a área `00_GOVERNANCE_AND_PROJECT_CONTROL/MULTI_SESSION_COLLABORATION/` para coordenar duas sessões Claude Code na aba Code do mesmo Claude Desktop.
- Definidos os papéis operacionais Session A — Coordinator e Session B — Specialist/Worker, sem hierarquia de autoridade humana.
- Criados protocolos de paralelismo, registry de workstreams, handoff, mensagens entre sessões, ownership de arquivos, resolução de conflitos e checklist de inicialização.
- Atualizado o guia de integração Claude Desktop Code para o cenário de duas sessões no mesmo computador.
- Atualizado o catálogo para diferenciar papéis de sessão de subagentes.

### Limites
- O addendum é `PROPOSAL` e não altera a aprovação da arquitetura-base 1.0.0.
- [SUPERSEDED IN 1.1.0-rc.2] Orientação preliminar dizia que Worktree precisava ser ativado manualmente; foi atualizada após reconsulta da documentação atual do Claude Desktop.
- Sem Git/worktree ou cópia independente verificável, a escrita paralela deve ser serializada.
- A comunicação entre sessões não sincroniza arquivos/branches nem substitui registry, handoffs, Git ou aprovação humana.
- Nenhuma integração MCP/serviço externo é presumida como instalada.

### Referências técnicas verificadas
- Claude Code Desktop: https://code.claude.com/docs/pt/desktop
- Claude Code settings: https://code.claude.com/docs/en/settings

---

## v1.0.0 — arquitetura-base aprovada (17/11/2026)

### Aprovado
- Arquitetura v0.4 explicitamente aprovada como estrutura de trabalho do Blueprint.
- Escopo integral de empresa, marketplace, operação e ecossistema de produtos mantido.
- Propriedade documental, limites, princípios de não duplicidade e integração não destrutiva aceitos como regras estruturais.
- Matriz RACI aceita como modelo por papel; nomes e alçadas individuais permanecem não atribuídos até confirmação humana.

### Consolidado
- Criado `00_GOVERNANCE_AND_PROJECT_CONTROL/ARCHITECTURE_APPROVAL_RECORD.md` com a decisão `BP-ARCH-001`.
- `BLUEPRINT_ARCHITECTURE.md`, `README.md`, `BLUEPRINT_PROGRESS.md` e `ARCHITECTURE_REVIEW_CHECKLIST.md` atualizados para refletir a aprovação.
- Criado `CLAUDE.md` restrito ao workspace independente do Blueprint; não deve ser copiado automaticamente para o repositório-alvo.
- Materializada a árvore de diretórios aprovada, com READMEs de orientação nos diretórios cujos documentos especializados ainda não foram produzidos.
- Mantido `.mcp.json.example` sem servidores ativos e sem credenciais.

### Limites preservados
- A aprovação é estrutural; não aprova documentos de domínio ainda não escritos, decisões comerciais, alçadas pessoais, conformidade legal, configurações técnicas ou integração com o repositório do Rafael.
- O `PRODUCT_CREATION_FRAMEWORK.md` permanece `NOT_STARTED` e é a próxima entrega.

---

## v0.4 — revisão de arquitetura e integração (17/11/2026)

### Adicionado
- `DOCUMENT_OWNERSHIP_AND_BOUNDARIES.md`: matriz de fonte de verdade, propriedade documental, limites e resolução de conflitos; ampliada para preço, comissões, finanças, KPIs, superfícies, organização, notificações e backoffice.
- `DECISION_AUTHORITY_AND_RACI.md`: papéis candidatos, matriz RACI, autorizações explícitas e tratamento de divergências sem presumir poderes de Keven ou Rafael.
- `ARCHITECTURE_REVIEW_CHECKLIST.md`: checklist para cobertura, duplicidade, autoridade, Claude Code, referências e integração.
- `CLAUDE_DESKTOP_CODE_INTEGRATION_GUIDE.md`: procedimento para os dois computadores, separação de Desktop Chat e Code, settings locais/compartilhados e MCP.
- `AGENT_AND_SKILL_CATALOG.md`: missão, entregáveis e limites dos agentes e Skills candidatos.

### Atualizado
- Arquitetura geral passou a `v0.4` e `IN_REVIEW`.
- Árvore passou a referenciar os novos documentos e a deixar explícito que configurações do Claude Code são artefatos de integração futura; incluído checklist de compatibilidade do repositório-alvo.
- Regras de configuração passaram a distinguir `.claude/settings.json`, `.claude/settings.local.json`, `~/.claude.json`, `.mcp.json` e MCP do aplicativo de chat Desktop.
- Base externa atualizada: NIST SSDF v1.1 final e v1.2 como Initial Public Draft; OWASP ASVS 5.0.0, MASVS, MASTG, MASWE e API Security Top 10; ANPD; Google SRE.
- Checklist e progresso separados entre conteúdo estruturalmente preparado, revisão humana pendente e validação técnica futura.

### Correções de governança
- Claude pode preparar e executar tarefas autorizadas, mas nunca ser autoridade final (`A`) ou aprovar decisões reservadas aos responsáveis humanos.
- Nomes, alçadas e poderes de aprovação dos fundadores não foram presumidos; ficam `UNASSIGNED` até confirmação.
- Conflitos entre documentos ou responsáveis devem ser registrados e encaminhados, nunca resolvidos silenciosamente.
- Aprovação arquitetural não equivale à aprovação de todas as decisões de produto, operação ou implementação.

### Preservado
- Escopo amplo e árvore-base da v0.3.
- Núcleo de contexto `YVENIST/`.
- Princípios de migração não destrutiva, execução progressiva, rastreabilidade e validação humana.

## v0.3 — arquitetura ampliada (17/11/2026)
- Acrescentou núcleo `YVENIST/`, domínios operacionais empresariais e estrutura candidata para Claude Code.

## v0.2 — arquitetura ampliada (17/11/2026)
- Ampliou o Blueprint para empresa, marketplace, operações, suporte, transações, crescimento, finanças, logística, dados e evolução.

## v0.1 — estrutura inicial
- Primeira proposta de fases de produto, design, engenharia e qualidade.

## Política de versionamento

- Não apagar versões anteriores.
- Cada versão deve registrar o que mudou, por que mudou, o que foi preservado e quais pendências permanecem.
- Não considerar uma versão aprovada apenas porque foi gerada ou distribuída.


## 1.1.0-rc.4 — correção da revisão multi-sessão

- Corrigida a conclusão da rc.3: a documentação oficial atual efetivamente documenta mensagens nativas cross-session entre sessões Claude Code alcançáveis.
- Registrados os requisitos de versão publicados: Windows nativo Claude Code `v2.1.234+`; macOS/Linux/WSL 2 `v2.1.224+`; `@menção` `v2.1.232+`.
- Registrados descoberta por `/list-agents`/linguagem natural, mensagens por `ListAgents`/`SendMessage`, controles de entrada `crossSessionInbound` e limites de segurança.
- Corrigida a regra Worktree: no Claude Desktop, o controle é desativado por padrão e deve ser ativado antes de iniciar cada sessão que necessita isolamento.
- Mantido o Git/commit/handoff como fonte persistente; mensagens são canal auxiliar, não transporte de arquivos nem consentimento humano.
- Atualizados os protocolos, checklist de inicialização, plano de piloto, guia de integração, catálogo de agentes, arquitetura, progresso, manifesto e notas da release.
- Reconfirmada a distinção entre duas sessões independentes + cross-session messaging e Agent Teams (recurso distinto, não presumido no Desktop).
- Simulação Git worktree/conflict continua PASS; piloto da interface Desktop e acessos autenticados GitHub/Figma continuam PENDING.

### Correção de revisão anterior

A rc.3 afirmava incorretamente que a documentação Desktop não descrevia mensagens nativas entre sessões. A página oficial específica `https://code.claude.com/docs/pt/cross-session-messaging` documenta explicitamente o recurso. A rc.4 supersede essa conclusão e retém o brief manual apenas como fallback.


## 1.1.0-rc.4 — correção final após reconsulta da documentação oficial (17/11/2026)

- A rc.3 continha uma conclusão incorreta de que mensagens nativas entre sessões locais não estavam documentadas. A página oficial específica de cross-session messaging confirma que Claude Code pode listar e enviar mensagens de texto a outras sessões alcançáveis.
- Requisitos registrados: Windows nativo Claude Code `v2.1.234+`; macOS/Linux/WSL 2 `v2.1.224+`; `@menção` `v2.1.232+`.
- Worktree no Desktop: a opção é desativada por padrão e precisa ser ligada antes de iniciar cada sessão que exige isolamento.
- Atualizados os documentos operacionais para usar mensagens nativas como canal de coordenação e Git/commits/handoffs como estado persistente; brief manual permanece como fallback.
- Mensagens não transferem arquivos ou histórico, não aprovam permissões nem modificam settings; controles de entrada `crossSessionInbound` e permissões por sessão permanecem aplicáveis.
- Piloto real Desktop e autenticação das fontes GitHub/Figma permanecem pendentes.

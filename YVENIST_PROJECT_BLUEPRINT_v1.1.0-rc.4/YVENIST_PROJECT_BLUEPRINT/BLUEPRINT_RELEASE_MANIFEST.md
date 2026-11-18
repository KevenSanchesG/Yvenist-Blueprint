# BLUEPRINT RELEASE MANIFEST

**Release:** `1.0.0`  
**Architecture status:** `APPROVED_AS_WORKING_ARCHITECTURE`  
**Approval record:** `00_GOVERNANCE_AND_PROJECT_CONTROL/ARCHITECTURE_APPROVAL_RECORD.md`

## Contents

This release includes the approved architecture, approval record, governance baseline, initial YVENIST context, Claude Code planning guidance, integration checklists, and directory-level READMEs.

## Important distinction

A directory README is an index and scope note, not a completed domain specification. Documents listed in `BLUEPRINT_ARCHITECTURE.md` but not yet present remain planned. The next authored domain document is `00_GOVERNANCE_AND_PROJECT_CONTROL/PRODUCT_CREATION_FRAMEWORK.md`.

## Package safety

- `.mcp.json.example` contains no configured servers or credentials.
- `.claude/settings.json` is not provided as an active configuration.
- No real secrets or production credentials are included.
- The root `CLAUDE.md` applies only to this Blueprint workspace and must not be copied automatically to the target repository.
- `.gitignore` excludes selected local Claude settings, environment files and private key material from version control.
- Directory-level `README.md` files explain scope and planned contents; they are not completed domain specifications.


## Addendum multi-sessão 0.2 — proposta

Este pacote também inclui um protocolo proposto para duas sessões Claude Code na aba Code do mesmo computador. O addendum não altera a arquitetura-base 1.0.0 aprovada. Sua ativação depende de aprovação específica, Git/worktree verificável, teste de transferência de brief, worktree, commit e handoff entre sessões e piloto de baixo risco.


## Addendum 1.1.0-rc.2 — registro das fontes do projeto

- Registrado o repositório GitHub `https://github.com/KevenSanchesG/Yvenist` como fonte pretendida para código e histórico.
- Registrado o arquivo Figma `Yvenist_v0` como fonte pretendida para design atual e histórico de versões.
- Criados protocolo de aquisição e reconciliação de fontes e os respectivos gates de acesso.
- Acesso ao GitHub e ao Figma permanece `PENDING` até ser testado com credenciais autorizadas.
- Não há autorização implícita para modificar o repositório ou o arquivo original do Figma.


## Estado do addendum 1.1.0-rc.3

A release candidata registra as fontes GitHub e Figma declaradas pelos responsáveis e acrescenta o procedimento de aquisição. O acesso às fontes ainda não foi testado. A coordenação multi-sessão permanece proposta até teste-piloto e aprovação humana.


## Addendum 1.1.0-rc.3 — revisão e testes do protocolo multi-sessão

- Padronizada a versão do protocolo multi-sessão como `0.2`.
- Removida a dependência de um canal nativo de mensagens entre sessões; o fluxo padrão utiliza transferência de brief pelo operador humano e Git branches/commits/handoffs.
- Acrescentado piloto operacional com duas sessões Desktop em repositório Git existente.
- Executada simulação de Git worktrees em repositório temporário: isolamento de arquivos, visibilidade de commits/branches e integração de alterações em caminhos distintos.
- Executada simulação de conflito no mesmo arquivo e confirmada a detecção pelo Git.
- Teste real da interface Claude Desktop, acesso autenticado ao GitHub e acesso ao Figma permanecem pendentes.


### Resultado de QA da release candidata 1.1.0-rc.3

- Integridade do ZIP e sintaxe do JSON de exemplo verificadas.
- Simulação de isolamento/integracão de Git worktrees e detecção de conflito aprovada em repositório temporário.
- Nenhum teste real da interface Claude Desktop foi executado neste ambiente.
- Nenhum conteúdo autenticado do GitHub ou Figma foi acessado nesta release.
- O protocolo multi-sessão permanece `PROPOSAL` até piloto real.


## Addendum multi-sessão 0.3 — release candidate 1.1.0-rc.4

- Comunicação nativa cross-session documentada em versões compatíveis, sujeita a descoberta de alvo e controles de mensagens recebidas.
- Windows nativo: Claude Code `v2.1.234+`; macOS/Linux/WSL 2: `v2.1.224+`; @mention `v2.1.232+`.
- Worktree precisa ser ativado antes de iniciar cada sessão de escrita no Desktop; vem desativado por padrão.
- Mensagens são texto auxiliar; Git, commits, registro e handoff são persistentes. Fallback manual permanece disponível.
- Simulação de Git worktrees realizada em repositório descartável: isolamento, branches, integração não conflitante e detecção de conflito passaram.
- Piloto real Desktop e autenticação GitHub/Figma não executados neste ambiente e permanecem pendentes.


## Multi-session addendum 0.3 — 1.1.0-rc.4

This candidate corrects the rc.3 capability assessment based on the official cross-session messaging documentation. Messaging is supported for reachable sessions meeting version and platform requirements, subject to inbound controls. Desktop Worktree must be enabled before each session starts; it is off by default. The addendum is still pending an actual Desktop pilot.

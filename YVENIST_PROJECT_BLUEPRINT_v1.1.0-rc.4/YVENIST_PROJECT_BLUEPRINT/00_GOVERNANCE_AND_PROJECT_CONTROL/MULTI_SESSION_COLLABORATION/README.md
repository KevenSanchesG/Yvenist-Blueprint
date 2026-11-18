# Multi-Session Collaboration

**Blueprint architecture baseline:** `1.0.0` (`APPROVED_AS_WORKING_ARCHITECTURE`)
**Protocol addendum:** `0.3`
**Status:** `PROPOSAL / READY_FOR_DESKTOP_PILOT`
**Environment:** duas sessões independentes Claude Code na aba Code do Claude Desktop, no mesmo computador.

## Finalidade

Coordenar duas sessões Claude Code que trabalham no mesmo projeto, combinando mensagens nativas entre sessões (quando disponíveis), Git worktrees, registro de tarefas, handoffs e revisão humana. O objetivo é aumentar a produtividade sem criar alterações concorrentes, decisões divergentes ou integrações não revisadas.

## Documentos

- `MULTI_SESSION_ORCHESTRATION.md` — papéis, ciclo e modelo de coordenação.
- `PARALLEL_WORK_PROTOCOL.md` — critérios para paralelizar ou serializar.
- `WORKSTREAM_REGISTRY.md` — fonte persistente de tarefas e estado.
- `SESSION_HANDOFF_PROTOCOL.md` — formato de entrega verificável.
- `CROSS_SESSION_COMMUNICATION.md` — mensagens nativas, limites e fallback.
- `WORKSPACE_OWNERSHIP_RULES.md` — propriedade de arquivos e diretórios.
- `CONFLICT_RESOLUTION_PROTOCOL.md` — resolução de conflitos.
- `SESSION_STARTUP_CHECKLIST.md` — preparação das sessões.
- `MULTI_SESSION_PILOT_TEST_PLAN.md` — teste controlado antes da ativação.

## Modelo de trabalho

- **Session A — Coordinator:** uma sessão coordenadora por ciclo; mantém o registro central, atribui tarefas, acompanha dependências, revisa entregas e coordena integração.
- **Session B — Specialist/Worker:** recebe um workstream delimitado, executa e valida a tarefa, comunica status e entrega branch/commit e handoff.
- Os papéis são operacionais. Nenhuma sessão adquire autoridade empresarial, jurídica, financeira, societária, de segurança ou de lançamento.

## Comunicação e fonte de verdade

A comunicação nativa cross-session é um canal auxiliar suportado pelas versões compatíveis do Claude Code. Ela transmite texto entre sessões, não sincroniza históricos nem arquivos, não transfere automaticamente anexos e não aprova permissões ou decisões humanas. Git, commits, handoffs versionados e documentos proprietários continuam sendo a evidência durável.

Se cross-session messaging não estiver disponível, estiver bloqueado ou falhar, usar o fallback documentado: brief transferido pelo operador e handoff por branch/commit.

## Worktrees

No Claude Desktop, o controle `Worktree` precisa ser ativado antes de iniciar cada sessão que deverá ter cópia isolada. Por padrão, o Worktree está desativado. Não iniciar escrita paralela até confirmar caminhos e branches distintos para as duas sessões.

## Ativação

Este addendum não configura automaticamente o Claude Desktop, Git, permissões, mensagens, hooks ou MCP. O protocolo só passa a `APPROVED_FOR_TWO_SESSION_WORKFLOW` após piloto na máquina real, registro das versões e evidências, resolução das falhas e aprovação humana.

## Fontes declaradas

- GitHub: https://github.com/KevenSanchesG/Yvenist
- Figma: https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1

O acesso autenticado continua pendente até ser verificado na máquina dos responsáveis.

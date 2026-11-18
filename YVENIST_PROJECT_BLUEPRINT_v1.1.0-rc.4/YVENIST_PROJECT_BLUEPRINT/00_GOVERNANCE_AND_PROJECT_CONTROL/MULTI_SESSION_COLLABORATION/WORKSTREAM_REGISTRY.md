# Workstream Registry

**Addendum:** `0.3` · **Status:** `PROPOSAL`
**Single writer:** Session A — Coordinator (durante cada ciclo ativo).

## 1. Estado inicial

Não há workstreams multi-sessão ativos registrados nesta release.

| Workstream ID | Tarefa | Sessão | Classe | Estado | Arquivos permitidos | Dependências | Base/branch | Última atualização |
|---|---|---|---|---|---|---|---|---|
| — | Nenhuma tarefa ativa | — | — | `NOT_STARTED` | — | — | — | — |

## 2. Estados permitidos

- `PROPOSED` — tarefa identificada, ainda não atribuída.
- `READY` — escopo, dependências e aceite definidos.
- `CLAIMED` — sessão responsável confirmou o recebimento.
- `IN_PROGRESS` — execução em andamento.
- `BLOCKED` — existe impedimento registrado.
- `HANDOFF_READY` — entrega apresentada, aguardando revisão.
- `IN_REVIEW` — coordenador avaliando.
- `INTEGRATED` — mudanças integradas e verificadas.
- `ACCEPTED` — critérios atendidos e aceite registrado.
- `REJECTED` — entrega não aceita; motivo registrado.
- `CANCELLED` — tarefa encerrada sem integração.

## 3. Template de workstream

Copiar este bloco para cada tarefa:

```yaml
workstream_id: WS-YYYYMMDD-001
name: "Nome curto da tarefa"
objective: "Resultado verificável"
requester: "Responsável humano ou coordenador delegado"
coordinator_session: "SESSION-A"
worker_session: "SESSION-B"
work_class: "READ_ONLY_PARALLEL | DISJOINT_WRITE | DEPENDENT_SEQUENCE | SHARED_FILE_SERIAL | HIGH_RISK_SERIAL"
status: "PROPOSED"
priority: "P0 | P1 | P2 | P3"
source_of_truth: ["caminhos dos documentos proprietários"]
read_paths: ["caminhos permitidos para leitura"]
write_paths: ["caminhos exclusivos de escrita"]
forbidden_paths: ["caminhos que não podem ser alterados"]
dependencies: []
assumptions: []
required_evidence: []
acceptance_criteria: []
allowed_tools: []
restricted_actions: ["sem publicação", "sem migração destrutiva"]
git_base: "branch/commit de origem ou N/A"
worktree: "enabled | separate-copy | read-only | N/A"
branch: "branch efetiva ou N/A"
handoff_path: "caminho exclusivo da entrega"
reviewer_session: "SESSION-A"
updated_at: "YYYY-MM-DD HH:MM TZ"
```

## 4. Transporte do brief entre worktrees

O registro é mantido no worktree da Session A e não fica automaticamente visível no worktree isolado da Session B. O fluxo preferencial é:

1. Session A prepara brief completo a partir deste registro ou de um arquivo versionado.
2. Session A envia uma mensagem cross-session resumida para Session B, apontando para o brief completo.
3. Session B confirma recebimento, escopo, branch/worktree, `write_paths` e critérios.
4. Se a mensagem não estiver disponível/for retida/recusada, o operador humano copia o brief para Session B.
5. Session B não edita o registro central; entrega handoff e commit em sua branch e envia aviso para A.
6. Session A inspeciona branch/commit e atualiza o registro após revisão.

Mensagens não sincronizam arquivos nem o registro central. Não presumir visibilidade de alterações não commitadas entre worktrees.

## 5. Regras do registro

- Session A é a única sessão que modifica este arquivo durante o ciclo.
- Session B envia atualizações/handoff à Session A por mensagem cross-session quando disponível; se indisponível, usa o fallback manual. Não edita o registro central.
- Toda tarefa de escrita precisa declarar `write_paths` e `forbidden_paths`.
- O registro não pode conter segredos, tokens ou dados pessoais desnecessários.
- Alterar estado exige data, motivo e responsável.
- Decisões de produto ou negócio devem ser registradas também na fonte de verdade aplicável; o registro de tarefas não substitui o `DECISION_LOG.md`.

## 6. Histórico resumido

| Data | Workstream ID | Mudança | Responsável |
|---|---|---|---|
| 2026-11-17 | — | Registro criado; nenhuma tarefa ativa | Blueprint maintainer |

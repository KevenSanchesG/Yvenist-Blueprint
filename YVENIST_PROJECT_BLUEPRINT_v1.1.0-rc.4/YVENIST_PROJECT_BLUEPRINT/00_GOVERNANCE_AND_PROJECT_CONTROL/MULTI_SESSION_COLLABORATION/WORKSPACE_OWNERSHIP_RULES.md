# Workspace Ownership Rules

**Addendum:** `0.3` · **Status:** `PROPOSAL`

## 1. Princípio

Cada arquivo ou conjunto de arquivos possui um único escritor ativo por vez. A leitura pode ser compartilhada; a escrita concorrente no mesmo caminho não é permitida sem plano explícito e coordenador responsável.

## 2. Ownership por padrão

| Recurso | Proprietário durante o ciclo |
|---|---|
| `WORKSTREAM_REGISTRY.md` | Session A — Coordinator, single writer |
| `DECISION_LOG.md` | Session A ou responsável humano designado; Session B envia proposta |
| `BLUEPRINT_ARCHITECTURE.md` e `CLAUDE.md` | Serializado; Session A prepara, humano aprova mudanças estruturais |
| `BLUEPRINT_PROGRESS.md` e `BLUEPRINT_CHANGELOG.md` | Session A após integração; Session B reporta dados |
| Documento de domínio atribuído | Sessão explicitamente indicada em `write_paths` |
| `.claude/settings*.json`, `.mcp.json`, hooks e permissões | Serializado, com revisão e autorização humana |
| Código e testes de uma feature | Sessão dona da feature, em branch/worktree isolado |
| Arquivos compartilhados por duas features | Coordenador escolhe um escritor; outra tarefa aguarda ou propõe patch separado |

## 3. Regras

- Session A declara ownership no registro antes de Session B escrever.
- A sessão executora não amplia seus `write_paths` por conta própria.
- Ao encontrar conflito, parar a escrita no caminho afetado e solicitar decisão.
- Não utilizar o mesmo checkout físico para duas sessões com escrita concorrente.
- Em Claude Desktop, ativar o controle `Worktree` antes de iniciar cada sessão de escrita; o controle fica desativado por padrão. Verificar um worktree isolado e branch identificável por sessão.
- Se o worktree não estiver disponível ou não puder ser verificado, usar uma cópia independente verificada ou serializar a escrita.
- Não integrar arquivos de um worktree simplesmente copiando por cima; revisar diff e preservar histórico Git quando houver.

## 4. Arquivos gerados e handoffs

Cada worker deverá produzir arquivos de handoff com nome único e não sobrescrever handoffs anteriores. Só o coordenador move conteúdo aceito para a fonte oficial, após revisão.

## 5. Limite humano

Ownership técnico não transfere autoridade de decisão. A sessão que possui um arquivo não pode aprovar o conteúdo de negócio reservado a um responsável humano.

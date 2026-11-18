# Session Handoff Protocol

**Protocol addendum:** `0.3` · **Status:** `PROPOSAL / PILOT_REQUIRED`

## 1. Quando é obrigatório

Toda tarefa executada pela Session B e destinada à integração precisa de handoff. Para tarefas read-only, o handoff ainda é necessário, mas não precisa de commit. Mensagens nativas avisam a sessão coordenadora; o handoff versionado e o commit constituem a evidência durável.

## 2. Estrutura de entrega

Criar um arquivo exclusivo por tarefa, preferencialmente em um diretório de handoffs de trabalho:

`WORKSTREAM_HANDOFFS/WS-YYYYMMDD-001_HANDOFF.md` (na branch/worktree da Session B).

Se o diretório não existir, Session B pode criá-lo em seu próprio worktree após o caminho ser incluído no brief. O handoff deve ser commitado na branch da Session B antes da entrega, salvo tarefa exclusivamente read-only.

## 3. Campos obrigatórios

```markdown
# Handoff — WS-YYYYMMDD-001

- Sessão executora:
- Tarefa e objetivo:
- Estado: HANDOFF_READY
- Base/branch/worktree:
- Commit SHA (se aplicável):
- Arquivos criados:
- Arquivos modificados:
- Arquivos não alterados, mas analisados:
- Fontes e evidências consultadas:
- Critérios de aceite: PASS / FAIL / NOT_RUN
- Testes/verificações executados e resultados:
- Decisões propostas (não aprovadas):
- Hipóteses e incertezas:
- Dependências e bloqueios:
- Riscos e impactos:
- Itens fora do escopo identificados:
- Próxima ação recomendada:
- Confirmação de que nenhum caminho proibido foi alterado:
```

## 4. Regras de integridade

- Não declarar teste PASS se não foi executado.
- Não declarar integração se só existe uma alteração local na worktree.
- Identificar claramente arquivos novos, modificados, removidos e renomeados.
- Não esconder alterações colaterais.
- Não atualizar status para `INTEGRATED` ou `ACCEPTED`; somente Session A pode fazê-lo após revisão, e o aceite humano continua obrigatório quando aplicável.

## 5. Mensagem de handoff

Depois de criar o handoff e fazer commit, Session B deve enviar mensagem cross-session à Session A com: ID, resumo curto, caminho do handoff, branch, SHA, testes e bloqueios. A Session A confirma recebimento, consulta a branch/commit no Git e revisa o diff. Se cross-session messaging falhar, o operador retransmite o resumo.

Mensagens não anexam arquivos. A coordenadora precisa obter o conteúdo por Git e pelos caminhos disponíveis em seu worktree. Não presumir que arquivos não commitados de B estejam visíveis em A.

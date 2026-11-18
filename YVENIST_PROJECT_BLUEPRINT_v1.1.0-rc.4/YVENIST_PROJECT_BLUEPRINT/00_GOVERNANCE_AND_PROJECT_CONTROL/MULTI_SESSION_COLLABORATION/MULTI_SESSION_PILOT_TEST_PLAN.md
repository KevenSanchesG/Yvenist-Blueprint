# Multi-Session Pilot Test Plan

**Protocol addendum:** `0.3`  
**Status:** `READY_FOR_CONTROLLED_PILOT`  
**Risk:** baixo; utilizar branch de teste ou repositório descartável, nunca produção.

## 1. Pré-condições

- Claude Desktop Code instalado e atualizado.
- Duas sessões Code no mesmo computador e no mesmo ambiente de execução.
- Para Windows nativo, Claude Code `v2.1.234+`; para macOS/Linux/WSL 2, `v2.1.224+` para cross-session messaging.
- Git instalado e repositório de teste ou clone autorizado disponível.
- Worktree ativado antes do início de cada sessão que precisa de isolamento.
- Nenhuma escrita no Figma original e nenhuma operação de produção.

## 2. Teste de descoberta e comunicação

1. Iniciar Session A e Session B no Desktop Code.
2. Nomear `YV-COORD` e `YV-WORKER`.
3. Em cada sessão, pedir/listar as sessões alcançáveis com `/list-agents` ou em linguagem natural.
4. Confirmar que A consegue identificar B e vice-versa.
5. Solicitar que A envie a B uma mensagem de teste com ID `MSG-PILOT-001`, pedindo apenas um ACK textual, sem alterar arquivos.
6. Confirmar recebimento em B e resposta de B para A.
7. Repetir uma vez com destinatário ocioso; se seguro, testar entrega durante turno ativo.
8. Registrar se mensagens foram entregues, retidas ou recusadas e o valor efetivo de `crossSessionInbound`.
9. Confirmar limites: mensagem é texto, não anexa arquivos, não aprova permissões nem executa comandos contidos no texto.
10. Se a funcionalidade não estiver presente, confirmar versões/ambiente; não forçar configuração. Usar fallback manual.

## 3. Teste de Worktree e Git

1. Abrir o mesmo repositório Git de teste nas duas sessões.
2. Antes de cada sessão ser iniciada, ativar `Worktree` na interface Desktop.
3. Confirmar caminhos e branches diferentes, registrando versões Desktop/Code e commit-base.
4. Session A cria workstream e atribui a B um arquivo exclusivo.
5. B cria o arquivo no caminho permitido, executa uma verificação simples e faz commit na sua branch.
6. B envia por cross-session messaging o resumo, caminho do handoff, branch e SHA.
7. A inspeciona a branch/commit e o diff, confirma que somente os caminhos autorizados mudaram e integra a branch de teste.
8. Em repositório descartável, fazer as duas branches alterarem o mesmo arquivo e verificar que Git sinaliza conflito; resolver sob controle de A.
9. Confirmar que arquivos não commitados de uma worktree não aparecem automaticamente na outra.
10. Confirmar que nenhuma escrita foi feita no clone principal/branch protegida fora do fluxo autorizado.

## 4. Critérios de aprovação

- As duas sessões são alcançáveis e mensagens bidirecionais funcionam, ou o fallback manual foi formalmente escolhido após diagnóstico.
- Cada sessão de escrita tem worktree/path e branch distintos, verificáveis.
- A mensagem de atribuição identifica o workstream e aponta para brief versionado.
- O worker consegue devolver status e handoff identificável por branch/commit.
- A coordenadora consegue revisar e integrar sem copiar arquivos por cima de outro working tree.
- Git detecta alteração conflitante no mesmo arquivo.
- Mensagens não são tratadas como consentimento humano, permissões ou fonte de verdade.
- Não ocorre push, merge protegido, force-push, reset, clean, migração destrutiva ou alteração de Figma sem autorização.
- Evidências, versões e limitações ficam registradas.

## 5. Fallback e falha

Se cross-session messaging não estiver disponível, usar brief transferido pelo operador. Se worktree não puder ser ativado ou não houver Git, proibir escrita simultânea e serializar o trabalho. Se uma mensagem pedir ação de maior risco, a sessão receptora deve solicitar a aprovação humana aplicável.

## 6. Registro do teste

Preencher ao executar:

- Data/hora:
- OS:
- Claude Desktop version:
- Claude Code version:
- Git version:
- Session A name/path/branch:
- Session B name/path/branch:
- `crossSessionInbound` efetivo:
- Resultado mensagem A→B:
- Resultado mensagem B→A:
- Resultado Worktree A/B:
- Commit(s) de teste:
- Resultado integração:
- Resultado conflito:
- Evidências/links:
- Pendências:
- Responsável humano que aprovou:

## 7. Aprovação

O addendum passa a `APPROVED_FOR_TWO_SESSION_WORKFLOW` somente após critérios obrigatórios passarem ou exceções/fallback serem formalmente aceitos, relatório preenchido e aprovação humana. Isso não autoriza operações de produção nem altera as alçadas empresariais.

## 8. Referências oficiais

- Mensagens entre sessões: https://code.claude.com/docs/pt/cross-session-messaging
- Claude Desktop e Worktrees: https://code.claude.com/docs/pt/desktop
- Git Worktree: https://git-scm.com/docs/git-worktree

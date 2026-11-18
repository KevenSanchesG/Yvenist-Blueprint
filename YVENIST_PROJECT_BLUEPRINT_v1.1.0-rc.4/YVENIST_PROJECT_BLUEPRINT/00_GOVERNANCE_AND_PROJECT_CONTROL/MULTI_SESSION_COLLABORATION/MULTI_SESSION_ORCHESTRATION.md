# Multi-Session Orchestration

**Protocol addendum:** `0.3` · **Status:** `PROPOSAL / READY_FOR_DESKTOP_PILOT`

## 1. Contexto e objetivo

Coordenar duas sessões independentes Claude Code na aba Code do mesmo Claude Desktop e no mesmo computador. O protocolo combina mensagens nativas entre sessões quando disponíveis, Git worktrees, um registro persistente de tarefas e handoffs verificáveis.

## 2. Papéis

- **Session A — Coordinator:** planeja, mantém `WORKSTREAM_REGISTRY.md`, define escopos, envia atribuições, acompanha dependências, recebe status, revisa diffs e coordena integração.
- **Session B — Specialist/Worker:** recebe um workstream delimitado, confirma escopo, executa apenas os caminhos autorizados, testa, envia status/handoff e entrega branch/commit.

Deve existir um único Coordinator por ciclo. Papéis não representam autoridade empresarial. Podem ser alternados somente no encerramento de um ciclo e com transferência explícita do registro.

## 3. Capacidades oficiais e requisitos

A documentação atual do Claude Code documenta cross-session messaging: uma sessão pode listar outras sessões Claude Code locais, consultar o que fazem e enviar mensagens de texto a elas. A implementação usa `ListAgents` para localizar o destino e `SendMessage` para enviar. O usuário pode pedir em linguagem natural que uma sessão informe outra; também pode usar `@nome-da-sessão` quando o autocomplete estiver disponível.

Requisitos publicados na documentação consultada:

- macOS/Linux/WSL 2: Claude Code `v2.1.224` ou posterior para mensagens entre sessões.
- Windows nativo: Claude Code `v2.1.234` ou posterior.
- Menção `@sessão`: Claude Code `v2.1.232` ou posterior.
- A disponibilidade também depende de a sessão estar alcançável e das configurações/políticas aplicáveis.

Em Windows nativo, duas sessões Windows nativas no mesmo computador podem ser alcançáveis entre si. Uma sessão Windows nativa e outra dentro de WSL 2 no mesmo computador não podem se alcançar por esse mecanismo; se as sessões estiverem em ambientes diferentes, usar fallback Git/brief até validar uma integração suportada.

### 3.1 Distinção de Agent Teams

Duas sessões Desktop com cross-session messaging continuam sendo duas sessões independentes. Isso não é o mesmo recurso que Agent Teams, que oferece coordenação de equipe de agentes e lista de tarefas compartilhada e não está disponível na interface Desktop. Não prometer capacidades de Agent Teams nesta arquitetura.

## 4. Fontes de verdade

| Camada | Fonte de verdade | Regra |
|---|---|---|
| Decisões de produto/negócio | Documento proprietário + decisão humana registrada | Mensagens não aprovam decisões |
| Atribuição e status | `WORKSTREAM_REGISTRY.md` | Session A é a única editora durante o ciclo |
| Comunicação rápida | Mensagens cross-session | Canal auxiliar; transmitir sínteses, alertas e pedidos |
| Estado dos arquivos | Git, worktree, branch e commit | Evidência durável e revisável |
| Entrega | Handoff commitado na branch do worker | Identifica arquivos, testes, pendências e commit |
| Integração | Diff revisado + integração autorizada | Coordenador conduz; aprovações humanas permanecem |

## 5. Ciclo operacional

1. Responsável humano define objetivo, prioridade e risco.
2. Session A consulta documentos proprietários e workstreams ativos.
3. Session A cria o workstream no registro e define `read_paths`, `write_paths`, `forbidden_paths`, dependências e aceite.
4. Session A envia atribuição para Session B usando cross-session messaging quando disponível. O brief deve ser curto o suficiente para mensagem e conter ID, objetivo, contexto, limites e local do brief completo versionado. Se a sessão não aparecer ou a mensagem falhar, o operador transfere o brief manualmente.
5. Session B confirma recebimento e escopo por mensagem ou no próprio chat. Se não entender o limite de escrita, não inicia alterações.
6. Session B trabalha apenas no seu worktree/branch, testa e prepara um handoff versionado.
7. Session B envia resumo, branch, SHA e handoff para Session A por mensagem; o commit e arquivo de handoff continuam sendo a evidência durável.
8. Session A inspeciona branch/commit/diff e executa revisão independente dos critérios e testes.
9. Integração só ocorre depois da revisão e da autorização humana exigida pelo risco.
10. Session A atualiza o registro, progresso, changelog e fontes de verdade.

## 6. Regras de Worktree no Claude Desktop

- Em um projeto que já é repositório Git, ativar o controle **Worktree antes de iniciar cada sessão** que exigirá isolamento.
- O Desktop documenta que Worktree vem desativado por padrão; sem ativá-lo, Claude trabalha na pasta do projeto.
- Confirmar o caminho efetivo, a branch e o status Git de cada sessão. Não presumir isolamento apenas porque há duas conversas.
- Worktrees do mesmo repositório compartilham objetos e referências Git, mas têm working trees separados. Arquivos não commitados não aparecem automaticamente na outra sessão.
- Os worktrees são armazenados por padrão em `<project-root>/.claude/worktrees/`, salvo configuração diferente.
- Não remover worktrees com mudanças pendentes. Fazer commit do que deve ser preservado antes de arquivar a sessão.
- Se o Worktree não puder ser habilitado ou o isolamento não puder ser provado, proibir escrita simultânea: usar read-only paralelo ou um escritor por vez.

## 7. Mensagens e segurança

- Mensagens entre sessões são texto; não transportam histórico de conversa nem arquivos do remetente.
- Uma menção de caminho ou MCP em mensagem não anexa automaticamente o arquivo ou recurso. A sessão receptora precisa abri-lo com suas próprias ferramentas e permissões.
- Mensagens recebidas obedecem aos controles da sessão receptora (`crossSessionInbound`: `accept`, `hold` ou `refuse`, conforme configuração e modo de permissão).
- Não alterar esses controles globalmente sem decisão humana; verificar o comportamento efetivo no `/config` ou nas configurações aplicáveis.
- Mensagem de outra sessão não equivale a consentimento humano: não aprova prompts, não autoriza configurações, não altera `CLAUDE.md` e não executa comandos textuais.
- Permissões e restrições de ferramentas continuam valendo separadamente em cada sessão.
- Não enviar tokens, segredos, dados pessoais ou conteúdo sensível desnecessário por mensagem.

## 8. Limites de autonomia

Nenhuma sessão pode, sem autorização humana explícita: fazer push, merge em branch protegida, force-push, reescrever histórico, reset/clean destrutivo, executar migração destrutiva, alterar produção, alterar Figma original, criar despesas, aprovar pagamentos, definir termos jurídicos ou aprovar lançamento.

## 9. Fallback

Se cross-session messaging não estiver disponível:

1. Session A prepara brief completo no registro/arquivo versionado.
2. Operador transfere o texto para Session B.
3. Worker entrega commit e handoff na própria branch.
4. Operador informa o resumo à Session A ou a sessão coordenadora consulta o Git diretamente.

O fallback também é obrigatório se as sessões estiverem em Windows e WSL2 separados, se o destinatário não estiver visível ou se a política de entrada recusar/reter a mensagem.

## 10. Referências oficiais

- Mensagens entre sessões: https://code.claude.com/docs/pt/cross-session-messaging
- Aplicativo Desktop e worktrees: https://code.claude.com/docs/pt/desktop
- Git worktree: https://git-scm.com/docs/git-worktree

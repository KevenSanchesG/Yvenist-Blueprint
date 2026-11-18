# CLAUDE DESKTOP CODE — INTEGRATION GUIDE

**Blueprint architecture:** `1.0.0`  
**Multi-session protocol:** `0.3` (`PROPOSAL / PILOT_REQUIRED`)  
**Environment:** duas sessões Claude Code na aba Code do mesmo Claude Desktop, no mesmo computador.

## 1. Desktop Chat x Claude Code

Servidores MCP configurados para o aplicativo de chat Claude Desktop não devem ser presumidos como disponíveis na aba Code. A experiência Code utiliza a configuração e o runtime do Claude Code.

Para sessões locais, consultar a documentação atual sobre arquivos e precedência de configuração: `https://code.claude.com/docs/en/settings`.

## 2. Escopos de configuração

| Arquivo/configuração | Escopo | Tratamento |
|---|---|---|
| `CLAUDE.md` | Instruções do projeto | Auditar e consolidar na raiz real após integração; não sobrescrever arquivo existente automaticamente. |
| `.claude/settings.json` | Configuração compartilhada | Versionar apenas após revisão de permissões. |
| `.claude/settings.local.json` | Preferências locais do projeto | Não compartilhar por padrão. |
| `~/.claude/settings.json` | Configuração de usuário/máquina | Não copiar indiscriminadamente entre computadores. |
| `~/.claude.json` | Estado/configuração local, incluindo MCPs por usuário | Não versionar nem compartilhar credenciais. |
| `.mcp.json` | Servidores MCP no escopo do projeto | Criar apenas após avaliação, autorização e estratégia de segredos. |
| `claude_desktop_config.json` | MCP do app Chat | Não presumir que configure a aba Code. |

## 3. Duas sessões no mesmo computador

### 3.1 Versões e alcance

A documentação atual de mensagens cross-session estabelece:

- Windows nativo: Claude Code `v2.1.234+`.
- macOS/Linux/WSL 2: Claude Code `v2.1.224+`.
- `@menção` por nome de sessão: `v2.1.232+`.

Confirmar a versão instalada antes do piloto. Duas sessões Windows nativas podem alcançar uma à outra; Windows nativo e WSL 2 no mesmo computador não se alcançam por esse mecanismo.

Renomear as sessões para `YV-COORD` e `YV-WORKER`. Listar sessões alcançáveis usando `/list-agents` quando disponível ou pedir ao Claude para listar as outras sessões. Pedir a uma sessão que envie mensagem à outra em linguagem natural; pode-se usar `@YV-WORKER` com autocomplete nas versões compatíveis.

### 3.2 Controles de mensagens recebidas

`crossSessionInbound` possui `accept`, `hold` e `refuse`. O comportamento padrão pode depender dos modos de permissão quando nenhum valor explícito se aplica. Verificar em `/config` (versões compatíveis) e documentar o valor efetivo. Não configurar `accept` globalmente sem aprovação. Mensagens continuam sujeitas às políticas e permissões da sessão receptora.

Mensagens são texto; não transferem histórico nem arquivos, não aprovam permissões, não alteram configurações e não executam comandos incluídos no texto. Mensagens não substituem registros persistentes e Git.

### 3.3 Worktree em cada sessão

No Desktop, em projetos Git, ativar o controle **Worktree antes de iniciar cada sessão** que requer isolamento. O controle vem desativado por padrão; sem ativá-lo, a sessão trabalha na pasta do projeto. Confirmar caminho, branch e estado Git diferentes para A e B antes de permitir escrita simultânea.

O padrão de armazenamento dos worktrees é `<project-root>/.claude/worktrees/`, salvo configuração diferente. Preservar alterações necessárias em commits antes de arquivar sessões/worktrees.

### 3.4 Fluxo de atribuição e integração

1. Session A consulta e atualiza `WORKSTREAM_REGISTRY.md`.
2. A define brief, `read_paths`, `write_paths`, `forbidden_paths`, dependências e critérios.
3. A envia uma mensagem resumida à B, apontando para o brief completo versionado. Se messaging falhar, o operador transfere o brief manualmente.
4. B confirma e executa somente no seu worktree/branch.
5. B entrega handoff versionado, commit SHA e mensagem de status.
6. A revisa branch, diff, testes e ownership. A integração requer autorização adequada.
7. A atualiza registro, changelog e progresso.

Agent Teams não deve ser confundido com duas sessões Desktop independentes: este protocolo usa sessões separadas + mensagens cross-session + Git Worktrees, não um Agent Team com task list compartilhada.

## 4. Segurança e permissões

- Começar em Plan mode ou no modo de permissão mais restritivo adequado.
- Não ativar Bypass Permissions para trabalho comum.
- Não conceder acesso amplo a shell, produção, dados pessoais, pagamentos ou repositórios fora do escopo.
- Não armazenar tokens, senhas, chaves privadas ou dados pessoais em Markdown/JSON versionado.
- Avaliar cada MCP por origem, ferramentas, dados, privilégios e plano de remoção.
- Revisar hooks e scripts antes de ativá-los.
- Uma mensagem de outra sessão não constitui consentimento humano nem altera as permissões da sessão receptora.

## 5. GitHub e Figma da Yvenist

Fontes declaradas:
- GitHub: `https://github.com/KevenSanchesG/Yvenist`
- Figma: `https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1`

O Claude deve auditar o repositório existente e preservar seu histórico; não criar um segundo histórico Git independente sem aprovação. O acesso autenticado ao GitHub/Figma deverá ser comprovado no ambiente autorizado antes de qualquer leitura ou alteração.

## 6. Compatibilidade e registro

Registrar Claude Desktop version, Claude Code version, OS, Git version, branch, worktree paths, sessão alcançável, `crossSessionInbound`, MCPs ativos, permissões e resultado do piloto. Consultar documentação atual quando houver mudança de versão.

## 7. Referências oficiais

- Desktop: https://code.claude.com/docs/pt/desktop
- Cross-session messaging: https://code.claude.com/docs/pt/cross-session-messaging
- Settings: https://code.claude.com/docs/en/settings

# Cross-Session Communication

**Protocol addendum:** `0.3` · **Status:** `PROPOSAL / PILOT_REQUIRED`

## 1. Canal primário: mensagens nativas cross-session

A documentação oficial atual do Claude Code disponibiliza mensagens entre sessões. Uma sessão pode descobrir outras sessões alcançáveis na mesma máquina, ler informações de status e enviar mensagens de texto. O Claude utiliza `ListAgents` e `SendMessage`; o operador não precisa chamar essas ferramentas diretamente.

O operador pode solicitar em linguagem natural, por exemplo:

> Informe à sessão YV-WORKER que a especificação de domínio foi aprovada e que ela já pode iniciar o workstream WS-20261117-001. Não altere o escopo nem os arquivos fora do brief.

Também é possível mencionar uma sessão pelo nome com `@nome-da-sessão` quando o autocomplete estiver disponível (Claude Code `v2.1.232+`). Renomear sessões com nomes estáveis, por exemplo `YV-COORD` e `YV-WORKER`, facilita o direcionamento.

### Requisitos de versão publicados

- macOS/Linux/WSL 2: Claude Code `v2.1.224+`.
- Windows nativo: Claude Code `v2.1.234+`.
- `@menção`: Claude Code `v2.1.232+`.

Verificar a versão instalada antes do piloto. Se estiver abaixo do mínimo, atualizar conforme a política do usuário ou utilizar o fallback.

## 2. Descoberta e nomeação das sessões

- Renomear as sessões com `/rename YV-COORD` e `/rename YV-WORKER` ou usar os controles de título da interface, conforme disponíveis.
- Pedir a Claude para listar as outras sessões acessíveis ou executar `/list-agents` quando o comando estiver disponível na versão instalada.
- Confirmar que a sessão de destino é a correta pelo nome e diretório de trabalho, quando exibido.
- Se o alvo não aparecer, verificar versões, ambiente (Windows nativo versus WSL), execução e política de mensagens; não presumir que duas sessões abertas são automaticamente alcançáveis.

## 3. Controles de mensagens recebidas

O Claude Code documenta `crossSessionInbound` com três valores:

- `accept`: entrega as mensagens recebidas ao Claude.
- `hold`: mantém a mensagem retida para aprovação/liberação conforme as regras de configuração.
- `refuse`: descarta mensagens recebidas.

Quando nenhum valor explícito se aplica, o comportamento pode depender dos modos de permissão das sessões. Consultar `/config` (se suportado, Claude Code `v2.1.232+`) e a documentação de precedência antes de alterar qualquer setting. Não forçar `accept` globalmente por conveniência; no piloto, registrar o comportamento encontrado e deixar a configuração existente intacta salvo decisão humana.

## 4. O que uma mensagem faz — e o que não faz

Mensagens são texto entre contextos de sessão. Não transferem o histórico inteiro nem arquivos. Se a mensagem citar um path ou recurso MCP, a sessão receptora deverá acessar o recurso por conta própria, com suas permissões.

Uma mensagem recebida:

- não aprova prompt de permissão;
- não equivale ao consentimento humano;
- não altera automaticamente settings, `CLAUDE.md` ou outras configurações;
- não executa comandos escritos no texto;
- permanece sujeita às permissões e regras da sessão receptora.

Por isso, a mensagem deve conter resumo e referência para o brief/handoff completo versionado, não substituir o registro formal.

## 5. Protocolo de atribuição

Session A prepara a tarefa no `WORKSTREAM_REGISTRY.md` e envia mensagem com:

```text
[WORKSTREAM ASSIGNMENT] WS-YYYYMMDD-001
Coordinator: YV-COORD
Worker: YV-WORKER
Objective:
Brief completo: <commit SHA que contém o arquivo + path>
Read-only command: git show <brief-commit>:<path>
Read paths:
Write paths exclusivos:
Forbidden paths:
Dependencies:
Acceptance criteria:
Git base / branch:
Handoff expected:
Confirme recebimento, branch/worktree e escopo antes de escrever.
```

A mensagem é um aviso/brief resumido. O arquivo versionado continua sendo o brief completo e fonte de referência. Para que B leia a versão exata em seu worktree, A deve informar o commit SHA que contém o brief e o caminho do arquivo. B pode consultar o conteúdo sem trocar de branch usando `git show <brief-commit>:<path>`. Se o commit/path não estiver acessível, A envia o brief completo na mensagem ou o operador usa a transferência manual. Não pedir ao worker que faça checkout da branch da coordenadora enquanto essa branch estiver aberta no worktree A.

## 6. Protocolo de status e handoff

Session B pode enviar mensagens curtas de status: `ACK`, `IN_PROGRESS`, `BLOCKED`, `HANDOFF_READY`. A mudança de estado só é registrada oficialmente por Session A no `WORKSTREAM_REGISTRY.md` após verificar a evidência.

Handoff mínimo:

```text
[WORKSTREAM HANDOFF] WS-YYYYMMDD-001
Summary:
Branch:
Commit SHA:
Handoff path:
Files changed:
Tests and results:
Known limitations:
Human decisions required:
```

A branch/commit e o arquivo de handoff são evidência durável; a mensagem apenas notifica a coordenadora.

## 7. Fallback manual

Se não for possível usar mensagens nativas, o operador copia o brief para Session B e transmite o resumo do worker à Session A. Se o compartilhamento de Git não estiver acessível, não copiar arquivos sobre o outro working tree; restabelecer acesso Git ou usar um caminho de transferência autorizado, seguido de revisão de integridade.

## 8. Referências oficiais

- Mensagens entre sessões: https://code.claude.com/docs/pt/cross-session-messaging
- Git Worktrees no Desktop: https://code.claude.com/docs/pt/desktop

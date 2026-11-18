# Session Startup Checklist

**Protocol addendum:** `0.3` · **Status:** `PROPOSAL / PILOT_REQUIRED`

## A. Confirmar ambiente e versões

- [ ] As duas sessões estão na aba **Code** do mesmo Claude Desktop.
- [ ] Ambas usam o mesmo ambiente de execução (preferencialmente Windows nativo para as duas, se for o ambiente definido); uma sessão Windows nativa e outra WSL 2 não se alcançam por cross-session messaging.
- [ ] Versão do Claude Code verificada. Para Windows nativo, cross-session messaging requer `v2.1.234+`; macOS/Linux/WSL 2 requer `v2.1.224+`.
- [ ] Para usar `@nome-da-sessão`, confirmar Claude Code `v2.1.232+`.
- [ ] Renomear as sessões para `YV-COORD` e `YV-WORKER` ou nomes inequívocos.
- [ ] Usar `/list-agents` ou pedir a Claude para listar as sessões alcançáveis; confirmar que ambas aparecem como esperado.
- [ ] Verificar `crossSessionInbound`/Messages from your other sessions na configuração aplicável; registrar `accept`, `hold`, `refuse` ou default sem alterar silenciosamente.

## B. Git e isolamento antes de escrita paralela

- [ ] Confirmar que a raiz lógica é o clone/repositório autorizado da Yvenist, não uma cópia temporária ou outro diretório homônimo.
- [ ] Verificar `.git`, `git status --short --branch`, branch e commit-base.
- [ ] Antes de iniciar **cada** sessão que deverá ser isolada, ativar o controle **Worktree** na interface Desktop. A opção fica desativada por padrão.
- [ ] Confirmar caminhos efetivos distintos, branches distintos e estado Git de cada worktree.
- [ ] Confirmar onde o Desktop armazenou os worktrees (por padrão `<project-root>/.claude/worktrees/`, salvo configuração diferente).
- [ ] Verificar se arquivos locais ignorados necessários (`.env`, credenciais) estão disponíveis de forma segura; não copiar segredos para o Blueprint nem incluir em commits.
- [ ] Se não houver isolamento comprovável, não permitir escrita em paralelo.
- [ ] Não criar outro repositório, alterar remote, fazer push ou alterar branch protegida sem autorização humana.

## C. Testar mensagens antes de delegar

- [ ] Session A pede à Session B um ACK de recebimento por linguagem natural ou `@YV-WORKER`.
- [ ] Session B responde para Session A confirmando que recebeu texto e identificou o remetente.
- [ ] Testar uma mensagem enquanto B está ociosa e, se seguro, outra enquanto B está em turno ativo.
- [ ] Confirmar que a mensagem não anexa arquivos automaticamente e que arquivos citados precisam ser acessados com permissões próprias.
- [ ] Confirmar que mensagens não aprovam permissões, não alteram configurações e não executam comandos textuais.
- [ ] Se mensagem estiver retida/recusada, registrar motivo; não contornar política. Usar fallback manual.

## D. Abrir workstream

- [ ] Session A é a única coordenadora e editora do registro central durante o ciclo.
- [ ] Criar ID e brief no `WORKSTREAM_REGISTRY.md`.
- [ ] Definir `read_paths`, `write_paths`, `forbidden_paths`, dependências e critérios de aceite.
- [ ] Enviar mensagem resumida e referência para o brief completo versionado.
- [ ] Session B confirma ID, escopo, branch/worktree e critérios antes de escrever.
- [ ] Permissões das sessões são adequadas; não usar Bypass Permissions para trabalho comum.

## E. Encerrar ciclo

- [ ] Worker entrega handoff versionado, branch e SHA de commit.
- [ ] Coordenadora recebe o aviso, inspeciona o diff e confirma ownership de arquivos.
- [ ] Testes são executados ou marcados `NOT_RUN` com justificativa.
- [ ] Integração ocorre de forma controlada, após aprovação exigida.
- [ ] Registro, progresso, changelog e documentos proprietários são atualizados.
- [ ] Não arquivar sessão/worktree com mudanças necessárias sem preservá-las em commit.

## F. Bloqueio

Se versão, alcance da sessão, permissões, branch, isolamento ou ownership não puderem ser confirmados, não iniciar escrita paralela. Usar leitura paralela, fallback manual ou um único escritor por vez.

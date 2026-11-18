# MCP Configuration Policy
**Release do Blueprint:** `1.0.0`

- O arquivo `.mcp.json.example` é apenas um exemplo sem servidores configurados.
- Não adicionar tokens, senhas ou segredos diretamente a arquivos versionados.
- Selecionar servidores MCP somente após identificar a necessidade, a origem do servidor, as permissões, os dados acessíveis e o responsável.
- Preferir variáveis de ambiente ou mecanismos seguros de autenticação documentados pelo fornecedor.
- Revisar escopo mínimo de ferramentas; não conceder acesso amplo a repositórios, produção, dados pessoais ou pagamentos sem justificativa e autorização.
- Validar a sintaxe e o suporte com a versão do Claude Code instalada no computador de cada colaborador.
- Documentar servidor, versão, finalidade, ferramentas habilitadas, dados acessíveis, risco, processo de atualização e plano de desativação.
- A existência deste arquivo não significa que qualquer servidor MCP já esteja autorizado ou configurado.

## Escopo do Claude Desktop

A aba Code usa os mecanismos de configuração do Claude Code. Não presumir que servidores configurados no aplicativo de chat Claude Desktop estejam disponíveis na aba Code. Para o Code, validar configuração no escopo de projeto (`.mcp.json`) ou de usuário (`~/.claude.json`), conforme a documentação vigente. Não copiar `claude_desktop_config.json` como se fosse a configuração do Code.

## Compartilhamento entre máquinas

- `.mcp.json` pode ser usado para servidores MCP no escopo do projeto, sem segredos embutidos.
- `~/.claude.json` é configuração por usuário/máquina e não deve ser versionada nem copiada indiscriminadamente.
- Cada computador deve autenticar-se de acordo com o fornecedor e confirmar o servidor ativo.
- Registrar diferenças de versão, autenticação e capacidades entre as máquinas.
- Revogar/remover MCP quando sua finalidade terminar ou houver mudança de risco.

Documentação oficial: https://code.claude.com/docs/pt/desktop e https://code.claude.com/docs/en/settings.

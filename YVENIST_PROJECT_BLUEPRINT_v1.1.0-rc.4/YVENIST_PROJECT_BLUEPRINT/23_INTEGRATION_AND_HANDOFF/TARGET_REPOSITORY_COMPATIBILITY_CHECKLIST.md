# TARGET REPOSITORY COMPATIBILITY CHECKLIST
**Release do Blueprint:** `1.0.0`

**Versão:** 0.4  
**Status:** `NOT_STARTED` — execução somente na integração futura.  
**Objetivo:** validar compatibilidade real com o repositório e os dois ambientes Claude Desktop Code.

## A. Repositório e estado de trabalho

- [ ] Confirmar a raiz correta do repositório.
- [ ] Registrar branch atual, remotos e último commit observado.
- [ ] Registrar alterações locais não commitadas e arquivos não rastreados.
- [ ] Confirmar backup e branch específica de integração.
- [ ] Inventariar instruções, configurações, regras, Skills, agentes e hooks existentes.
- [ ] Não sobrescrever ou apagar instruções existentes sem plano aprovado.

## B. Conteúdo e autoridade das fontes

- [ ] Inventariar Markdown, PDFs, decisões, requisitos, APIs e documentação de Figma acessível.
- [ ] Identificar origem, data, autoridade e status das fontes.
- [ ] Mapear cada fonte para a propriedade documental do Blueprint.
- [ ] Registrar contradições e lacunas antes de consolidar.
- [ ] Obter aprovação dos responsáveis para resolver conflitos de decisões aprovadas.

## C. Claude Desktop Code — computador 1 e computador 2

- [ ] Registrar versão Desktop/Code e sistema operacional em cada computador.
- [ ] Abrir a raiz do projeto-alvo na aba Code.
- [ ] Confirmar leitura do `CLAUDE.md` final.
- [ ] Confirmar settings compartilhados e locais carregados.
- [ ] Confirmar que arquivos locais/segredos não serão versionados.
- [ ] Confirmar Skills e agentes disponíveis.
- [ ] Confirmar hooks com testes seguros e logs.
- [ ] Confirmar os MCPs definidos para Claude Code; não confundir com MCP do chat Desktop.
- [ ] Comparar diferenças entre computadores e registrar correções.

## D. Testes de segurança e comportamento

- [ ] Testar em branch/cópia de baixo risco.
- [ ] Confirmar que Claude pede autorização para alterações destrutivas e ações externas relevantes.
- [ ] Confirmar que não acessa segredos e caminhos fora do escopo autorizado.
- [ ] Validar que o modelo de permissão é compatível com a versão instalada.
- [ ] Validar scripts de hooks isoladamente antes de ativar.
- [ ] Validar configuração JSON e MCP com mecanismos/documentação atuais.

## E. Resultado e aprovação

- [ ] Relatório de compatibilidade por computador concluído.
- [ ] Plano de integração e rollback aprovado.
- [ ] Alterações aplicadas em branch dedicada.
- [ ] Diff revisado por responsável humano.
- [ ] Testes pós-integração concluídos.
- [ ] Commits aprovados e estratégia de merge definida.

**Regra:** até concluir esta lista e obter aprovação humana, o Blueprint é documentação de planejamento; não é configuração de produção nem autorização para modificar o repositório.


## F. Fontes oficiais declaradas pelos responsáveis

- [ ] Registrar GitHub `https://github.com/KevenSanchesG/Yvenist` em `SOURCE_REGISTER.md`.
- [ ] Verificar acesso ao repositório sem presumir que é público; registrar resultado.
- [ ] Confirmar se a pasta selecionada é clone existente e comparar remotes com a URL declarada.
- [ ] Não inicializar Git nem alterar remotes automaticamente.
- [ ] Registrar Figma `Yvenist_v0`: `https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1`.
- [ ] Confirmar permissões Figma de leitura.
- [ ] Inventariar arquivo atual e histórico de versões, com IDs exatos.
- [ ] Registrar versões relevantes em `FIGMA_VERSION_LEDGER.md` (a ser produzido na auditoria).
- [ ] Reconciliar Figma com decisões aprovadas e estado do código no commit auditado.
- [ ] Obter aprovação humana antes de alterar GitHub ou Figma.

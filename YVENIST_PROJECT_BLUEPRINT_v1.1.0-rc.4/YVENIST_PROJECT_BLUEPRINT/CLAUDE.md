# CLAUDE.md — YVENIST PROJECT BLUEPRINT WORKSPACE

## Contexto e limite deste diretório

Esta pasta é o ambiente independente de planejamento e documentação do `YVENIST_PROJECT_BLUEPRINT`. Ela não é o repositório do aplicativo Yvenist e não autoriza alterações no código, backend, Figma ou infraestrutura do projeto de Rafael.

A arquitetura do Blueprint está aprovada como estrutura de trabalho (`1.0.0`). Isso não significa que todos os documentos de domínio, decisões de negócio ou configurações técnicas estejam concluídos ou aprovados.

## Leitura obrigatória no início de uma tarefa relevante

1. `README.md`
2. `BLUEPRINT_ARCHITECTURE.md`
3. `BLUEPRINT_PROGRESS.md`
4. `00_GOVERNANCE_AND_PROJECT_CONTROL/ARCHITECTURE_APPROVAL_RECORD.md`
5. `00_GOVERNANCE_AND_PROJECT_CONTROL/DOCUMENT_OWNERSHIP_AND_BOUNDARIES.md`
6. `00_GOVERNANCE_AND_PROJECT_CONTROL/DECISION_AUTHORITY_AND_RACI.md`
7. Documentos de domínio diretamente relacionados à tarefa.

## Regras de trabalho

- Trate `BLUEPRINT_ARCHITECTURE.md` como arquitetura aprovada. Não altere sua estrutura sem solicitação e aprovação humana explícitas.
- Preserve arquivos, históricos e decisões. Não apague, sobrescreva em massa ou mova materiais sem inventário, justificativa e autorização.
- Consulte a matriz de propriedade documental antes de criar ou alterar um documento; mantenha uma fonte de verdade por assunto.
- Diferencie `APPROVED`, `PROPOSAL`, `ASSUMPTION`, `UNVERIFIED`, `BACKEND_DEPENDENCY`, `SUPERSEDED` e `REJECTED`.
- Diferencie `MVP`, `POST_MVP`, `FUTURE_VISION`, `OUT_OF_SCOPE` e `TO_VALIDATE`.
- Não invente estado do produto, dados, preços, fornecedores, APIs, backend, integrações, regras comerciais, capacidade operacional ou requisitos legais.
- Quando faltar evidência, registre a lacuna e identifique o que precisa ser verificado.
- Claude pode pesquisar, analisar, redigir e executar tarefas autorizadas; não é autoridade final de negócio, jurídica, societária, financeira ou de lançamento.
- Não atribua papéis ou alçadas nominais aos fundadores. Enquanto não forem confirmados, mantenha `UNASSIGNED`.
- Não trate diretórios README como documentos de especificação concluídos. Produza cada documento quando sua finalidade, entradas, proprietário, dependências e critérios de aceite estiverem definidos.
- Não instale nem configure MCP, hooks, permissões amplas, agentes ou Skills automaticamente. Primeiro documente necessidade, origem, dados acessíveis, ferramentas, riscos e validação.
- Quando houver mais de uma sessão Claude Code ativa, leia `00_GOVERNANCE_AND_PROJECT_CONTROL/MULTI_SESSION_COLLABORATION/README.md` e siga o `WORKSTREAM_REGISTRY.md`, o protocolo de ownership, mensagens cross-session, Worktree, handoff e conflito. Mensagens são texto auxiliar; não transferem arquivos/contexto nem aprovam permissões. No Desktop, o Worktree deve ser habilitado antes de iniciar cada sessão que precisa de isolamento (desativado por padrão). Se mensagens não estiverem disponíveis, use o fallback manual documentado.
- Não inclua segredos, credenciais ou dados pessoais reais nos arquivos.

## Manutenção obrigatória

Toda mudança substancial deve atualizar:

- `BLUEPRINT_CHANGELOG.md`;
- `BLUEPRINT_PROGRESS.md`;
- o documento especializado afetado;
- o registro de decisão, quando houver nova decisão ou mudança de decisão.

Ao concluir uma entrega, informe o que foi alterado, o que permaneceu pendente, quais evidências foram verificadas e qual aprovação humana é necessária.

## Integração futura

Este `CLAUDE.md` orienta apenas o workspace do Blueprint. Não o copie automaticamente para a raiz do repositório de desenvolvimento. Na etapa de integração, audite o `CLAUDE.md` existente, preserve instruções válidas e prepare uma versão consolidada para aprovação humana.

## Fontes oficiais declaradas pelos responsáveis

- GitHub: https://github.com/KevenSanchesG/Yvenist — repositório pretendido para auditoria e integração; acesso ainda precisa ser verificado.
- Figma: https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1 — arquivo de design e histórico; acesso e permissões precisam ser verificados.
- Não substitua, inicialize, clone, altere remotes ou escreva nessas fontes sem seguir o protocolo de aquisição e obter a autorização indicada.

# Parallel Work Protocol

**Addendum:** `0.3` · **Status:** `PROPOSAL`

## 1. Objetivo

Aumentar a velocidade sem permitir que duas sessões alterem simultaneamente a mesma fonte de verdade, gerem documentos divergentes ou integrem código não revisado.

## 2. Classificação das tarefas

| Classe | Descrição | Execução |
|---|---|---|
| `READ_ONLY_PARALLEL` | Pesquisa, auditoria, leitura, revisão sem alteração | Pode ocorrer em paralelo; saídas separadas |
| `DISJOINT_WRITE` | Alterações em arquivos/diretórios sem sobreposição e sem dependência conflitante | Pode ocorrer em paralelo com ownership e isolamento confirmados |
| `DEPENDENT_SEQUENCE` | A tarefa B depende da decisão ou do entregável da tarefa A | Executar em sequência ou aguardar handoff explícito |
| `SHARED_FILE_SERIAL` | Duas tarefas precisam alterar o mesmo arquivo ou fonte de verdade | Um único escritor por vez |
| `HIGH_RISK_SERIAL` | Configuração global, migração, segurança, pagamentos, produção, arquitetura central ou mudança destrutiva | Serializar, exigir revisão e autorização apropriada |

## 3. Condições mínimas para paralelizar escrita

Todas precisam ser verdadeiras:

1. Existe um ID de tarefa e um brief no registro central da Session A; Session A enviou atribuição resumida à Session B por mensagem cross-session e apontou para o brief completo versionado. Se mensagens não estiverem disponíveis, o operador transfere o brief manualmente.
2. Os arquivos de escrita permitidos estão delimitados.
3. Não há outro workstream ativo com ownership sobre os mesmos caminhos.
4. O repositório é Git e o controle `Worktree` foi ativado antes de iniciar cada sessão de escrita; os caminhos e branches efetivos são distintos e verificáveis, ou existe cópia de trabalho independente e verificada.
5. A base/branch de origem está identificada.
6. Os critérios de aceite e o formato de handoff estão definidos.
7. Há um coordenador único responsável pela integração; a entrega do worker inclui branch/commit, handoff commitado e mensagem cross-session de notificação (ou fallback manual).

Se qualquer condição falhar, restringir a atividade a leitura/pesquisa ou permitir apenas um escritor por vez. Se cross-session messaging falhar mas o Git/worktree estiver correto, usar transferência manual do brief e handoff como fallback; não contornar controles de mensagens.

## 4. Dependências e arquivos compartilhados

- Dois trabalhos podem ler o mesmo documento.
- Dois trabalhos não podem escrever no mesmo documento simultaneamente.
- Alterações em `CLAUDE.md`, arquitetura raiz, RACI, ownership, registro de decisões, settings, `.mcp.json`, hooks e regras globais são serializadas, salvo plano de integração explícito.
- Um trabalho que descubra que precisa tocar arquivo de outro workstream deve parar a alteração desse arquivo, avisar Session A por mensagem cross-session (ou fallback manual) e aguardar reatribuição.
- Não editar o mesmo arquivo em duas worktrees e resolver depois por tentativa e erro; a prevenção é a regra.

## 5. Limites de paralelismo

Começar com duas sessões, uma coordenadora e uma executora. Não abrir novas sessões de escrita apenas porque há capacidade de uso disponível. O número de tarefas simultâneas depende de independência, risco, contexto, custo de revisão e capacidade humana de integrar.

## 6. Exemplos para a Yvenist

**Paralelizável, com arquivos separados:** pesquisa de concorrentes e pesquisa de fornecedores; auditoria read-only de fluxos do app consumidor e revisão read-only de documentação de backend; produção de dois briefs independentes depois de aprovados os critérios comuns.

**Não paralelizar escrita:** duas sessões ajustando `PRODUCT_CREATION_FRAMEWORK.md`; uma alterando `BUSINESS_RULES.md` enquanto outra altera a mesma regra em um documento de operação; duas sessões mexendo em `.claude/settings.json`; duas sessões alterando o mesmo fluxo de contratação.

## 7. Critério de conclusão

Uma tarefa paralela só é considerada concluída depois de handoff commitado, aviso à coordenadora, revisão do diff, validação dos critérios e integração controlada. “A sessão terminou” não equivale a “a tarefa foi integrada”.

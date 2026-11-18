# YVENIST PROJECT BLUEPRINT

**Release:** `1.0.0`  
**Status da arquitetura:** `APPROVED_AS_WORKING_ARCHITECTURE`  
**Data de aprovação:** `17/11/2026`  
**Base aprovada:** arquitetura v0.4  
**Natureza:** arquitetura de trabalho, conhecimento e governança para orientar o desenvolvimento integral da Yvenist.

## 1. O que foi aprovado

Foi aprovada a arquitetura do Blueprint como estrutura de trabalho para orientar Claude Code e os responsáveis humanos no planejamento, construção, operação, lançamento e evolução da Yvenist como empresa, marketplace e ecossistema de produtos e serviços.

A aprovação está registrada em `00_GOVERNANCE_AND_PROJECT_CONTROL/ARCHITECTURE_APPROVAL_RECORD.md` e detalhada em `BLUEPRINT_ARCHITECTURE.md`.

## 2. O que esta release contém

- Árvore de diretórios aprovada, materializada nesta pasta.
- Núcleo de contexto empresarial `YVENIST/`.
- Governança, critérios de decisão e propriedade documental.
- Catálogo candidato de agentes e Skills e orientações de integração do Claude Desktop Code.
- Procedimentos e checklists planejados para integração não destrutiva com o repositório existente.
- Arquivos README em diretórios de domínio para explicar finalidade e documentos planejados.

Os README de diretórios indicam escopo e sequência. Eles **não substituem** os documentos especializados listados na arquitetura, que serão escritos conforme o framework e as prioridades aprovadas.

## 3. O que ainda não está concluído

- `00_GOVERNANCE_AND_PROJECT_CONTROL/PRODUCT_CREATION_FRAMEWORK.md` — próximo documento a ser produzido.
- Documentos especializados de estratégia, pesquisa, operação, design, engenharia e demais domínios.
- Atribuição nominal dos papéis e alçadas RACI.
- Auditoria do repositório, código, Figma, backend, APIs e ambiente do Rafael.
- Implementação e teste das configurações Claude Code, Skills, agentes, hooks e MCP.
- Integração do Blueprint ao repositório-alvo.

Portanto, `APPROVED` refere-se à **arquitetura do Blueprint**, não à conclusão do conteúdo de todos os domínios nem à prontidão técnica da integração.

## 4. Como trabalhar com este pacote

1. Mantenha esta pasta independente do projeto de código do Rafael até a etapa de handoff.
2. Comece lendo `CLAUDE.md`, `BLUEPRINT_ARCHITECTURE.md` e `BLUEPRINT_PROGRESS.md`.
3. Consulte as fontes de verdade indicadas em `00_GOVERNANCE_AND_PROJECT_CONTROL/DOCUMENT_OWNERSHIP_AND_BOUNDARIES.md`.
4. Preserve o histórico; nunca substitua decisões aprovadas silenciosamente.
5. Ao alterar a arquitetura, atualize checklist, changelog e progresso.
6. Ao escrever documentos de domínio, use os templates de `22_TEMPLATES/` quando aplicável.
7. Não adicione credenciais, tokens, senhas, chaves privadas ou dados pessoais reais ao Blueprint.
8. Não copie o `CLAUDE.md` deste ambiente para o repositório-alvo sem auditoria e adaptação.

## 5. Addendum multi-sessão em revisão

O protocolo `00_GOVERNANCE_AND_PROJECT_CONTROL/MULTI_SESSION_COLLABORATION/` foi acrescentado como proposta para duas sessões Claude Code na aba Code do mesmo computador. A arquitetura-base `1.0.0` continua aprovada; o addendum `0.3` requer piloto operacional. A comunicação nativa cross-session é documentada em versões compatíveis e será testada; mensagens não transferem arquivos nem substituem Git/handoffs. No Desktop, ativar `Worktree` antes de iniciar cada sessão que deverá ser isolada (desativado por padrão).

## 6. Próxima etapa oficial

Aprovar e testar o addendum multi-sessão em tarefa-piloto. Depois, construir `00_GOVERNANCE_AND_PROJECT_CONTROL/PRODUCT_CREATION_FRAMEWORK.md`, incorporando as regras de coordenação, paralelismo, handoff e integração ao processo operacional do produto.

## 7. Fontes oficiais declaradas

- GitHub: https://github.com/KevenSanchesG/Yvenist
- Figma `Yvenist_v0`: https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1

Ambas estão registradas em `00_GOVERNANCE_AND_PROJECT_CONTROL/SOURCE_REGISTER.md`. A designação pelos responsáveis não equivale à verificação de acesso ou auditoria dos conteúdos.

## 8. Addendum de fontes e multi-sessão

A versão `1.1.0-rc.4` corrige o protocolo multi-sessão após nova conferência das páginas oficiais: mensagens cross-session estão documentadas e Worktree deve ser ativado antes de iniciar cada sessão de escrita. O piloto real do Desktop e o acesso autenticado ao GitHub/Figma continuam pendentes.


## 9. Limite da verificação atual

Os endereços do GitHub e Figma foram registrados por declaração dos responsáveis. Nenhum acesso, branch/commit, arquivo Figma ou histórico de versões foi auditado por esta release. Os procedimentos de aquisição são somente leitura até aprovação separada para alterações.

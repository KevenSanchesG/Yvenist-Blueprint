# DECISION AUTHORITY AND RACI
**Release do Blueprint:** `1.0.0`

**Versão:** 0.4  
**Status:** `PROPOSAL` — os responsáveis humanos ainda devem confirmar os nomes e poderes de aprovação.  
**Objetivo:** impedir que Claude, documentos ou permissões técnicas sejam confundidos com autoridade empresarial.

## 1. Princípios

- A autoridade final pertence a uma pessoa humana formalmente designada para a decisão.
- Claude pode ser `R` (Responsible pela execução de uma tarefa autorizada), `C` (Consulted) ou `I` (Informed), mas nunca `A` (Accountable) nem aprovador final.
- Os fundadores devem indicar quem detém a autoridade final por domínio e se certas decisões exigem aprovação conjunta. O Blueprint não presume que todos os temas exigem unanimidade nem atribui poder unilateral a qualquer fundador.
- Se não houver autoridade designada, registrar `UNASSIGNED`; não executar ações irreversíveis nem declarar decisão aprovada.
- Poder de editar código ou arquivo não equivale a poder de aprovar mudança de produto, negócio ou política.
- Quando uma decisão exigir conhecimento regulatório ou profissional, identificar o profissional habilitado como consultado/revisor e registrar seu parecer, sem delegar a decisão empresarial a Claude.

## 2. Papéis a confirmar

| Código | Papel | Responsabilidade esperada | Pessoa designada |
|---|---|---|---|
| `BO` | Business Owner / autoridade de negócio | Estratégia, modelo comercial, prioridades empresariais e alocação de recursos | `UNASSIGNED` |
| `PO` | Product Owner / responsável de produto | Visão, necessidades, roadmap, escopo e aceite de produto | `UNASSIGNED` |
| `TO` | Technical Owner / responsável técnico | Arquitetura, qualidade técnica, segurança técnica e decisões de engenharia | `UNASSIGNED` |
| `DO` | Design/Brand Owner | Direção de marca, UX, identidade, Design System e aceite visual | `UNASSIGNED` |
| `OO` | Operations Owner | Operação de marketplace, fornecedores, atendimento e fulfillment | `UNASSIGNED` |
| `FO` | Finance Owner / responsável financeiro | Orçamento, preço, comissões, pagamentos, conciliação e controles financeiros | `UNASSIGNED` |
| `LO` | Legal/Privacy professional | Revisão jurídica, contratual, societária, consumerista e LGPD, conforme habilitação | `UNASSIGNED` |
| `SO` | Security specialist | Revisão de ameaças, controles e testes especializados, quando necessário | `UNASSIGNED` |
| `CL` | Claude / agente de IA | Pesquisa, análise, documentação, implementação e testes autorizados | Não se aplica como autoridade humana |
| `EXT` | Terceiro / fornecedor especializado | Execução contratada ou parecer dentro do escopo acordado | Conforme contratação |

Os papéis podem ser acumulados por uma mesma pessoa em uma startup pequena. Acúmulo não elimina a necessidade de explicitar conflitos de interesse, revisão independente em temas críticos e limites de autoridade.

## 3. Matriz RACI proposta

Legenda: `A` = autoridade final humana; `R` = executa/prepara; `C` = consultado; `I` = informado. Cada linha deve ter exatamente um `A` humano depois da nomeação. O quadro abaixo é uma proposta de distribuição por papel, não uma atribuição já aprovada.

| Classe de decisão | A (humano a designar) | R principal | Consultados mínimos | Claude |
|---|---|---|---|---|
| Estratégia empresarial e posicionamento | `BO` | `BO` / `PO` | fundadores, pesquisa, financeiro | `R/C` para análise e documentação; nunca A |
| Modelo de negócio e monetização | `BO` | `BO` / `FO` | `PO`, `OO`, `LO` quando aplicável | análise de cenários; nunca aprova preços ou comissões |
| MVP, roadmap e priorização | `PO` ou `BO` conforme governança a confirmar | `PO` | `BO`, `TO`, `OO`, `DO` | prepara opções e backlog; humano aceita escopo |
| Pesquisa com usuários e fornecedores | `PO` | pesquisa / `CL` autorizado | `OO`, `DO`, participantes | pode preparar roteiro e síntese; não inventa entrevistas ou evidências |
| Regras do marketplace | `BO` / `OO` conforme política a confirmar | `OO` / `PO` | `FO`, `LO`, `TO` | modela e documenta; não aprova política |
| Atendimento, suporte e incidentes | `OO` | equipe de suporte / `CL` autorizado | `BO`, `LO`, `TO` | auxilia triagem e procedimentos; não decide disputas críticas por conta própria |
| Identidade e expressão da marca | `DO` ou `BO` conforme governança a confirmar | `DO` | fundadores, `PO` | explora e propõe; aceite humano obrigatório |
| UX e Design System | `DO` / `PO` conforme domínio | design | usuários, engenharia, acessibilidade | propõe, documenta e implementa o que for autorizado |
| Arquitetura técnica | `TO` | engenharia | `PO`, segurança, operação | analisa e propõe; alteração estrutural depende de aprovação definida |
| Segurança e privacidade | `TO` para controles técnicos; `LO` para enquadramento jurídico | especialistas/equipe técnica | `SO`, `LO`, `BO` | auxilia análise; não emite parecer jurídico nem certifica segurança |
| Dados, analytics e IA | `PO` / `TO` conforme domínio | dados/engenharia | `BO`, `LO`, `OO` | propõe eventos e modelos; não autoriza tratamento de dados ou decisões de alto impacto |
| Orçamento, contratos e contratação | `BO` / `FO` conforme alçada a definir | `FO` / área responsável | `LO` | prepara comparação; não compromete recursos ou aceita contratos |
| Alteração destrutiva ou migração | autoridade de repositório designada pelo time | `TO` / responsável documental | `BO`, proprietários de domínio | só executa após aprovação explícita, backup e plano de reversão |
| Publicação e lançamento | `BO` com aceite técnico de `TO` e operação `OO` | `TO` / `OO` | `PO`, `LO`, suporte, marketing | prepara checklist e evidências; não publica nem assume aprovação final sem autorização |

## 4. Decisões que exigem autorização explícita

Exigem autorização específica antes da execução:

- exclusão, sobrescrita, movimentação em massa ou migração irreversível de arquivos;
- alterações de produção, banco de dados, credenciais, pagamentos ou permissões de usuários;
- contratação, compra, assinatura ou mudança de plano de serviço;
- envio de mensagens externas, publicação de conteúdo ou comunicação oficial;
- lançamento, submissão às lojas ou ativação de pagamentos;
- adoção de política jurídica, comercial, de privacidade ou de moderação;
- utilização de dados pessoais reais em testes, pesquisas ou ferramentas externas;
- criação de automações que executem ações externas ou com impacto financeiro.

## 5. Como registrar uma decisão

Toda decisão deve registrar:

- ID único;
- assunto e contexto;
- alternativas consideradas;
- recomendação e justificativa;
- evidências e fontes;
- impactos, riscos e dependências;
- papel e pessoa que aprovou;
- data de aprovação;
- escopo, status e documentos afetados;
- condições para reavaliação.

Apenas uma confirmação expressa do responsável identificado altera o status para `APPROVED`. Uma sugestão do Claude, um documento escrito ou uma execução técnica não constituem aprovação.

## 6. Resolução de divergências

Se os responsáveis discordarem:

1. suspender a decisão afetada, sem bloquear atividades independentes;
2. registrar as posições e consequências de cada alternativa;
3. identificar o procedimento de resolução acordado entre os fundadores;
4. se envolver direitos societários, observar os documentos jurídicos vigentes e consultar advogado;
5. manter a decisão `IN_REVIEW` até resolução formal.

O Claude não deve inventar voto de desempate, hierarquia societária ou regra de unanimidade.

## 7. Campos pendentes antes da integração

- [ ] Confirmar os responsáveis e nomes para cada papel.
- [ ] Confirmar quais decisões exigem aprovação conjunta dos fundadores.
- [ ] Definir alçadas financeiras e limites de contratação.
- [ ] Definir o responsável pelo repositório e pela publicação.
- [ ] Definir quem aprova políticas legais, privacidade e segurança.
- [ ] Definir fluxo de aprovação de marca, UX e produto.

**Regra:** até que esses campos sejam resolvidos, a matriz é uma proposta de governança, não uma representação de poderes societários ou legais.

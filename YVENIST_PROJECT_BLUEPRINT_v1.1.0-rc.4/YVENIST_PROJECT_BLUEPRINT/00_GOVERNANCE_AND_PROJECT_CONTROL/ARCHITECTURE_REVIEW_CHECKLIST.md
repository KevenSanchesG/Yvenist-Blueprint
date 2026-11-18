# ARCHITECTURE REVIEW CHECKLIST

**Release aprovada:** 1.0.0 (baseline estrutural v0.4)  
**Status atual:** `APPROVED_AS_WORKING_ARCHITECTURE`  
**Objetivo:** apoiar a aprovação da arquitetura do Blueprint como estrutura de trabalho. Não aprova o conteúdo ainda não produzido, a implementação técnica ou a integração ao repositório-alvo.

## 1. Cobertura do escopo da Yvenist

- [x] Empresa, estratégia e modelo de negócio.
- [x] Produto, portfólio e escopo de lançamento.
- [x] Pesquisa e validação com consumidores, fornecedores e operações.
- [x] Marketplace, catálogo, solicitações, propostas, contratações e estados.
- [x] Aplicativos, backoffice, ferramentas internas e canais públicos.
- [x] UX, conteúdo, marca, identidade visual, Design System e acessibilidade.
- [x] Arquitetura técnica, dados, APIs, infraestrutura e integrações.
- [x] Operação de fornecedores, administração, moderação, suporte e incidentes.
- [x] Confiança, transações, pagamentos, repasses, comissões, reembolsos e disputas.
- [x] Crescimento, CRM, finanças, jurídico, conformidade e governança.
- [x] Logística, entrega e cumprimento de serviços físicos.
- [x] Analytics, métricas, personalização, recomendações e governança de IA.
- [x] Testes, segurança, confiabilidade, lançamento e melhoria contínua.

## 2. Prevenção de duplicidades e propriedade documental

- [x] Criada matriz de proprietário/consumidor para os principais assuntos com risco de sobreposição.
- [x] Definida diferença entre jornadas atuais observadas e jornadas futuras projetadas.
- [x] Definida diferença entre fundamentos da marca e estratégia de expressão da marca.
- [x] Separados processo de suporte, regras de reembolso e execução técnica de estorno.
- [x] Separados incidentes da prestação do serviço e exceções de logística/transporte.
- [x] Separados governança de dados, arquitetura técnica de dados e obrigações de privacidade.
- [ ] Revisar a matriz quando cada documento especializado for produzido e aprovado.

## 3. Autoridade, papéis e aprovação humana

- [x] Criada matriz RACI por papel, sem presumir atribuições pessoais.
- [x] Claude excluído da posição de aprovador final.
- [x] Ações destrutivas, externas, financeiras e de produção exigem autorização explícita.
- [x] Previsto tratamento de divergência entre responsáveis.
- [ ] Fundadores devem nomear responsáveis, alçadas e aprovações conjuntas antes da integração.

## 4. Claude Code e Claude Desktop Code

- [x] Separados artefatos de documentação do Blueprint e artefatos ativos do projeto-alvo.
- [x] Distinguido `.claude/settings.json` compartilhado de `.claude/settings.local.json` local.
- [x] Distinguido MCP do aplicativo Chat/Desktop de MCP do Claude Code.
- [x] Definida criação de Skills com `SKILL.md` e critérios de reutilização.
- [x] Definidos limites para agentes, hooks e permissões.
- [ ] Validar sintaxe e comportamento com a versão instalada no computador de cada colaborador.
- [ ] Validar a abertura da pasta do Blueprint e posteriormente do repositório-alvo no Claude Desktop Code.

## 5. Referências externas

- [x] NIST SSDF v1.1 identificado como publicação final vigente consultada.
- [x] NIST SP 800-218 Rev. 1 / SSDF v1.2 identificado como Initial Public Draft, não como versão final.
- [x] OWASP ASVS 5.0.0 identificado como versão estável consultada.
- [x] OWASP MASVS, MASTG e MASWE incluídos como referências distintas de segurança móvel, com as versões/estados consultados em 17/11/2026.
- [x] OWASP API Security Top 10 incluído como referência complementar de API.
- [x] Materiais da ANPD e Google SRE incluídos como fontes de orientação.
- [ ] Confirmar aplicabilidade concreta de cada controle quando arquitetura e tratamento de dados forem conhecidos.

## 6. Integração com o projeto existente

- [x] Definido processo de auditoria antes da integração.
- [x] Definido princípio não destrutivo e necessidade de backup/branch/revisão.
- [x] Definido mapeamento fonte-alvo e tratamento de conflitos.
- [ ] Auditar repositório, documentos, Figma, APIs e ambiente do Rafael — etapa futura.
- [ ] Testar configurações, Skills, agentes, hooks e MCP no repositório-alvo — etapa futura.
- [ ] Aprovar o plano de integração e o pacote final — etapa futura.

## 7. Decisão de aprovação da arquitetura

A aprovação humana foi registrada em `ARCHITECTURE_APPROVAL_RECORD.md`, decisão `BP-ARCH-001`, em 17/11/2026.

- [x] A árvore representa adequadamente o escopo da Yvenist.
- [x] A distribuição de documentos e limites é compreensível como arquitetura de trabalho.
- [x] O mapa de propriedade documental é aceito como regra de governança.
- [x] A matriz de autoridade é aceita como modelo, mantendo nomes e alçadas pessoais não atribuídos até confirmação.
- [x] A estratégia de Claude Code/Desktop Code é aceita como desenho para validação no ambiente real.
- [x] A integração não destrutiva está aprovada como princípio obrigatório.
- [x] A árvore será implementada progressivamente, sem criar documentos vazios em massa.

**Resultado:** `APPROVED_AS_WORKING_ARCHITECTURE`. Os itens futuros das seções 2, 3, 4 e 6 continuam abertos porque dependem da produção de documentos, nomeação de responsáveis, auditoria do repositório e testes reais. Sua permanência desmarcada não invalida a aprovação da arquitetura; indica trabalho operacional ainda não executado.

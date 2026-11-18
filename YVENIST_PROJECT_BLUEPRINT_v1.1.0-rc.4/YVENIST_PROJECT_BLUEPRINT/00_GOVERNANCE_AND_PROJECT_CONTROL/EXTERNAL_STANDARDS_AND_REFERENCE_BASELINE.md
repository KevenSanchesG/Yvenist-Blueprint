# EXTERNAL STANDARDS AND REFERENCE BASELINE
**Release do Blueprint:** `1.0.0`

**Versão do registro:** 0.4  
**Data da verificação:** 17/11/2026  
**Status:** `REFERENCE_BASELINE` — fontes de referência; não equivalem a adoção formal, certificação ou parecer profissional.

## 1. Claude Code / Claude Desktop Code

| Fonte | Estado consultado | Uso previsto | Limite |
|---|---|---|---|
| Claude Code — Settings files and precedence | Documentação oficial consultada em 17/11/2026 | Escopo e precedência de settings, permissões e configurações compartilhadas/locais | Revalidar na versão instalada antes de implementar. |
| Claude Code — Desktop app | Documentação oficial consultada em 17/11/2026 | Diferença Desktop Code/CLI e separação entre MCP do chat e MCP do Code | Recursos podem mudar; validar em ambos os computadores. |
| Anthropic Help Center — FAQ do Claude Code | Documentação oficial consultada em 17/11/2026 | Conceitos de MCP e hooks | Não usar como única fonte de configuração detalhada. |

Links:
- https://code.claude.com/docs/en/settings
- https://code.claude.com/docs/pt/desktop
- https://support.claude.com/pt/articles/14554922-faq-do-claude-code

## 2. Desenvolvimento seguro e segurança de aplicações

| Fonte | Versão/estado consultado | Uso previsto | Limite |
|---|---|---|---|
| NIST SP 800-218, SSDF | v1.1, publicação final de 03/02/2022 | Base estável de práticas de desenvolvimento seguro | Selecionar práticas conforme risco e contexto. |
| NIST SP 800-218 Rev. 1, SSDF v1.2 | Initial Public Draft publicado em 17/12/2025; comentários encerrados em 30/01/2026; status consultado como Draft | Monitorar evolução e comparar melhorias | Não tratar como versão final ou requisito obrigatório enquanto permanecer draft. |
| OWASP ASVS | v5.0.0, versão estável publicada em 30/05/2025 | Requisitos de verificação para aplicações web e serviços | Definir nível e controles aplicáveis; não declarar conformidade sem verificação. |
| OWASP MASVS | Projeto consultado em 17/11/2026; v2 indicada como "coming soon"; v1.5.0 identificada pelo projeto como última versão da linha v1 | Requisitos de segurança para aplicativos móveis | Acompanhar a transição v1/v2; não misturar requisitos de versões diferentes sem registrar a versão adotada. |
| OWASP MASTG | v2.0.0 anunciada em 2026; consultado em 17/11/2026 | Métodos e testes para segurança móvel | A v2 alterou artefatos e organização; não presumir checklists estáticos antigos como artefatos oficiais. |
| OWASP MASWE | v1.0.0 estável publicada em 17/08/2026 | Relacionar fraquezas, impacto e mitigações móveis | A ligação MASVS → MASWE → MASTG é útil para rastreabilidade; ainda pode haver fraquezas sem teste dedicado. |
| OWASP API Security Top 10 | Edição 2023 consultada em 17/11/2026 | Riscos recorrentes de API | Taxonomia de riscos, não substitui modelagem de ameaças nem ASVS. |
| OWASP Web Application Top 10 | Edição 2025 consultada em 17/11/2026 | Riscos gerais de aplicações web, inclusive backoffice e canais web | Taxonomia de conscientização; não é checklist completo de verificação. |

Links:
- NIST SSDF v1.1 final: https://csrc.nist.gov/pubs/sp/800/218/final
- NIST SSDF v1.2 draft: https://csrc.nist.gov/pubs/sp/800/218/r1/ipd
- OWASP ASVS: https://asvs.owasp.org/
- OWASP MASVS: https://mas.owasp.org/MASVS/
- OWASP MASTG: https://mas.owasp.org/MASTG/
- OWASP MASWE: https://mas.owasp.org/MASWE/
- OWASP Web Application Top 10 2025: https://owasp.org/www-project-top-ten/
- OWASP API Security Top 10 2023: https://owasp.org/API-Security/editions/2023/en/0x11-t10/

**Regras importantes:** (1) o NIST SSDF v1.2 aparece como Initial Public Draft na fonte oficial consultada; o encerramento do prazo de comentários não o transforma em versão final. Manter v1.1 como publicação final de referência e v1.2 no radar de atualização. (2) A OWASP anunciou MASWE v1.0.0 em 17/08/2026 e MASTG v2.0.0 em 2026; a página de contribuição identifica MASVS v2 como futura e MASVS v1.5.0 como última versão da linha v1 consultada. Registrar a versão escolhida antes de aplicar controles. (3) OWASP ASVS 5.0.0 estável desde 30/05/2025; OWASP Web Top 10 edição 2025; API Security Top 10 edição 2023.

## 3. Privacidade e proteção de dados no Brasil

| Fonte | Estado consultado | Uso previsto | Limite |
|---|---|---|---|
| ANPD — Guia sobre agentes de tratamento e encarregado | Página oficial consultada; publicação 22/11/2024, modificação 23/01/2025 | Analisar papéis de controlador, operador e encarregado | A qualificação decorre das atividades reais, não apenas do contrato. |
| ANPD — Direitos dos titulares | Página oficial consultada em 17/11/2026 | Orientar processo de atendimento a titulares | Validar texto legal vigente e prazos aplicáveis com assessoria especializada. |

Links:
- https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-para-definicoes-dos-agentes-de-tratamento-de-dados-pessoais-e-do-encarregado
- https://www.gov.br/anpd/pt-br/assuntos/titular-de-dados/direito-dos-titulares

## 4. Confiabilidade e operação

| Fonte | Estado consultado | Uso previsto | Limite |
|---|---|---|---|
| Google SRE Books and Resources | Conteúdo de referência consultado em 17/11/2026 | SLI/SLO, incidentes, postmortems, capacidade e confiabilidade | Adaptar proporcionalmente ao porte e à criticidade da operação. |

Links:
- https://sre.google/books/
- https://sre.google/resources/book-update/

## 5. Como o Claude deverá usar essas referências

1. Tratar standards e guias como fontes para análise, não como prova automática de conformidade.
2. Registrar versão, estado (final/draft/estável/experimental), data e aplicabilidade.
3. Antes de elaborar requisito, consultar a fonte oficial mais atual disponível.
4. Distinguir obrigação legal, requisito interno adotado, recomendação e certificação.
5. Registrar quais controles foram selecionados, quais não se aplicam e por quê.
6. Não fornecer parecer jurídico, fiscal, contábil ou certificação de segurança; preparar insumos para os profissionais competentes.
7. Atualizar este registro quando uma versão final substituir uma draft ou quando houver mudança material.

## 6. Evidência da verificação externa

- NIST confirma SSDF v1.2 como Initial Public Draft de 17/12/2025, com comentários encerrados em 30/01/2026: https://csrc.nist.gov/pubs/sp/800/218/r1/ipd
- OWASP anuncia ASVS 5.0.0 como estável, publicado em 30/05/2025: https://asvs.owasp.org/
- OWASP anunciou MASWE v1.0.0 em 17/08/2026 e explica o encadeamento MASVS → MASWE → MASTG: https://mas.owasp.org/news/2026/08/17/maswe-v100-release/
- OWASP informa MASTG v2 e mudanças nos artefatos de checklist: https://mas.owasp.org/checklists/MASVS-CODE/
- OWASP identifica MASVS v2 como futura e MASVS v1.5.0 como última v1 no momento da consulta: https://mas.owasp.org/contributing/
- Anthropic documenta arquivos e precedência de settings, incluindo projeto compartilhado e settings locais: https://code.claude.com/docs/en/settings
- Anthropic documenta que Desktop Code e CLI compartilham configurações de Claude Code, enquanto MCP do chat Desktop é separado do Code: https://code.claude.com/docs/pt/desktop
- ANPD publica orientação sobre agentes de tratamento e direitos dos titulares: links acima.


## Project-specific authoritative sources (registered separately)

The two project sources declared by the responsible user are maintained in `SOURCE_REGISTER.md` and are not external standards: GitHub repository `https://github.com/KevenSanchesG/Yvenist` and Figma file `https://www.figma.com/design/G2QX9NnDe8gJOnTrFUw1jH/Yvenist_v0?t=0u2P7rgPxMKQ5kxX-1`. Their access and contents must be audited before factual claims are made from them.

# Blueprint Progress

**Arquitetura-base:** `1.0.0` — `APPROVED_AS_WORKING_ARCHITECTURE`  
**Addendum multi-sessão:** `0.3` — `PROPOSAL / READY_FOR_DESKTOP_PILOT`  
**Release candidata atual:** `1.1.0-rc.4`

## Concluído

- Arquitetura-base 1.0.0 aprovada pelos responsáveis.
- Fontes declaradas GitHub e Figma registradas; acesso autenticado ainda não auditado.
- Protocolo multi-sessão 0.3 redigido para duas sessões Claude Code Desktop no mesmo computador.
- Comunicação nativa cross-session validada documentalmente com a Anthropic; teste operacional na máquina dos responsáveis pendente.
- Regras de versões mínimas registradas: Windows nativo Claude Code 2.1.234+; macOS/Linux/WSL 2 2.1.224+; @mention 2.1.232+.
- Regra Worktree corrigida: controle deve ser ativado antes de iniciar cada sessão de escrita; padrão desativado.
- Simulação Git em repositório temporário: worktrees isolados, commits independentes, integração não conflitante e detecção de conflito: `PASS`.
- Testes estáticos anteriores do ZIP, estrutura, paths sem duplicação e JSON MCP example: `PASS`.

## Pendente

- Executar piloto real com duas sessões Claude Desktop Code na máquina do usuário.
- Verificar versão Claude Desktop/Code e sistema operacional.
- Confirmar descoberta, mensagens bidirecionais, comportamento de mensagens recebidas e fallback.
- Confirmar Worktree ativado individualmente antes de cada sessão, paths/branches distintos e handoff real.
- Validar acesso autenticado ao GitHub e auditar o repositório existente sem modificá-lo.
- Validar acesso autorizado ao Figma, versão atual, páginas, frames e histórico; não editar o original durante a aquisição.
- Escrever `PRODUCT_CREATION_FRAMEWORK.md` após o piloto ou decisão explícita de prosseguir com o protocolo como proposta.

## Regra de progresso

A existência de um documento ou pasta não indica que a especificação está concluída. Marcar um item como concluído somente com conteúdo, evidência, revisão e status explícitos.

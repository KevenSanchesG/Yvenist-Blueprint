# Conflict Resolution Protocol

**Addendum:** `0.3` · **Status:** `PROPOSAL`

## 1. Quando há conflito

Considerar conflito qualquer divergência entre sessões sobre requisito, decisão, fonte de verdade, conteúdo de arquivo, estado Git, prioridade ou critério de aceite.

## 2. Resposta imediata

1. A sessão que identificar o conflito pausa alterações no escopo afetado.
2. Mantém os arquivos e diffs sem sobrescrever.
3. Envia à Session A, preferencialmente por mensagem cross-session, o ID dos workstreams envolvidos, caminhos, commits/branches, divergência e impacto. Se messaging falhar, usa o fallback manual.
4. Session A registra o bloqueio no `WORKSTREAM_REGISTRY.md`.
5. Se a decisão for de negócio, produto, marca, jurídico, finanças ou autoridade, Session A prepara opções e encaminha ao responsável humano.

## 3. Tipos de conflito

| Tipo | Resolução |
|---|---|
| Mesmo arquivo alterado | Serializar; comparar diffs; escolher uma integração ou compor patch revisado |
| Documento duplicado | Consultar `DOCUMENT_OWNERSHIP_AND_BOUNDARIES.md`; manter uma fonte de verdade e converter o outro em referência |
| Requisito contraditório | Consultar decisão aprovada; se ausente, registrar `IN_REVIEW` e pedir decisão humana |
| Dependência alterada | Pausar consumidor; atualizar brief e critérios; replanejar |
| Testes incompatíveis | Reproduzir em base comum, isolar a causa e registrar evidência |
| Divergência de interpretação | Expor evidência e opções; não deixar uma sessão sobrescrever a outra silenciosamente |
| Conflito Git/merge | Revisão humana ou técnica do diff; nunca forçar resolução automática em arquivo crítico |

## 4. Regras de integração

- Coordenador integra somente após receber handoff.
- Revisar `git status`, diff, arquivos não rastreados, testes e commits.
- Nunca usar `reset --hard`, `clean -fd`, sobrescrita em massa ou remoção de worktree para “resolver” conflito sem autorização humana explícita e backup.
- Mudanças nos documentos centrais, configuração, segurança, pagamentos, dados ou produção exigem revisão adicional proporcional ao risco.

## 5. Encerramento

Registrar causa, resolução, arquivos afetados, testes, decisão humana se aplicável e prevenção de recorrência. Atualizar o workstream e o changelog quando a solução alterar o Blueprint.

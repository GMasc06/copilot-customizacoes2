---
name: governanca-seguranca
description: "Aplique governanca DevSecOps em issues, Pull Requests, revisoes, documentacao e gates de merge. Use para criar tickets de seguranca, sugerir correcoes linha a linha, atualizar SECURITY.md ou README.md e recomendar bloqueio de merge com evidencia."
argument-hint: "Informe o achado, PR, ticket ou documento que precisa ser atualizado."
user-invocable: true
---

# Governanca e Acao de Seguranca

## Procedimento

1. Confirme o achado, o escopo, a severidade, o ativo afetado e a evidencia tecnica.
2. Proponha correcao pequena e testavel, incluindo arquivo, linha, exemplo seguro e criterio de aceite.
3. Para revisoes, escreva comentarios objetivos no ponto exato: problema, impacto, sugestao e teste.
4. Para tickets, inclua titulo, severidade, prioridade, componentes, passos para reproduzir, risco, correcao e tags `security` e `high` quando justificadas.
5. Atualize SECURITY.md, README.md ou politica somente quando a regra for confirmada e o texto permanecer coerente com o projeto.
6. Antes de bloquear merge ou alterar status de PR, exija evidencia de risco critico e confirmacao do responsavel ou da politica CI configurada.

## Guardrails

- Nao crie ticket, comentario, commit, bloqueio de merge ou alteracao externa sem autorizacao explicita e ferramenta disponivel.
- Nao use prioridade alta automaticamente: justifique com impacto e explorabilidade.
- Nao altere o status de um PR apenas por suspeita ou falso positivo nao investigado.
- Nao remova protecoes, force push ou aprove excecoes de seguranca.

## Entrega

Retorne o achado, a acao proposta, a autorizacao necessaria, o texto pronto para issue ou comentario e o criterio para fechar ou desbloquear o item.
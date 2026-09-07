---
name: contexto-seguranca
description: "Consulte documentacao interna, politicas, OWASP, LGPD, GDPR, PCI DSS, Marco Civil, memoria do projeto e logs de auditoria para responder perguntas de seguranca com contexto. Use quando houver Notion, Confluence, Google Docs, RAG, Splunk, Datadog, CloudWatch ou outras fontes conectadas."
argument-hint: "Informe a politica, fonte de conhecimento, sistema de logs ou intervalo que deve ser consultado."
user-invocable: true
---

# Contexto, Memoria e Evidencias

## Procedimento

1. Liste as fontes disponiveis e confirme escopo, permissao, atualidade e confiabilidade.
2. Consulte primeiro politica interna, arquitetura, threat model, excecoes aprovadas e historico do projeto.
3. Use OWASP, LGPD, GDPR, PCI DSS e Marco Civil como referencias de apoio, observando versao e jurisdicao aplicavel.
4. Para logs, filtre por ator, recurso, acao, resultado, correlation ID e janela de tempo; agregue sem expor dados pessoais.
5. Diferencie fato observado, ausencia de evidencia, inferencia e recomendacao. Registre a origem de cada conclusao.
6. Atualize a memoria ou documentacao somente com conhecimento confirmado, versionado e sem segredos.

## Privacidade e segurança

- Nao consulte sistemas externos sem autorizacao e ferramenta configurada.
- Nao reproduza tokens, PII, payloads sensiveis ou logs brutos na resposta.
- Nao trate um documento antigo ou uma resposta vazia como prova de conformidade.
- Quando fontes conflitarem, destaque o conflito e solicite decisão do responsavel.

## Entrega

Informe fontes consultadas, periodo e filtros, evidencias mascaradas, conclusao, nivel de confianca, lacunas de contexto e proximo passo de verificacao.
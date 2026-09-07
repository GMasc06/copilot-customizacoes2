---
name: validacao-dinamica
description: "Valide seguranca em runtime com testes HTTP, Postman, HTTPie, OWASP ZAP, Burp Suite e verificacao de headers. Use para DAST autorizado, testes de autenticacao, autorizacao, IDOR, API, CSP, HSTS e respostas 403."
argument-hint: "Informe a URL de homologacao, endpoints, credenciais de teste e escopo autorizado."
user-invocable: true
---

# Validacao Dinamica de Seguranca

## Pre-condicoes

1. Confirme autorizacao escrita, ambiente de homologacao, janela de teste e limites de carga.
2. Nunca teste producao, terceiros ou dados reais sem escopo explicito.
3. Use contas e tokens de teste com privilegios minimos; nunca solicite ou registre segredos reais.

## Procedimento

1. Verifique disponibilidade, TLS, redirects, CORS, cookies e headers como CSP, HSTS, X-Frame-Options, Referrer-Policy e Permissions-Policy.
2. Execute chamadas positivas e negativas com HTTPie, Postman ou cliente equivalente.
3. Teste autenticação, expiracao, revogacao, RBAC, acesso por objeto, mass assignment, enumeracao e respostas 401/403.
4. Execute DAST com OWASP ZAP ou Burp somente no escopo autorizado, com limite de requisicoes e sem dados destrutivos.
5. Colete evidencias minimizadas: request, response, status, correlation ID e timestamp, removendo tokens e dados pessoais.
6. Reproduza apenas o necessario para confirmar o impacto e valide a correcao com um teste de regressao.

## Regras

- Nao realize exploracao destrutiva, exfiltracao, persistencia ou bypass fora do escopo.
- Nao trate ausencia de alerta do scanner como prova de seguranca.
- Interrompa se houver risco de indisponibilidade, dados reais ou efeito fora da homologacao.

## Entrega

Informe escopo, ferramenta e versao, testes executados, resultado esperado e observado, evidencia mascarada, severidade, risco residual e proximo gate.
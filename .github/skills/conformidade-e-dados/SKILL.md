---
name: conformidade-e-dados
description: "Analise dados pessoais, logs, consentimento, cookies, fluxos e retencao sob LGPD e GDPR. Use para DLP, CPF em logs, pixels antes do consentimento, data mapping, criptografia, anonimização, pseudonimizacao e DPIA."
argument-hint: "Informe o fluxo, banco, log, tela de consentimento ou mapa de dados a analisar."
user-invocable: true
---

# Conformidade e Protecao de Dados

## Procedimento

1. Identifique titulares, categorias de dados, finalidade, base legal, origem, destinatarios, transferencias e prazo de retencao.
2. Mapeie o fluxo desde coleta até processamento, armazenamento, compartilhamento, backup, log e exclusao.
3. Procure CPF, documentos, cartao, e-mail, telefone, tokens e outros dados sensiveis em logs, fixtures, exports e respostas.
4. Valide mascaramento, pseudonimizacao, anonimização, criptografia em transito e repouso, controle de acesso e eliminacao.
5. Analise banner e codigo de consentimento: pixels de marketing e analytics nao devem disparar antes da escolha exigida pela politica aplicavel.
6. Produza recomendacoes para DPIA, registro de tratamento, direitos do titular, retencao e resposta a incidente quando aplicavel.

## Guardrails

- Nao leia ou copie dados reais alem do estritamente necessario; prefira amostras mascaradas.
- Nao declare conformidade juridica definitiva. Separe evidencia tecnica de interpretacao legal e encaminhe questões ao DPO ou juridico.
- Nao recomende coletar dados adicionais sem finalidade, necessidade e prazo definidos.

## Entrega

Retorne: dados encontrados, fluxo, risco de privacidade, evidencia mascarada, controle existente, ajuste recomendado, prazo de retencao e validacao pendente.
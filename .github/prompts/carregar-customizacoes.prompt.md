---
name: Carregar Customizacoes
description: "Localiza e aplica os agentes e skills de Copilot relevantes para a tarefa atual."
argument-hint: "Descreva a tarefa que deseja executar usando as customizacoes."
agent: agent
tools: [read, search]
---

Use este prompt como atalho para preparar a conversa com as customizacoes deste repositorio.

## Modos de carregamento

- **Modo seletivo (padrao):** carregue somente os agentes e skills relacionados a tarefa.
- **Modo completo:** se o usuario escrever `carregar todas`, `carregar tudo` ou equivalente, leia e apresente todas as customizacoes encontradas antes de executar a tarefa.

## Procedimento

1. Localize os arquivos em `.github/agents/` e `.github/skills/` no workspace atual.
2. Se o workspace nao tiver esses diretorios, procure os arquivos pessoais em `C:\Users\Gmtec\.copilot\agents\` e `C:\Users\Gmtec\.copilot\skills\`.
3. Leia as descricoes e, no modo seletivo, selecione somente os agentes e skills relacionados a tarefa informada pelo usuario.
4. No modo completo, leia todos os arquivos encontrados em `.github/agents`, `.github/skills`, `C:\Users\Gmtec\.copilot\agents` e `C:\Users\Gmtec\.copilot\skills`, removendo duplicatas por nome.
5. Use os agentes como personas especializadas e siga as instrucoes completas das skills carregadas.
6. No modo seletivo, nao carregue ou repita todas as instrucoes quando apenas uma parte for relevante.
7. Antes de agir, informe o modo usado e quais customizacoes foram carregadas.

## Prioridades

- Para implementar ou corrigir codigo, use `producao-codigo` e o agente de linguagem ou dominio adequado.
- Para seguranca, privacidade, LGPD, GDPR, OWASP ou CVEs, use o `Guardiao de Privacidade e Seguranca` e as skills de seguranca relevantes.
- Para auditoria de repositorio, diff, SAST, SCA ou IaC, use `analise-codigo-seguranca`.
- Para testes autorizados de API, headers ou DAST, use `validacao-dinamica`.
- Para dados pessoais, consentimento, logs ou retencao, use `conformidade-e-dados`.
- Para issues, code review, documentacao ou merge gate, use `governanca-seguranca`.
- Para politicas internas, memoria e logs de auditoria, use `contexto-seguranca`.

## Resultado esperado

Depois de selecionar as customizacoes, execute a tarefa do usuario seguindo as convencoes do projeto, valide a mudanca e informe quais agentes e skills foram usados.
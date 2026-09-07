---
name: analise-codigo-seguranca
description: "Analise repositorios, diffs, Pull Requests, resultados SAST, dependencias e IaC para encontrar riscos de seguranca. Use em auditorias de codigo, revisoes de PR, CVEs, Semgrep, SonarQube, Snyk, Checkmarx, Terraform, CloudFormation, Docker e Kubernetes."
argument-hint: "Informe o repositorio, diff, arquivos de resultado ou modulo a auditar."
user-invocable: true
---

# Analise de Codigo e Infraestrutura

## Objetivo

Produzir uma leitura tecnica rastreavel do codigo, historico e configuracao, traduzindo achados em risco, impacto e correcao.

## Procedimento

1. Identifique branch, commit, PR, arquivos alterados, linguagem, build e ambiente alvo.
2. Leia o codigo e o diff ao redor de cada mudanca; rastreie chamadas, dados, permissoes e dependencias.
3. Procure entradas externas, autenticacao, autorizacao por objeto, segredos, logs, serializacao e chamadas de processo.
4. Leia resultados de SAST e confirme cada achado no codigo antes de classificar falso positivo ou risco real.
5. Inspecione package.json, lockfiles, requirements, poetry, pom.xml, Gradle, csproj e manifests equivalentes para SCA.
6. Analise Terraform, CloudFormation, Bicep, Dockerfile, Kubernetes e CI/CD quanto a portas publicas, IAM excessivo, buckets abertos, imagens inseguras, secrets e criptografia ausente.

## Regras

- Nao invente resultados de scanners que nao foram executados.
- Classifique por severidade, explorabilidade, impacto, evidencia e alcance.
- Diferencie vulnerabilidade confirmada, risco potencial e informacao insuficiente.
- Nunca exponha segredos encontrados; mascare o valor e recomende rotacao imediata.

## Entrega

Para cada achado informe: severidade, arquivo e simbolo ou recurso, evidencia, impacto, caminho de exploracao, correcao e teste de verificacao. Termine com riscos residuais e comandos que ainda precisam ser executados.
# Copilot Customizacoes

Colecao de agentes customizados e Agent Skills para uso no GitHub Copilot dentro do VS Code. O repositorio pode ser usado no proprio workspace ou clonado em outro computador.

## Estrutura

```text
.github/
├── agents/     # Agentes customizados em arquivos .agent.md
└── skills/     # Skills reutilizaveis, cada uma com seu SKILL.md
```

Os agentes ficam em `.github/agents/` e as skills em `.github/skills/`. O VS Code detecta esses arquivos automaticamente quando este repositorio esta aberto como workspace.

## Agentes

### Engenheiro de Automacao

Especializado em Python, Ruby, PHP, Perl, Lua, Tcl, Bash, Zsh, Fish, PowerShell, Batch, Nushell, Awk, Sed, Make, CMake, Nix, Ansible, Terraform e HCL. Ajuda com scripts, build, infraestrutura, CI/CD, idempotencia, portabilidade e operacao segura.

### Engenheiro Backend

Especializado em C#, Java, Kotlin, Scala, Groovy, F#, Visual Basic, Dart server, Elixir, Erlang, Haskell, OCaml, Clojure, Lisp, Java EE e .NET. Analisa APIs, persistencia, contratos, concorrencia, filas, cache, observabilidade e seguranca.

### Engenheiro de Dados

Especializado em SQL, PostgreSQL, MySQL, MariaDB, SQLite, Oracle SQL, PL/SQL, T-SQL, PL/pgSQL, SAP HANA SQL, R, Julia, MATLAB, Octave, SAS, Stata, Wolfram Language, DAX, MDX, SPARQL, Cypher, Gremlin, GraphQL, HiveQL, Pig Latin e Spark SQL.

### Engenheiro Mobile e Jogos

Especializado em Swift, Objective-C, Objective-C++, Kotlin, Java Android, Dart, Flutter, Unity, Unreal Engine, Haxe, GDScript, Lua, Godot, Cocos2d, GLSL, HLSL, ShaderLab, Metal, WGSL e WebGPU. Considera ciclo de vida, memoria, bateria, frame time e experiencia do usuario.

### Engenheiro Poliglota

Atende linguagens, paradigmas e DSLs que nao estejam cobertos pelos demais agentes, incluindo Prolog, Mercury, Smalltalk, Pharo, Self, Gleam, Pony, Q#, Futhark, Idris, Agda, Coq, Lean, Factor, Forth, PostScript, Solidity, Vyper, Move, Cairo, Yul, Motoko, Clarity, Michelson, DAML, Modelica, QML, Promela, TLA+, Alloy, SMT-LIB, Rego, Dhall e Jsonnet.

### Engenheiro de Sistemas

Especializado em C, C++, C++/CLI, Rust, Go, Zig, D, Nim, V, Crystal, Ada, Fortran, COBOL, Pascal, Delphi, Modula-2, Oberon, Assembly, CUDA, OpenCL, GLSL, HLSL, Metal, Verilog, SystemVerilog, VHDL, Chisel, Bluespec, eBPF e WebAssembly.

### Engenheiro Web

Especializado em JavaScript, TypeScript, JSX, TSX, HTML, XHTML, CSS, Sass, SCSS, Less, Stylus, PostCSS, WebAssembly, PHP, Ruby, Dart, Elm, PureScript, ReasonML, ReScript, ClojureScript, CoffeeScript, Haml, Pug, Handlebars, Jinja, Twig, Liquid, Astro, Svelte, Vue, Angular, React, Solid, Qwik e Web Components.

### Guardiao de Privacidade e Seguranca

Atua como arquiteto de seguranca e DPO tecnico. Analisa LGPD, GDPR, OWASP, Zero Trust, RBAC, ABAC, autenticacao, autorizacao, IDOR, criptografia, segredos, logs, auditoria, threat modeling, DevSecOps e resposta a incidentes.

## Skills

### producao-codigo

Workflow geral para implementar, corrigir, refatorar, revisar e otimizar C, C++, C#, JavaScript, Python e SQL. Orienta a entender requisitos, localizar o ponto de controle, fazer mudancas pequenas e validar com testes, build, lint e typecheck.

### analise-codigo-seguranca

Le repositorios, diffs, Pull Requests, resultados de SAST, dependencias e IaC. Ajuda a interpretar Semgrep, SonarQube, Snyk e Checkmarx, alem de revisar Terraform, CloudFormation, Bicep, Docker, Kubernetes e configuracoes publicas.

### governanca-seguranca

Orienta a criar issues de seguranca, comentarios de code review, atualizacoes em `SECURITY.md` e `README.md`, alem de definir criterios para solicitar bloqueio de merge. Exige evidencia e autorizacao antes de alterar sistemas externos ou status de PR.

### validacao-dinamica

Orienta testes autorizados em homologacao com HTTPie, Postman, OWASP ZAP e Burp Suite. Verifica autenticacao, RBAC, IDOR, respostas 401/403, TLS, CORS, cookies e headers como CSP, HSTS e X-Frame-Options.

### conformidade-e-dados

Analisa dados pessoais, logs, cookies, consentimento, retencao, anonimização, pseudonimizacao, criptografia e data mapping sob LGPD e GDPR. Tambem orienta DLP e DPIA sem expor dados reais.

### contexto-seguranca

Organiza consultas a documentacao interna, politicas, OWASP, LGPD, GDPR, PCI DSS, Marco Civil, memoria do projeto e logs de auditoria em fontes como Notion, Confluence, Splunk, Datadog e CloudWatch.

## Como usar no VS Code

1. Abra este repositorio no VS Code.
2. Abra o Copilot Chat.
3. Use `/agents` para selecionar ou configurar agentes.
4. Use `/skills` para listar as skills.
5. Tambem e possivel pedir diretamente, por exemplo: `use a skill validacao-dinamica para revisar esta API`.
6. Se uma customizacao nao aparecer, execute `Developer: Reload Window`.

## Atalho para carregar agentes e skills

O repositorio possui o prompt reutilizavel `.github/prompts/carregar-customizacoes.prompt.md`. Ele aparece no Copilot Chat como:

```text
/carregar-customizacoes
```

Use o atalho informando a tarefa. No modo seletivo, o Copilot localiza e aplica somente as customizacoes relacionadas ao pedido:

```text
/carregar-customizacoes corrigir este codigo Python e criar testes
/carregar-customizacoes revisar a seguranca desta API
/carregar-customizacoes analisar este Pull Request em busca de CVEs
```

Para carregar todas as skills e agents disponiveis, use explicitamente as palavras `carregar todas` ou `carregar tudo`:

```text
/carregar-customizacoes carregar todas as skills e agents
```

No modo completo, o atalho procura:

- agentes em `.github/agents/`;
- skills em `.github/skills/`;
- agentes pessoais em `C:\Users\Gmtec\.copilot\agents\`;
- skills pessoais em `C:\Users\Gmtec\.copilot\skills\`.

As duplicatas entre o workspace e o perfil pessoal devem ser consideradas uma única customização. O Copilot informa o modo usado e os arquivos carregados antes de executar a tarefa.

### Se o atalho nao aparecer

1. Confirme que o arquivo existe em `.github/prompts/carregar-customizacoes.prompt.md`.
2. No VS Code, pressione `Ctrl + Shift + P`.
3. Execute `Developer: Reload Window`.
4. Abra o Copilot Chat e digite `/carregar-customizacoes`.
5. Alternativamente, use `Chat: Run Prompt...` na Command Palette.

O modo completo pode consumir mais contexto. Para tarefas normais, prefira o modo seletivo e carregue tudo somente quando precisar revisar ou consultar a coleção inteira.

## Usar em outros computadores

Clone o repositorio:

```powershell
git clone https://github.com/GMasc06/copilot-customizacoes.git
cd copilot-customizacoes
code .
```

Para instalar os agentes e skills globalmente no perfil do usuario:

```powershell
New-Item -ItemType Directory -Force "$HOME\.copilot\agents"
New-Item -ItemType Directory -Force "$HOME\.copilot\skills"
Copy-Item ".github\agents\*.agent.md" "$HOME\.copilot\agents\" -Force
Get-ChildItem ".github\skills" -Directory | ForEach-Object {
    Copy-Item $_.FullName "$HOME\.copilot\skills\" -Recurse -Force
}
```

Depois, recarregue o VS Code. Os agentes ficam em `~/.copilot/agents` e as skills em `~/.copilot/skills`.

## Atualizar depois de uma mudanca

Na pasta do repositorio:

```powershell
git add .github README.md
git commit -m "Atualiza customizacoes do Copilot"
git push
```

## Seguranca

Nao publique tokens, senhas, chaves, logs pessoais ou a pasta inteira `.copilot`. Este repositorio deve conter apenas os arquivos de agentes, skills e documentacao que podem ser compartilhados.

As skills de seguranca orientam analises tecnicas, mas nao substituem DPO, assessoria juridica, aprovacao de mudanca ou autorizacao formal para testes de seguranca.
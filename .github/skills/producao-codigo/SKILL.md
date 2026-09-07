---
name: producao-codigo
description: 'Produza, altere e revise codigo em C, C++, C#, JavaScript, Python e SQL com um workflow orientado a requisitos, contexto local, testes, qualidade e seguranca. Use quando o usuario pedir implementar, corrigir, refatorar, revisar ou otimizar codigo nessas linguagens.'
argument-hint: 'Descreva o requisito, o comportamento esperado e o arquivo ou modulo afetado.'
user-invocable: true
---

# Producao de Codigo

## Objetivo

Entregar mudancas pequenas, compreensiveis e verificadas, preservando as convencoes do projeto e evitando alteracoes fora do escopo.

## Quando usar

- Implementar uma funcionalidade ou endpoint.
- Corrigir um bug ou comportamento inesperado.
- Refatorar codigo sem mudar o contrato observavel.
- Revisar codigo quanto a bugs, riscos, regressao e testes ausentes.
- Otimizar desempenho, uso de memoria ou consultas SQL.
- Trabalhar em C, C++, C#, JavaScript, Python ou SQL.

## Procedimento

### 1. Entender o resultado

1. Reescreva mentalmente o pedido como comportamento observavel.
2. Identifique entradas, saidas, erros esperados, efeitos colaterais e limites.
3. Se faltar uma informacao que muda a implementacao, faca uma pergunta objetiva; caso contrario, declare a suposicao e avance.

### 2. Encontrar o ponto de controle

1. Localize o arquivo, simbolo, teste, comando ou mensagem de erro mais proximo do problema.
2. Leia apenas o contexto necessario para entender quem decide, transforma ou persiste o comportamento.
3. Procure testes, chamadas e tipos adjacentes antes de introduzir uma nova abstracao.
4. Confirme uma hipotese falsificavel e escolha uma verificacao barata que possa refuta-la.

### 3. Escolher a abordagem

- Para bug: reproduza ou crie um caso minimo antes de corrigir a causa raiz.
- Para funcionalidade: defina primeiro o contrato e os caminhos de erro.
- Para refatoracao: preserve a API e valide equivalencia antes de melhorar a estrutura.
- Para desempenho: meça o caminho relevante antes e depois; nao substitua legibilidade por micro-otimizacao sem evidencia.
- Para SQL: verifique cardinalidade, nulos, transacoes, concorrencia, indices e parametros; nunca concatene entrada do usuario.

### 4. Implementar

1. Faça a menor alteracao que satisfaca o comportamento.
2. Siga o estilo, APIs, dependencias, tratamento de erros e convencoes ja existentes.
3. Valide entradas nas fronteiras e mantenha mensagens de erro uteis sem expor segredos.
4. Preserve compatibilidade quando o pedido nao autorizar mudanca de contrato.
5. Adicione ou ajuste testes para o caso principal, limites e regressao corrigida.

### 5. Validar

Execute, nesta ordem, o que estiver disponivel no projeto:

1. O teste mais estreito que cobre a mudanca.
2. Testes de integracao ou fluxo afetado.
3. Compilacao, typecheck, lint e formatacao.
4. Suite completa, quando o custo e o ambiente permitirem.

Quando uma etapa nao puder ser executada, informe o comando e o motivo. Nao declare sucesso apenas por inspeção visual.

### 6. Revisar a entrega

Antes de concluir, confirme:

- O requisito e os caminhos de erro estao cobertos.
- A mudanca nao introduz comportamento inseguro, vazamento de segredo ou injecao.
- Recursos sao liberados: memoria, arquivos, handles, conexoes, transacoes e processos.
- A concorrencia e o cancelamento foram considerados quando aplicaveis.
- Tipos, nulos, overflow, limites, encoding e compatibilidade foram tratados conforme a linguagem.
- Testes e documentacao foram atualizados quando o contrato ou uso mudou.
- O diff contem apenas mudancas relacionadas ao pedido.

## Orientacoes por linguagem

- **C:** trate ownership manual, limites de buffer, overflow, retorno de erro e liberacao em todos os caminhos.
- **C++:** prefira RAII, ownership explicito e a biblioteca padrao; evite `new`/`delete` manuais quando smart pointers resolverem.
- **C#:** use anulabilidade e tipos fortes; observe async, cancelamento, disposicao de recursos e validacao de entrada.
- **JavaScript:** preserve async/await, trate rejeicoes de Promise, valide dados externos e mantenha compatibilidade do runtime.
- **Python:** use tipos e context managers quando ajudarem, diferencie excecoes recuperaveis e bugs, e evite efeitos colaterais ocultos.
- **SQL:** use consultas parametrizadas, transacoes explicitas quando necessarias e valide o plano de execucao para mudancas de desempenho.

## Formato da resposta

Ao concluir, informe de forma concisa:

1. O que mudou e por que.
2. Quais arquivos ou contratos foram afetados.
3. Quais validacoes foram executadas e seus resultados.
4. Quais limites, riscos ou validacoes pendentes permanecem.
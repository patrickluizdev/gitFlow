---

# Templates

<br>

## Utilização

Para utilizar o template, siga as instruções abaixo:

1. Crie um diretório chamado `.github` na raiz do seu repositório.
2. Dentro do diretório `.github`, crie um arquivo chamado `PULL_REQUEST_TEMPLATE.md`.
3. Agora você pode adicionar o conteúdo [Orientações para Pull Requests](https://github.com/patrickluizdev/gitFlow/blob/feature/template/Pull%20Requests.md) ao arquivo `PULL_REQUEST_TEMPLATE.md`, que servirá como modelo para os pull requests no seu repositório.

<br>

# [Orientações para Pull Requests](https://github.com/patrickluizdev/gitFlow/blob/feature/template/Pull%20Requests.md)

## Descrição da Feature

Esta seção deve conter um resumo claro e conciso da mudança proposta neste pull request. Explique o problema que está sendo corrigido ou a funcionalidade que está sendo adicionada. Inclua também informações sobre a motivação por trás dessas alterações.

## Problema Corrigido

Descreva o problema específico que está sendo abordado por este pull request. Explique o cenário em que o problema ocorre e por que é necessário corrigi-lo. Se houver um problema registrado ou conhecido relacionado a essa questão, faça referência a ele aqui.

## Motivação e Contexto

Forneça uma explicação detalhada sobre a motivação por trás deste pull request. Explique como essa alteração beneficia o projeto, os usuários ou outras partes interessadas. Forneça contexto relevante, como informações sobre o fluxo de trabalho atual, limitações existentes ou requisitos específicos que influenciaram a abordagem adotada.

## Dependências

Se houver dependências específicas para este pull request, como outras alterações de código, pacotes ou bibliotecas externas, mencione-as nesta seção. Isso ajudará a identificar quaisquer pré-requisitos necessários para que essa alteração funcione corretamente.

## Como isso foi testado?

Descreva os testes que foram realizados para verificar as alterações feitas neste pull request. Inclua detalhes sobre a configuração de teste e os resultados obtidos. Certifique-se de mencionar qualquer teste automatizado, testes manuais ou outras estratégias de verificação que tenham sido aplicadas.

- [x] Teste A
- [x] Teste B

## Informações adicionais:

- [x] Meu código segue as diretrizes de estilo deste projeto
- [x] Eu revisei meu próprio código
- [x] Eu comentei o meu código, especialmente em áreas de difícil compreensão
- [x] Eu fiz as alterações correspondentes na documentação
- [x] Minhas alterações não geram novos avisos
- [x] Quaisquer alterações dependentes foram mescladas e publicadas em módulos dependentes



<br>
<br>

---

<br>

# [Orientação para Commits Semânticos](https://github.com/patrickluizdev/gitFlow/blob/feature/template/Commits%20Sem%C3%A2nticos.md)

## Feat:

> Nova Feature no projeto, exemplo: Funcionalidade, serviço, endpoint, etc...

---

## Refactor:

> Refatoração de Alguma parte do código.

---

## Fix:

> Correção de erros que estão causando bugs.

---

## Chore:

> Mudanças que não influenciam o sistema nem arquivos de teste, exemplo:
>
> - Adicionar arquivos ao git ignore, mudanças no eslint, etc...

---

## Style:

> Mudanças de formatação ou estilo de código que não influenciam na lógica do sistema.

---

## Build:

> Mudanças que impactam no processo de build.

---

## Teste:

> Criação ou alteração de algum código de teste.

---

## Perf:

> Alteração feita para melhorar a performance do projeto, exemplo:
>
> - Melhorar a query do banco de dados, deixar uma função mais performática, etc...

---

### Docs:

> Alterações na documentação do projeto, exemplo:
>
> - readme, swagger, etc ...

# Templates

<br>

## Utilização

Para utilizar o template, siga as instruções abaixo:

1. Crie um diretório chamado `.github` na raiz do seu repositório.
2. Dentro do diretório `.github`, crie um arquivo chamado `PULL_REQUEST_TEMPLATE.md`.
3. Agora você pode adicionar o conteúdo [Orientações para Pull Requests](https://github.com/patrickluizdev/gitFlow/edit/develop/Pull%20Requests.md) ao arquivo `PULL_REQUEST_TEMPLATE.md`, que servirá como modelo para os pull requests no seu repositório e automaticamente a estrutura será montada como no exemplo.

![Exemple Pull Request](https://raw.githubusercontent.com/patrickluizdev/gitFlow/develop/src/exemple%20pull.jpg)

<br>

# [Orientações para Pull Requests](https://raw.githubusercontent.com/patrickluizdev/gitFlow/develop/Pull%20Requests.md)

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

# [Utilização das Branches com Git Flow](https://github.com/patrickluizdev/gitFlow/edit/develop/gitFlow.md)

O Git Flow é um modelo de fluxo de trabalho que utiliza branches para organizar o desenvolvimento de um projeto. Ele fornece uma estrutura clara para trabalhar em diferentes funcionalidades, correções de bugs e lançamentos.

## Branches Principais

### Master

- A branch `master` é a branch principal do projeto.
- Ela representa a versão estável e produção do código.
- Commits nesta branch são normalmente feitos através de merges de outras branches, como a branch `release` ou `hotfix`.

### Hotfix - Bug

- A branch `hotfix` é usada para correção rápida de bugs críticos em produção.
- Ela é criada a partir da branch `master`.
- Commits nesta branch são mesclados tanto para a branch `master` quanto para a branch `develop`.

### Release

- A branch `release` é usada para preparar a próxima versão de lançamento.
- Ela é criada a partir da branch `develop`.
- Nesta branch, podem ser feitas correções finais e ajustes antes de ser mesclada com a branch `master`.
- Commits nesta branch são mesclados tanto para a branch `master` quanto para a branch `develop`.

## Branches de Suporte

### Develop

- A branch `develop` é usada para desenvolver novas funcionalidades.
- Ela é criada a partir da branch `master`.
- É a branch onde as funcionalidades são integradas e testadas antes de serem lançadas.
- Commits nesta branch são mesclados para a branch `release` ou para branches de funcionalidades.

### Feature

- A branch `feature` é usada para desenvolver uma nova funcionalidade específica.
- Ela é criada a partir da branch `develop`.
- Cada funcionalidade é desenvolvida em uma branch `feature` separada.
- Commits nesta branch são mesclados para a branch `develop` quando a funcionalidade estiver pronta.

## Fluxo de Trabalho

1. Crie uma nova branch `feature` para cada nova funcionalidade que você estiver trabalhando:

   ```
   git checkout -b feature/nome-da-funcionalidade develop
   ```

2. Desenvolva e faça commits na branch `feature` enquanto trabalha na funcionalidade.

3. Quando a funcionalidade estiver concluída, faça o merge da branch `feature` para a branch `develop`:

   ```
   git checkout develop
   git merge --no-ff feature/nome-da-funcionalidade
   ```

4. Quando for lançar uma nova versão, crie uma branch `release` a partir da branch `develop`:

   ```
   git checkout -b release/versao-x.y.z develop
   ```

5. Realize os ajustes finais e testes na branch `release`.

6. Faça o merge da branch `release` para a branch `master` e crie uma tag para a versão:

   ```
   git checkout master
   git merge --no-ff release/versao-x.y.z
   git tag -a versao-x.y.z
   ```

7. Se necessário, faça o merge da branch `release` de volta para a branch `develop`:

   ```
   git checkout develop
   git merge --no-ff release/versao-x.y.z
   ```

8. Para correção rápida de bugs críticos em produção, crie uma branch

`hotfix` a partir da branch `master`:

```
git checkout -b hotfix/nome-do-bug master
```

9. Faça os ajustes necessários e faça o merge da branch `hotfix` para a branch `master` e `develop`:

   ```
   git checkout master
   git merge --no-ff hotfix/nome-do-bug
   git checkout develop
   git merge --no-ff hotfix/nome-do-bug
   ```

10. Por fim, delete as branches `feature`, `release` e `hotfix` quando elas não forem mais necessárias:
    `   git branch -d feature/nome-da-funcionalidade
 git branch -d release/versao-x.y.z
 git branch -d hotfix/nome-do-bug`
    Lembre-se de adaptar o fluxo de acordo com as necessidades do seu projeto.

<br>
<br>

---

<br>

# [Orientação para Commits Semânticos](https://github.com/patrickluizdev/gitFlow/edit/develop/Commits%20Sem%C3%A2nticos.md)

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

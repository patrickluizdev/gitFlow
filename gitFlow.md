# Utilização das Branches com Git Flow

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
    `    git branch -d feature/nome-da-funcionalidade
    git branch -d release/versao-x.y.z
    git branch -d hotfix/nome-do-bug
   `
    Lembre-se de adaptar o fluxo de acordo com as necessidades do seu projeto.

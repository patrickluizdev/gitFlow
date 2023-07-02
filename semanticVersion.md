# Tutorial: Utilização de Semantic Version em Projetos

O Semantic Versioning (ou Versionamento Semântico) é uma convenção para versionamento de software que segue um conjunto de regras para atribuir números de versão significativos a um projeto. Neste tutorial, você aprenderá como utilizar o Semantic Versioning em seus projetos.

## O que é o Semantic Versioning?

O Semantic Versioning segue um padrão de três partes para a numeração de versões: MAJOR.MINOR.PATCH. Cada parte possui um significado específico:

- MAJOR: Incrementado quando ocorrem alterações incompatíveis na API do software.
- MINOR: Incrementado quando novas funcionalidades são adicionadas ao software, mas mantendo compatibilidade com as versões anteriores.
- PATCH: Incrementado quando são feitas correções de bugs no software, sem adição de novas funcionalidades ou alterações incompatíveis.

Além dessas partes obrigatórias, é possível utilizar rótulos adicionais, como pré-lançamentos (pre-release) e metadados (metadata), para indicar estágios de desenvolvimento ou informações extras sobre a versão.

## Como utilizar o Semantic Versioning?

Para utilizar o Semantic Versioning em seu projeto, siga as seguintes práticas:

1. **Defina a versão inicial**: Inicie seu projeto com a versão 1.0.0 para indicar o primeiro lançamento estável.

2. **Incremente a versão corretamente**: Ao fazer alterações no projeto, siga as regras do Semantic Versioning para incrementar a versão corretamente. Veja alguns exemplos:

   - Ao adicionar novas funcionalidades compatíveis, incremente o número MINOR (exemplo: 1.1.0).
   - Ao corrigir bugs, incremente o número PATCH (exemplo: 1.0.1).
   - Ao fazer alterações incompatíveis, incremente o número MAJOR e redefina os números MINOR e PATCH para zero (exemplo: 2.0.0).

3. **Utilize pré-lançamentos e metadados, se necessário**: Caso você queira indicar versões em estágios de desenvolvimento ou adicionar informações extras, utilize pré-lançamentos e metadados. Exemplos:

   - Versão de pré-lançamento: 1.1.0-beta.1
   - Versão com metadados: 2.0.0+20230526

4. **Documente as alterações**: Mantenha um arquivo de changelog para registrar as alterações feitas em cada versão, facilitando a compreensão das mudanças para os usuários.

## Conclusão

Utilizar o Semantic Versioning em seus projetos é uma prática recomendada para fornecer informações claras e consistentes sobre as versões do software. Seguir as regras de incremento de versão adequadas permite que os usuários entendam as alterações realizadas e ajuda na compatibilidade entre as diferentes versões do seu projeto.

Lembre-se de documentar corretamente as alterações em um arquivo de changelog e comunicar as versões de forma clara aos usuários.

> > ### [Semantic Version Official](https://semver.org/lang/pt-BR/)

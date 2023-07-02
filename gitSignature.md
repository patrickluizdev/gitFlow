# Tutorial: Utilizando o Git com Assinaturas

Neste tutorial, você aprenderá como configurar e usar o Git com assinaturas. Adicionar assinaturas aos seus commits no Git pode ajudar a verificar a autenticidade de suas contribuições e fornecer uma camada adicional de confiança.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Git instalado em sua máquina.
- Um repositório de código com o qual deseja trabalhar.

## Passo 1: Gerar um Par de Chaves GPG

Para usar assinaturas com o Git, você precisará de um par de chaves GPG. Siga estes passos para gerar uma:

1. Abra um terminal ou prompt de comando.
2. Execute o seguinte comando para gerar um novo par de chaves GPG:
   ```
   gpg --full-generate-key
   ```
3. Siga as instruções para configurar sua chave, incluindo fornecer um nome e um endereço de e-mail.
4. Escolha uma senha para proteger sua chave privada. Certifique-se de que seja forte e memorável.

Depois de gerar o par de chaves, anote o ID ou a impressão digital da chave, pois você precisará dele posteriormente.

## Passo 2: Verificar e Exportar as Chaves GPG

Após gerar a chave, você pode verificar suas chaves GPG e exportar a chave pública para adicioná-la ao GitHub ou outros serviços.

1. Abra um terminal ou prompt de comando.
2. Execute o seguinte comando para verificar as chaves em sua máquina:

   ```
   gpg --list-secret-key --keyid-form LONG
   ```

   Anote o ID da chave que você gerou.

3. Execute o seguinte comando para exportar a chave pública em formato ASCII:

   ```
   gpg --armor --export $ID
   ```

   Substitua `$ID` pelo ID da chave que você anotou.

4. Copie a saída do comando `gpg --armor --export $ID`. Você poderá adicionar essa chave pública aos serviços que suportam assinaturas GPG, como o GitHub.

## Passo 3: Configurar o Git para Usar sua Chave GPG

Agora que você tem um par de chaves GPG, precisa configurar o Git para usá-lo para assinar commits.

1. Abra um terminal ou prompt de comando.
2. Execute os seguintes comandos para configurar o Git:
   ```
   git config --global user.signingkey $ID
   git config --global commit.gpgsign true
   git config --global tag.gpgSign true
   ```
   Substitua `$ID` pelo ID da chave que você anotou.

## Passo 4: Inicializar Automaticamente a Chave GPG (opcional)

Se você quiser inicializar automaticamente sua chave GPG ao abrir um novo terminal, siga estas etapas:

1. Abra um terminal ou prompt de comando.
2. Execute o seguinte comando para editar o arquivo `.bash_profile`:
   ```
   nano ~/.bash_profile
   ```
3. Adicione a seguinte linha ao arquivo `.bash_profile`:
   ```
   export GPG_TTY=$(tty)
   ```
4. Pressione `Ctrl + X`, digite `Y` para salvar as alterações e pressione `Enter` para confirmar.

Agora sua chave GPG será inicializada automaticamente ao

abrir um novo terminal.

## Passo 5: Verificar Commits Assinados

Você pode verificar as assinaturas em seus commits para garantir sua autenticidade.

1. Abra um terminal ou prompt de comando.
2. Navegue até o repositório de código.
3. Execute o seguinte comando para verificar as assinaturas:
   ```
   git log --show-signature
   ```

O Git exibirá o histórico de commits, incluindo informações sobre as assinaturas e sua validade.

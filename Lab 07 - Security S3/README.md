# Lab 07 - Security S3

## 1. Criação do bucket

1. Acesse o painel do S3 clicando em S3 na parte de Storage.

![Image 01](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-01.png)

2. Para esse tutorial vamos criar um bucket. Clique em **Create bucket**

![Image 02](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-02.png)

3. Escolha um nome único para seu bucket. Para o tutorial utilizei “bucket-tutorial-solvimm” como nome do bucket.
Escolha a região onde a bucket vai ser criado. Clique **Next**

![Image 03](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-03.png)

4. Somos direcionados para essa tela que nos fornece diversas opções, como versionamento automático do bucket, registro de logs de acesso, tags, assim como a possibilidade de encriptar os objetos do bucket. Para nosso exemplo não vai ser preciso utilizar esses recursos portanto basta clicar em **Next**.

![Image 04](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-04.png)

5. Note que todos os buckets são configurados para bloquear acesso público durante sua criação. Para que um bucket fique público é necessário que o usuário, com as devidas permissões, realize essa modificação.
Lembramos que essa ação é considerada falha grave de segurança já que expõe seus dados para a internet.
Clique **Next**. Revise as informações na tela e clique **Create bucket**.

![Image 05](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-05.png)

## 2. Access Control List

1. Vamos acessar o bucket e verificar as suas configurações.
Clique em cima do nome no bucket criado.

![Image 06](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-06.png)

2. Após acessar o bucket somos direcionados para o local onde os arquivos são armazenados. Já que acabamos de criar o bucket não existe nenhum arquivo dentro dele. Clique em **Permissions**

![Image 07](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-07.png)

3. Existem 4 configurações dentro de permissions que podemos modificar. A primeira, **Block public access** nos possibilita modificar a visibilidade do bucket. Podemos deixar ele público ou privado. Em nosso exemplo o bucket esta privado. Clique em **Access Control List**.

![Image 08](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-08.png)

4. A segunda, **Access Control List** é utilizado para dar permissão de leitura/escrita para alguma conta AWS. Vamos levar em consideração que gostaríamos de conceder permissão para uma determinada conta para apenas escrever os objetos dentro de nosso bucket. Clique em **Add account** Coloque o email associado a conta que gostaria de dar essa permissão Clique em **Write objects**.

![Image 09](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-09.png)

5. Clique em **Save** para salvar as configurações. O acesso para escrever os objetos nesse bucket utilizando outra conta AWS foi permitido com sucesso

![Image 10](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-10.png)

## 3. Bucket Policy

1. Na parte de **Bucket Policy** podemos dar diferentes permissões para os recursos da AWS. Utilizando JSON como linguagem. Existem diversas políticas que podíamos incluir, como Adição de uma política de bucket para exigir MFA, Conceder permissão a uma identidade de origem do Amazon CloudFront, Restringir o acesso a um indicador HTTP específico, Permitir endereços IPv4 e IPv6, entre outros.

![Image 11](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-11.png)

2. Coloque a política para exigir a adição do MFA no S3. Clique em **Save**

![Image 12](https://d1b7vbmva6nnec.cloudfront.net/lab07/lab-07-security-12.png)

# Backup em Bancos de Dados no Postgresql

Neste tutorial iremos falar sobre backups em Bases de dados e mostraremos um exemplo prático de como podemos fazê-los. [Aqui](https://youtu.be/6gSQRxe1PW8) é possível assistir esse tutorial em vídeo no nosso canal do Youtube.

O backup do PostgreSQL é importante pois existe para auxiliar na prevenção de perda de dados, como registros apagados acidentalmente por falha física ou humana.

Este procedimento garante a manutenção da integridade dos dados, além de ser muito útil em migração de servidores ou quando ocorre problema em um servidor.

### Fazendo Backup

Para fazer o backup dos dados no pgAdmin, basta escolher em qual banco de dados será feito o backup, ao escolher deve-se abrir as opções dele e escolher a opção **Backup**. Após fazer isso, abrirá uma janela como a que é apresentada abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Backup%20em%20Banco%20de%20Dados%20no%20Postgresql/Imagens/Imagem01.png)

Nessa aba, em **Filename** deve-se definir o caminho, o nome e a formatação do arquivo de backup, em **Format** deve-se escolher o formato dos dados, como por exemplo **Plain**, em **Encoding** e **Rolename** deve-se selecionar a mesma do banco no qual está sendo feito o backup.

Após isso ao passar para a aba de **Dump Options #1** deve-se selecionar os dados que serão armazenados em backup, como na imagem abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Backup%20em%20Banco%20de%20Dados%20no%20Postgresql/Imagens/Imagem02.png)

Na aba de **Dump Options #2**, deve-se selecionar as Queries que serão salvas no backup, como é apresentado na imagem abaixo.

1[](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Backup%20em%20Banco%20de%20Dados%20no%20Postgresql/Imagens/Imagem03.png)

Após serem feitas todas as configurações basta clicar em **Backup** que o backup será feito.

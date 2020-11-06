# DB Link

Neste tutorial iremos falar sobre os links entre Bases de dados. [Aqui]() é possível assistir esse tutorial em vídeo no nosso canal do Youtube.

Um link de banco de dados é um ponteiro que define um caminho de comunicação unilateral de um servidor de banco de dados para outro servidor de banco de dados. Uma conexão de link de banco de dados permite que usuários locais acessem dados em um banco de dados remoto. 

### Criando as bases de dados

Para utilizar como exemplo nesse tutorial, iremos criar duas bases de dados com os comandos abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20DBLink/Imagens/Imaagem01.png)

### Abilitando o DBLink

Para que seja possível utilizar o Dblink em uma base de dados, é necessário criar uma exteção.

Executamos o comando abaixo na base de dados **B**, para que seja possível conectá-la a  base de dados **A**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20DBLink/Imagens/Imagem02.png)

### Criando a conexão

Agora que temos o serviço do Dblink habilitado na base de dados, é possível fazer a conexão da base de dados **B** com a base de dados **A**.

Para isso iremos utilizar o comando abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20DBLink/Imagens/Imagem03.png)

Na primeira parte do comando fazemos a conexão com a base de dados **A**, passando o host, user, password e o dbname da base de dados **A**. Na segunda parte passamos a consulta que queremos fazer na base de dados **A**, que no caso é os usuários que   têm acesso a essa base de dados. Por fim, dizemos que o tipo de retorno é do tipo text. 

### Resultado

O resultado da consulta apresentada anteriormente é apresentado abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20DBLink/Imagens/Imagem04.png)

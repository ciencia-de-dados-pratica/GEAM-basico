# Introdução a Banco Orientado a Documentos
### Introdução
  * Os bancos orientados a documentso são bancos NoSQL, que são modelos onde o SQL não é utilizado para sua operações como inserção, remoção, atualização entre outras.
  O modelo orientado a documentos utiliza documentos do tipo JSON para seu armazenamento de dados se tornando mais flexível, semiestruturado e hieráquico. Criando uma
  time line de todos os documentos criados.
### MongoDB + Compass
  * O MongoDB é um banco de dados orientado a documento, um dos mais utilizados no mundo todo, pois ele dispôe de inúmeras funcionalidades que outros bancos da mesma categoria
  não possuem. Ele é de código aberto, então sua utilização é gratuita utilizando somente na própria máquina, caso seja necessário utilzar um serviço em nuvem, algumas coisas
  passam a ser pagas para ter uma melhor experiência de serviço. E também é multiplataforma, possibiliatando vários usuários realizarem alterações no banco, mas, somente de forma
  online, usando o MogoDB Atlas, onde é possível criar clusters, e cada um desses clusters pode ser utilizado de várias formas, mas lembre-se, cluters com maior capacidade de
  memória são pagos.
  * O Compass é uma das GUIs do MongoDB facilitando a sua utilização, para evitar ficar dependente do terminal para criar os bancos de dados e inserir informações nele. Uma outra GUI
  do MongoDB muito utilizada é o [Robo3T](https://robomongo.org/).
### Instalando o ambiente
  * Para instalar o MongoDB em sua máquina é muito simples, basta ir no site oficial em Docs, escolher a versão do mongo e [instalar](https://docs.mongodb.com/manual/installation/)
  conforme o sistema operacional utilizado. É recomendado usar a versão estável para não ter problemas com o software.
  * Após realizar a intalação, é necessário dar start nos serviços do MongoDB.
  * Depois disso iremos intalar o Compass, isso no mesmo site, basta ir em Software > Compass > Try it now, selecionar a versão (recomendado a estável) o sistema operacional e tipo
  de pacote, e clicar em [donwload](https://www.mongodb.com/try/download/compass).
 
### Criando um Database
  * Abrindo o Compass, na opção "Fill in conecction fields individually" já vem por padrão localhost e a porta que o MongoDB utiliza, basta clicar em connect.
  * Por padrão, já vem alguns bancos criados só para vermos que está funcionando normalmente.
  * Em "Create Database" podemos criar um novo banco, preenchendo os campos Database Name (nome do banco de dados) e Collection Name (o nome da nossa coleção). Como o modelo orientado
  a documentos é NoSQL, utilizamos as colecitions que correspondem as tables do modelo relacional. Dessa forma, na minha collection eu posso armazenar qualquer coisa, como clientes,
  produtos, compras, entre outras.
  * Após criar a collection, clicamos no nome atribuido a ela, após isso, vamos adicionar um documento clicando em Add Data. Nessa opção temos duas formas de armazenar, criando um documento
  com toda a estrutura JSON, ou apenas clicando na opção de inserção, onde digitamos só os dados, sem usar as definições do JSON.
  * Posteriormente, é só clicar em insert. Assim temos nosso primeiro banco orientado a documentos criado, com nossa primeria collection :).

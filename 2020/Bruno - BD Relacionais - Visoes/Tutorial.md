# Visões em Bancos de Dados Relacionais

Neste tutorial iremos fazer uma introdução sobre as consultas SQL e serão apresentadas algumas consultas básicas, [aqui](https://www.youtube.com/watch?v=8OUp7J0LEms) é possível assistir a esse tutorial em vídeo no nosso canal do Youtube. 

Uma visão é uma tabela “virtual” que não faz parte do conjunto das tabelas reais de um banco de dados, mas é visível para os usuários como tal.
As visões servem como forma de restringir o acesso de usuários a apenas uma parte das tabelas do Banco de Dados.Também, servem como meio de reorganizar a informação para melhor apresentação ou para facilitar sua “visão” para determinados usuários.

Para este tutorial iremos criar e povoar a tabela **Amigos**, para ser utilizada como exemplo.  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20BD%20Relacionais%20-%20Visoes/Imagens/criacao-da-tabela.png)

### Criação da Visão
Com base na tabela acima iremos criar uma visão. O comando de criação da visão é: **CREATE VIEW** em seguida o nome que quero dar a visão, **as** e a condição de seleção que irá formar a visão.

Para este exemplo, iremos criar a visão **Aniversarios**.  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20BD%20Relacionais%20-%20Visoes/Imagens/criacao-da-visao.png)

### Consultas
Assim como nas tabelas físicas do Banco de Dados, também é possível fazer consultas nas visões, como é mostrado no exemplo abaixo.  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20BD%20Relacionais%20-%20Visoes/Imagens/consulta.png)

### Atualização
É possível atualizar os valores da visão, como é mostrado abaixo.  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20BD%20Relacionais%20-%20Visoes/Imagens/atualizacao.png)

### Exclusão de valores
O comando abaixo apresenta a exclusão de uma tupla da visão.  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20BD%20Relacionais%20-%20Visoes/Imagens/delete.png)

### Exclusão da visão
É possível excluir uma visão do Banco de Dados, utilizando o comando abaixo.  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20BD%20Relacionais%20-%20Visoes/Imagens/drop.png)




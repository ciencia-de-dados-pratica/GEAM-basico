# Consultas SQL

Neste tutorial iremos falar sobre as consultas SQL. A linguagem de consulta de dados é usada para, fazer o que o nome diz, consultas, extrair informações de um banco de dados. É importante que essas consultas aconteçam sem causar mudanças no banco de dados, caso contrário dados valiosos poderiam ser prejudicados. 

## Definição das tabelas

Para a realização das consultas iremos utilizar as tabelas Clientes e Fiado como apresentado abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas-SQL/Imagens/Criacao.png)  

A seguir são apresentadas as inserções realizadas nas tabelas acima.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas-SQL/Imagens/Insercao.png)   

##  Consultas

O comando que é utilizado para fazer as consultas é o **SELECT**, que seleciona as linhas que serão retornadas. 

O **FROM** é utilizado para definir as tabelas que serão utilizadas na consulta.

A clausula **WHERE** define as condições de consulta.

A seguir são apresentadas algumas consultas realizadas nas tabelas acima.

### Consulta 1
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas-SQL/Imagens/Consulta1.png)

A consulta 1 retorna toda a tabela **Clientes**

### Consulta 2
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas-SQL/Imagens/Consulta2.png)

A consulta 2 retorna apenas os nomes dos clientes da tabela **Clientes**

### Consulta 3
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas-SQL/Imagens/Consulta3.png)

A consulta 3 retorna a junção da tabela **Clientes** com a tabela **Fiado**, onde o valor devido seja maior ou igual a 43.

### Consulta 4
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas-SQL/Imagens/Consulta4.png)

A consulta 4 retorna o maior valor devido da tabela **Fiado**.



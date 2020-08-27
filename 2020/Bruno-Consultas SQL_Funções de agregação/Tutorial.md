# Consultas SQL - Funções de agregação

Neste tutorial vamos falar sobre funções de agregação em consultas SQL. Uma função de agregação processa um conjunto de valores contidos em uma única coluna de uma tabela e retorna um único valor como resultado. Sua sintaxe é semelhante aquela encontrada em muitas linguagens de programação. Contudo, o parâmetro informado é sempre a coluna cujos valores desejamos processar.

Neste tutorial iremos utilizar como exemplo as duas tabelas a seguir, a tabela Clientes e a tabela Fiado.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem01.png)

Vamos fazer algumas inserções nessas tabelas para que possamos realizar as consultas.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem02.png)

## Consultas
Agora vamos ver algumas consultas utilizando as funções de agregação que podem ser feitas nas tabelas acima.

### Quantidade
A função COUNT retorna o total de linhas selecionadas. Ela pode receber por parâmetro o nome da coluna ou um asterisco. Por padrão, quando informado o nome de uma coluna, valores do tipo null são ignorados, mas quando informado * todas as linhas serão contabilizadas.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem03.png)

A consulta acima utiliza a função **count** e retorna a quantidade de clientes da tabela Clientes.

### Maior valor
A função MAX analisa um conjunto de valores e retorna o maior entre eles.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem04.png)

A consulta acima utiliza a função **max** e retorna o maior valor devido da tabela Fiado.

### Menor valor
A função MIN analisa um grupo de valores e retorna o menor entre eles.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem05.png)

A consulta acima utiliza a função **min** e retorna o menor valor devido da tabela Fiado.

### Soma
A função SUM realiza a soma dos valores em uma única coluna e retorna esse resultado.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem06.png)

A consulta acima utiliza a função **sum** e retorna a soma de todos os valores devidos da tabela Fiado.

### Média
Com a função AVG podemos calcular a média aritmética dos valores em uma única coluna. 

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem07.png)

A consulta acima utiliza a função **avg** e retorna a média dos valores devidos da tabela Fiado.

### Operações sobre as funções de agregação

Também é possível fazer operações sobre as funções de agregação. No exemplo a baixo é possível ver uma operação de subtração sobre as funções **max** e **min** que retorna a diferença entre o maior e o menor valor devido da tabela Fiado.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Consultas%20SQL_Fun%C3%A7%C3%B5es%20de%20agrega%C3%A7%C3%A3o/Imagens/Imagem08.png)

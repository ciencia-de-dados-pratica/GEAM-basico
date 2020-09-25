# Funções em Bancos de Dados Relacionais

Neste tutorial iremos fazer uma introdução sobre funções em Bancos de Dados Relacionais, [aqui](https://youtu.be/pcwSYm2fZ7o) é possível assistir a esse tutorial em vídeo no nosso canal do Youtube.

Funções SQL permitem que nomeiem consultas e as armazenem dentro do banco de dados para acesso posterior. As funções são muito uteis para fazer operações em diversas tabelas e valores diferentes.

Para este tutorial iremos utilizar como exemplo a tabela **Ferramentas**, segue abaixo a criação e a inserção de valores nesta tabela.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Fun%C3%A7%C3%B5es%20em%20Bancos%20de%20Dados%20Relacionais/Imagens/Imagem01.png)

### Criação da Função

Para criar uma função em SQL, deve-se utilizar o comando **CREATE FUNCTION**, em seguida o nome da função e o tipo de parâmetro que ela recebe, pós isso **RETURNS** e o tipo de retorno da função, em seguida a operação que a função fará e por fim a linguagem da tabela.

Para dar um exemplo iremos criar uma função chamada taxa, que recebe um numerico como parâmetro e retorna 6% deste valor. Segue abaixo o comando de criação.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Fun%C3%A7%C3%B5es%20em%20Bancos%20de%20Dados%20Relacionais/Imagens/Imagem02.png)

### Utilização da função

Agora que temos a nossa função criada, podemos utilizá-la. Iremos fazer uma consulta na tabela **Ferramenta**, onde iremos retornar o nome, valor, a taxa que é o valor submetido a função e o valor mais a taxa.  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Fun%C3%A7%C3%B5es%20em%20Bancos%20de%20Dados%20Relacionais/Imagens/Imagem03.png)

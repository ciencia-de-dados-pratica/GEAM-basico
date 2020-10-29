# Variáveis e Lopings em Bancos de Dados Relacionais

Neste tutorial iremos fazer uma introdução sobre as variáveis e loopings em bancos de dados e serão apresentadas algumas operações básicas, [aqui](https://youtu.be/CQkOqfvaYt4) é possível assistir a esse tutorial em vídeo no nosso canal do Youtube.

### Variáveis
Uma variável é um objeto (uma posição, frequentemente localizada na memória) capaz de reter e representar um valor ou expressão. Enquanto as variáveis só "existem" em tempo de execução, elas são associadas a "nomes", chamados identificadores, durante o tempo de desenvolvimento. 

### Loop

Loop é uma palavra inglesa, que significa 'laço', 'circuito' ou 'sequência' e, segundo o contexto, pode referir-se a: uma repetição dentro de um programa.

### Criação da tabela

Para este tutorial, iremos utilizar como exemplo a tabela produtos.
Segue abaixo os comandos de criação e inserção de valores nesta tabela.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20Vari%C3%A1veis%20e%20lopings%20em%20Bacos%20de%20dados/Imagens/Imagem01.png)

### Utilizando as variáveis e o loop

Para utilizarmos as variáveis e o loop, iremos criar uma função chamada list_produtos. Segue abaixo a criação desta função.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20Vari%C3%A1veis%20e%20lopings%20em%20Bacos%20de%20dados/Imagens/Imagem02.png)

A função acima atua sobre a tabela Produtos, nela temos três variáveis para auxiliar nesse processo. Após o DECLARE, temos a declaração das variáveis **soma**, **u_pos** e **eu**, e o tipo de cada variável.

Também é possível  instanciar variáveis, como é feito nas variáveis **eu** que recebe a string “Bruno” e a variável **soma** que recebe o valor 0.

O loop **for** está percorrendo a tabela Produtos e em cada tupla que o for passa, a variável **u_pos** recebe os valores da tupla.

Dentro do for, é imprimida uma mensagem com o  nome do produto e na variável soma, é somado o valor do produto.

No retorno da função temos uma string com o valor da variável **eu** e a soma total dos valores dos produtos.

### Retorno do resultado

Para retornar o resultado da função, executamos o comando apresentado abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20Vari%C3%A1veis%20e%20lopings%20em%20Bacos%20de%20dados/Imagens/Imagem03.png)

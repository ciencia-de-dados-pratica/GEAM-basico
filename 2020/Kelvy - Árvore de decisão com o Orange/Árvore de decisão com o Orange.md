# Árvore de decisão com o Orange
Nesse tutorial, utilizaremos um dataset disponível no Orange para fazermos o exemplo de um modelo de árvore de decisão e outros detalhes úteis para trabalharmos com nossos datasets.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_0.png)

## Inicializando os dados
Começamos com o widget Datasets, nele vamos selecionar o dataset Sailing:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_1.png)

Depois, conectamos o Datasets ao widget Data Table para fazermos uma leitura do nosso dataset. Três features e uma variável target, todas categóricas:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_2.png)

## Árvore de decisão
Conectamos o nosso dataset com o widget Tree, para implementarmos o modelo, em seguida, conectamos o Tree ao widget Tree Viewer para podermos visualizá-lo. Podemos ver as decisões tomadas a partir das features:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_3.png)

Porém, o modelo de árvore de decisão não é muito conciso, uma pequena mudança na quantidade de dados já altera a árvore. Podemos perceber essa mudança utilizando o widget Data Sampler, inserindo-o entre o Datasets e o Tree:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_4.png)

Com uma árvore com 80% das samples já podemos notar a diferença:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_5.png)

## Alternativa e conclusões
A árvore de decisão é mais utilizada para datasets pequenos. Um widget útil para datasets com muitas features e muitos dados é o Rank, vamos conectar o Datasets a ele, ele tem diversas métodos para mostrar-nos quais features têm mais importância na tomada de decisão do nosso modelo (Information Gain, Infomation Gain Ratio etc).

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_6.png)

Uma alternativa à árvore de decisão é o ensemble Random Forest, ele divide o dataset em diversas samples e a partir de cada sample ele constroi uma árvore, é mais conciso do que somente uma árvore, podemos conectar Datasets ao Random Forest e, em seguida, ao Pythagorean Forest para visualizarmos essas árvores:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20%C3%81rvore%20de%20decis%C3%A3o%20com%20o%20Orange/Imagens/Screenshot_7.png)

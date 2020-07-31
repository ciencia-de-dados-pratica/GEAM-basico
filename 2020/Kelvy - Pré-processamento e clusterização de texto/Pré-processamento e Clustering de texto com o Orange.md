# Pré-processamento e Clustering de texto com o Orange
Nesse tutorial, faremos o Pré-processamento de texto e separaremos em Clusters um dataset de histórias, que já vem no Orange, com o auxílio do Add-on Text Mining. Você pode optar também por um tutorial em [vídeo](https://www.youtube.com/watch?v=HWy9ITEzrKk).

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_0.png)

## Instalando o Add-on
Primeiramente, vamos precisar instalar um add-on para trabalharmos com textos, clicamos em "Options", em seguida, "Add-ons...":

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_1.png)

Ao abrir a tela com os add-ons disponíveis, marcamos a opção "Text" e clicamos em OK para instalar, depois é só reiniciar o Orange:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_3.0.png)

Depois de instalarmos o Text Mining, na barra à esquerda vão aparecer os novos widgets para trabalharmos com texto:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_2.png)

## Carregando e analisando o dataset
Utilizamos o widget Corpus para carregar o dataset, clicamos nele, depois em "Browse documentation corpora" e selecionamos o dataset "grimm-tales-selected":

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_3.png)

Para analisarmos o dataset, podemos utilizar o widget Corpus Viewer, então conectamos ele ao widget Corpus:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_4.png)

Nele, podemos visualizar o conteúdo do dataset de diferentes formas, na barra "Display features" podemos alterar o que visualizamos do nosso dataset ao selecionar ou não a feature:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_5.png)

Ele também nos permite procurar palavras ou frases específicas no dataset e na barra "Search features" podemos alterar em quais features vamos fazer essa busca:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_6.png)

Outra maneira de visualizarmos nossos textos é usando o widget Word Cloud, conectando-o ao widget Corpus, ele vai exibir os termos que aparecem no texto, quanto maior o tamanho do termo, maior é a frequência de aparição dele no dataset. Porém, o Word Cloud vai mostrar diversas palavras que não dizem muito sobre o texto e até pontuação, por isso precisamos fazer um pré-processamento antes de trabalharmos com esses dados:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_7.0.png)

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_7.1.png)

## Pré-processando nosso dataset
O Orange possui o widget Preprocess Text, para pré-processamento de texto, conectamos ele ao widget Corpus:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_8.png)

Ele possui várias funções para isso, utilizaremos o "Lowercase" que deixa todas as letras minúsculas, utilizaremos o "Regexp", ele vai separar o texto em palavras individuais (tokens) e desconsiderar pontuações e por último, filtraremos as "Stopwords" que são palavras genéricas nos textos, não dizem muito sobre o conteúdo dele:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_9.png)

Podemos conectar o widget Word Cloud novamente, agora com o texto pré-processado, percebemos que já melhorou bastante o entendimento do texto:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_10.png)

Porém, caso queiramos omitir alguma palavra, podemos criar um documento de texto e escrever as palavras que queremos omitir (uma por linha):

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_11.png)

Então, Voltamos no widget Preprocess Text e vamos filtrar essas palavras, carregando nosso documento de texto no filtro:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_12.png)

E essas palavras não vão mais aparecer no Word Cloud:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_13.png)

## Preparando para a Clusterização
Para fazermos a Clusterização, precisamos de valores númericos sobre o nosso dataset, assim vamos utilizar o widget Bag of Words, ele vai fazer a contagem de cada palavra dos contos:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_14.png)

E conectando-o ao widget Data Table, podemos visualizar isso. Ele faz a contagem de cada palavra e cria uma nova feature com essa contagem:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_15.png)

## Clusterização
Agora, para fazermos a Clusterização, vamos conectar o widget Distances com o widget Bag of Words, e utilizamos a métrica Cosine que normalmente funciona melhor com textos: 

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_16.png)

Então, conectamos o widget Hierarchical Clustering ao Distances para fazermos a divisão em clusters:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_17.png)

No Hierarchical Clustering, selecionamos o Linkage Ward, como nosso dataset já possui labels, podemos definir a quantidade de clusters que queremos ao selecionarmos "Top N" e o número de clusters que melhor separa os textos, que no nosso dataset é 2, que são os dois temas das nossas histórias:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_18.png)

Analisando a Clusterização, podemos perceber que alguns "Animal Tales" ficaram no cluster dos "Tales of Magic" isso, possivelmente, se deu porque nesses "contos de animais" devem ter vários características semelhantes aos "contos de magia", o que fez ele ser posto nesse cluster:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Pr%C3%A9-processamento%20e%20clusteriza%C3%A7%C3%A3o%20de%20texto/Imagens/Screenshot_19.png)

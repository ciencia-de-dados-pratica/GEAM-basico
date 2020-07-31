# Análise de sentimentos com o Orange: percorrendo um texto
Nesse tutorial, utilizaremos um pequeno dataset que vem no Orange para fazermos uma análise de sentimentos ao longo desse texto, contando com o auxílio dos add-ons Text Mining e Time Series.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_0.png)

## Instalando os add-ons
Começamos instalando os add-ons que utilizaremos, clicamos em "Options", em seguida, "Add-ons...":

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_1.png)

Ao abrir a tela com os add-ons disponíveis, marcamos a opção "Text" e "Timeseries", então, clicamos em OK para instalarmos, depois é só reiniciar o Orange:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_2.png)

Depois de instalarmos os add-ons, na barra à esquerda vão aparecer seus novos widgets:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_3.png)

## Inicializando os dados
Utilizaremos o widget Corpus para carregar o dataset, depois, podemos usar qualquer uma das opções abaixo e escolhemos o dataset "*andersen.tab*":

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_4.png)

Com o dataset carregado, vamos conectá-lo ao widget Data Table, no Data Table, podemos observar os textos disponíveis, porém, vamos selecionar somente o texto "The Little Match-Seller", pois é esse que vamos utilizar hoje:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_6.png)

## Preparando os dados

Agora nós vamos conectar o Data Table, com o texto selecionado, ao widget Preprocess Text. No Preprocess Text, vamos remover "Transformation" e "Filtering", clicando nos Xs, e vamos selecionar o metódo de tokenização "Sentence", é a única coisa que vamos fazer no momento:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_8.png)

Depois disso, vamos conectar o texto pré-processado ao widget Python Script, que permite programação em Python e vai nos propocionar uma função que não está pré-definida no Orange, criando um novo Corpus, com as sentenças, apartir dos nossos tokens. Copie o código abaixo:
```
import numpy as np
from Orange.data import Domain, StringVariable
from orangecontrib.text.corpus import Corpus

tokens = in_data.tokens
new_domain = Domain(attributes=[], metas=[StringVariable('Sentences'), StringVariable('Title')])

titles = []
content = []

for i, doc in enumerate(tokens):
    for t in doc:
        titles.append(in_data[i]['Title'].value)
        content.append(t)

metas = np.column_stack((content, titles))
out_data = Corpus.from_numpy(domain=new_domain, X=np.empty((len(content), 0)),
                            metas=metas)
out_data.set_text_features([StringVariable('Sentences')])
```
E cole no Python Script, depois clique em "Run":

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_9.png)

Depois, vamos conectar o widget Python Script, com nosso novo Corpus, ao widget Preprocess Text. Dessa vez, vamos usar o "Transformation" Lowercase, para transformar todas as letras em minúsculas, o "Filtering" Stopwords, para filtrar palavras que não dão muita informação sobre nosso texto e, novamente, "Tokenization", porém, desta vez, com o metódo de Regexp, que vai ignorar pontuações:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_10.png)

Obs: caso não apareça as opções de "Filtering" e/ou "Transformation", no Preprocess Text, é só clicar neles, na barra à esquerda e arrastar para a tela:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_11.png)

Com o texto pré-processado conectamos ele ao widget Sentiment Analysis, nele usaremos o método "Vader" (única linguagem suportada por ele é o inglês):

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_12.png)

Então, conectamos o Sentiment Analysis ao widget As Timeseries, que vai reinterpretar nossos dados como um objeto de tempo. Nesse widget vamos selecionar a opção "Sequence is implied by instance order", ou seja, nossos dados já estão organizados pelo tempo (ordem das sentenças).

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_13.png)

Depois, conectamos o As Timeseries ao widget Line Chart. No Line Chart, selecionamos a variável "Compound" para mostrarmos o gráfico dos sentimentos, nele podemos observar a variação dos sentimentos ao longo do texto:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_14.png)

Outra maneira de visualizarmos os sentimentos é com o widget Heat Map, conecte o Sentiment Analysis a ele. No Heat Map separaremos em clusters as "Rows", selecionamos a opção "Clustering (opt. ordering)", para organizá-los por quão similares são as emoções:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_15.png)

Nesse caso do Heat Map, quanto mais azul mais negativa é a emoção e quanto mais amarelo mais positiva é a emoção. Com isso, vamos selecionar as 4 partes do texto com emoções negativas para observarmos:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_16.png)

Então, depois de selecionarmos, conectamos o Heat Map ao Corpus Viewer para vermos o conteúdo desses trechos, se lermos, podemos perceber o porque esses trechos foram classificados como tendo emoções negativas:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_17.png)

Agora vamos ver 4 emoções positivas, voltamos ao Heat Map e selecionamos novamente:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_18.png)

Observando esses 4 novos trechos, podemos perceber que, de fato, eles possue emoções positivas:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20sentimentos%20com%20o%20Orange-%20percorrendo%20um%20texto/Imagens/Screenshot_19.png)

# Classificação de agrupamentos no Orange

Imagine que tenhamos as coordenadas bidimensionais de vários pontos em um gráfico, e que agora queremos classificar esses pontos, nós não conseguiríamos, pois para fazer uma classificação, necessitaríamos de uma variável Target (alvo) do tipo categórica e como só temos valores numéricos, é impossível fazer tal operação. A menos que separemos esses pontos em grupos e criemos uma Label (rótulo) para cada um. Assim poderemos classificar novos valores.

# Gerando os Dados

 Vamos começar usando o widget **Paint Data** para simular alguns dados.
 
 ![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/01.png?raw=true)

# Fazendo o Clustering

Agora ligamos esses dados ao widget **k-Means** para fazer o Clustering (agrupamento) desses dados.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/02.png?raw=true)

O k-Means decidiu que a melhor opção é separar os pontos em 6 grupos.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/03.png?raw=true)

O agrupamento gerou duas novas colunas, a **Cluster** que é do tipo categórico e a **Silhouette** que é do tipo numérica. Podemos visualizar essas colunas por meio do widget **Data Table**.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/04.png?raw=true)

Logo, podemos usar o widget de visualização **Scatter  Plot** e podemos ver o resultado do agrupamento.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/05.png?raw=true)

Mas iremos focar na coluna **Cluster**, pois ela será nossa variável **target** (alvo). Porém, por padrão, as colunas adicionadas pelo **k-Means** são colunas do tipo **Meta**. Para tornarmos a coluna **Cluster** em nossa variável **target** usaremos o widget **Select Columns**. Para definir a variável **target**, devemos arrastar **Cluster** de **Metas** para **Target**.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/06.png?raw=true)

# Fazendo a Classificação

Para começarmos o teste de classificação, precisamos separar uma parte dos dados para treino e uma outra para teste. Para isso usaremos o widget **Data Sampler**, nele nós separaremos 90% dos dados para treino e os outros 10% para teste.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/07.png?raw=true)

Após isso, ligaremos o **Data Sampler** a duas **Data Table**, nomeados de **Train table** e **Test Table**. 
E iremos editar os links para que fiquem da seguinte forma:

**Para Train Table**

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/08.png?raw=true)

**Para Test Table**

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/09.png?raw=true)

Feito isso, nosso workflow está com essa aparência até agora:

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/10.png?raw=true)

Agora, vamos começar o treinamento do nosso algoritmo e para isso, usaremos o widget **Logistic Regression**, que é um modelo de classificação bastante conhecido.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/11.png?raw=true)

E também vamos avaliar a precisão de classificação do nosso algoritmo, usando o widget  **Test  and  Score**.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/12.png?raw=true)

Como podemos ver acima, a precisão de categorização do nosso algoritmo é de **0.988**, ou seja, **98.8%**.

Por fim, vamos fazer a categorização usando o widget **Predictions**

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/13.png?raw=true)

Feito a classificação, podemos usar o widget **Confusion Matrix** para facilitar a nossa visualização dos resultados.

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/14.png?raw=true)![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/15.png?raw=true)

Analisando a matriz, podemos ver que só houve um erro, o que acaba condizendo com a nossa porcentagem de precisão.  
  
E esse é o resultado final do nosso workflow

![enter image description here](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/marcus-classifica%C3%A7%C3%A3o_de_agrupamentos/img/16.png?raw=true)

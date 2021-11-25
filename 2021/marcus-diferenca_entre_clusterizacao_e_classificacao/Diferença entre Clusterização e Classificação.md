# Diferença entre Clusterização e Classificação

Quando estudamos ciência de dados é certo que veremos *clustering* e *classificação*, porém, como ambos são modelos de identificação de padrões e é comum ficar confuso entre um e outro. No entanto, esses modelos possuem grandes diferenças, que serão apresentadas neste documento, por meio de exemplos na ferramenta *Orange Data Mining*.

## Clusterização

A clusterização é um método de aprendizado de máquina não supervisionado, ou seja, damos um conjunto de dados não rotulados como *input* e recebemos um *output* no qual não fazemos ideia do qual será até que seja processado. 

Para explicar a clusterização utilizarei o *dataset* "Iris" e o *widget K-means.*

![01](https://i.imgur.com/YMG0sL9.png)

O *workflow* acima é bem simples, começamos pelo *datasets* que importa o conjunto de dados "Iris", logo após, temos um *Data table* que serve para ver os dados.

![02](https://i.imgur.com/ILrkmOU.png)

Como podemos ver, esse conjunto de dados possui 5 colunas sendo, uma categórica e as outras quatro são numéricas. Para melhorar o nosso exemplo iremos remover a coluna "iris" das *features* e a tornaremos um metadado, para isso usaremos o *widget Select Columns*, fazendo isso teremos certeza de que os dados não estarão rotulados.

![03](https://i.imgur.com/BuumVsq.png)

Após isso, usaremos o *K-Means* para fazer a clusterização.

![04](https://i.imgur.com/T9WGgWZ.png)

Como podemos ver, o algoritmo avaliou que seria melhor separar os dados em dois *clusters*. Podemos ver o *Scatter Plot* dos dados logo abaixo.

![05](https://i.imgur.com/EanDMXR.png)

No entanto, como temos três tipos de iris, iremos forçar o *Kmeans* a separar os dados em três *clusters*. E também colocaremos na função *shape*, do *Scatter Plot*, a variável "iris" para facilitar a visualização.

![05.1](https://i.imgur.com/olIBZ6L.png)

Como podemos observar, com base nas legendas, temos a mesma forma com mais de uma cor, ou seja, a mesma "iris" em grupos diferente. Isso ocorre pois o *clustering* não passa por nenhum processo de treino e não possui rotulo, logo, ele separa os *clusters* com base na proximidade dos dados.

## Classificação

Diferente da clusterização, a classificação é um método de aprendizado de máquina supervisionado, ou seja, damos um conjunto de dados rotulados como *input* e recebemos um *output* que pode se previsto, mesmo antes que seja processado. 

Para explicar a classificação também utilizarei o *dataset* "Iris" e o *widget Logistic Regression.*

![06](https://i.imgur.com/JJzVu2J.png)

Bem, como o método de classificação precisa de dados de treino para realizar o teste, usaremos o *widget Data Samples*, para randomizar uma porcentagem dos dados para treino e liberar os demais para teste.

![07](https://i.imgur.com/lZew1s5.png)

No caso, 30 instâncias serão usadas para treinar o algoritmo do *Logistic Regression* e 120 instâncias serão usados para teste no *widget Predictions*.

![08](https://i.imgur.com/QBlECGq.png)

Acima podemos ver a *Confusion Matrix* dos resultados, o que está na diagonal principal são os acerto e o que está nas diagonais secundárias são os erros, nesse caso ouve 4 erros e 116 acertos.

![09](https://i.imgur.com/rLXl52L.png)

Ademais, temos o *Scatter Plot* dos resultados, e podemos afirmar que está bem mais preciso do que o de clusterização.

## Conclusão

Por fim, podemos concluir que as grandes diferenças entre a classificação e a clusterização é que um é um modelo de aprendizado supervisionado e o outro um modelo de aprendizado não supervisionado, além disso, a clusterização não necessita de uma etapa de treino como a classificação e também não precisa de variáveis rotuladas. Logo, em uma situação que só tivéssemos um conjunto de dados que não possua nenhum rótulo, podemos usar a clusterização para criar esses rótulos. Porém, no caso de já possuirmos uma base de dados rotulada, podemos usar a classificação. Há também a possibilidade de usar ambos os métodos em conjunto, usando a clusterização para rotular os dados e usar esses dados como base de treino para futuros testes, damos a essa combinação dos dois métodos o nome de prendizado de máquina semi-supervisionado.

## Link do vídeo
<a href="https://youtu.be/VnpKi_8HE54">Diferença entre Clusterização e Classificação</a>

## Referência
- <a href="https://orangedatamining.com">Orange Data Mining - Data Mining</a>
- <a href="https://blog.bismart.com/en/classification-vs.-clustering-a-practical-explanation">Classification Vs. Clustering - A Practical Explanation</a>
- <a href="https://blog.bismart.com/en/machine-learning-supervised-unsupervised-differences">The differences between supervised and unsupervised Machine Learning</a>


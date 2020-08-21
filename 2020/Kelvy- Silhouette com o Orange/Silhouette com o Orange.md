# Silhouette com o Orange
Nesse tutorial, utilizaremos um dataset disponível no Orange para explicarmos e exemplificarmos o funcionamento do Silhouette.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_0.png)

## Inicializando os dados
Usamos o widget Datasets e carregamos o dataset Iris:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_1.png)

Conectando o widget Data Table ao Datasets, vemos que o dataset possui três diferentes tipos de iris:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_2.0.png)
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_2.1.png)
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_2.2.png)

## Silhouette Plot
Com essa informação, podemos conectar o Datasets ao widget k-Means e fixar o nosso número de clusters em 3:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_3.png)

Em seguida, conectamos o k-Means ao widget Scatter Plot para observarmos nossos clusters:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_4.png)

Então, conectamos o k-Means ao widget Silhouette Plot, nele podemos ver o quanto cada uma das instâncias se relacionam com seu cluster. O Silhouette faz um cálculo e dá uma pontuação para cada uma das instâncias dos clusters, essa pontuação é normalizada e fica entre 0 e 1, quanto mais próximo de 0 mais longe do centro do cluster e quanto mais próximo do 1 mais perto do centro.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_5.0.png)

Podemos perceber isso conectando o Silhouette ao mesmo Scatter Plot, passando os dados que selecionamos. Enquanto as instâncias com menor pontuação ficam na borda do cluster, próximo a outro:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_5.1.png)

As instâncias com maior pontuação ficam mais ao centro do cluster:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_6.png)

## Demonstrando prováveis erros de classificação
Agora, com o dataset Iris, novamente, vamos conectar o Datasets a um novo Silhouette Plot, diretamente, sem clusters, e passando a variável Iris como atributo:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_7.png)

O que vamos demonstrar é que, as instâncias de Iris com menor pontuação no Silhouette serão as mais prováveis de serem classificadas incorretamente por algum algoritmo, como exemplo, o Random Forest. Conectamos o Datasets ao widget Test & Score, com os padrões do Orange (Cross validation, 10 folds etc), para testarmos nosso modelo de Random Forest e depois disso ao widget Confusion Matrix:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_8.png)

No Confusion Matrix, podemos selecionar os valores que, no nosso teste, foram classificados incorretamente pelo Random Forest:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_9.png)

Então, voltando ao Silhouette Plot, vamos selecionar alguns dos valores com menor pontuação para compararmos:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_10.png)

Agora, com nossos dados selecionados, faremos a comparação deles usando o widget Venn Diagram, conectamos o Confusion Matrix e o Sillhouette a ele. A interseção deles mostrará os valores com baixa pontuação e que foram classificados incorretamente, podemos selecioná-los para observarmos:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_11.png)

Com isso, conectamos o Datasets a um outro Scatter Plot, juntamente com o Venn Diagram, conseguindo demonstrar que os modelos, de fato, têm mais problemas na classificação de instâncias mais periféricas.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy-%20Silhouette%20com%20o%20Orange/Imagens/Screenshot_12.png)

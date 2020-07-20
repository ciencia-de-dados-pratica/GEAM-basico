# Classificação dos Animais Usando o Orange
Nesse tutorial, usamos o Orange para classificar os animais em suas classes (anfíbio, ave, inseto, mamífero, peixe, réptil ou invertebrado), de acordo com suas características biológicas, usando um dataset já integrado ao software. Você pode optar também por um tutorial em [vídeo](https://www.youtube.com/watch?v=0hVTZouALM0&t=3s).

![Fim](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-0.png)

## Inicializando os dados
Primeiramente, usamos o widget Datasets para inicializar os dados:

![Widget-Datasets](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-1.png)

Depois escolhemos o arquivo Zoo: 

![Zoo](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-2.png)

Então, conectamos o widget Data Table ao arquivo já carregado no Dataset para fazermos uma leitura dos dados e entendermos o dataset: 

![Conectando-DT](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-3.png)

No Data Table, podemos observar que os dados que vamos usar para ensinar o algoritmo a classificar os animais são, com exceção do número de pernas (*legs*), dados Booleanos indicando quando o animal tem ou não aquela característica e, no caso das pernas, a quantidade:

![Data-Table](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-4.png)

## Visualização dos dados
Para visualizar os dados, utilizaremos o widget Distribuitions:

![Conectando-Distribuitions](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-5.png)

Depois de conectarmos o nosso Dataset ao Distribuition, ele vai nos permitir visualizar nossos dados:

![Visualização-Distribuition](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-6.png)

No Distribuitions podemos ver dados bem detalhados e organizados. Vamos separar os animais por seu tipo e, alternando entre as características, podemos ver a correlação de cada característica com os tipos dos animais: 

![Distribuitions](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-7.png)

## Testando o algoritmo
Para classificarmos os animais, usaremos o Logistic Regression para ensinar o algoritmo a classificar os animais, pois foi o melhor modelo para esse caso, então, ligamos o Logistic Regression ao nosso dataset:

![Conectando-LR](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-8.png)

Para testarmos a funcionalidade do nosso algoritmo, nós utilizamos o widget Test and Score: 

![widget-Test-and-Score](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-9.png)

Então, conectamos o nosso dataset ao Test and Score, em seguida, conectamos o modelo que vamos usar para classificação, o Logistic Regression:

![Conectando-TaS](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-10.png)

No Test and Score, podemos observar como o modelo se saiu com nosso dataset, normalmente, usamos o modelo que possui maior CA (*Classification Acuraccy*) para classificar nossos dados: 

![Test-and-Score](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-11.png)

## Usando o dataset
Com o algoritmo pronto, agora podemos usá-lo para classificar outros animais. Usaremos o Excel para criar uma tabela, as colunas são as características dos animas (*features*), têm que ser iguais às do dataset original, e cada linha vai ser um animal diferente: 

![Excel](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-12.png)

No meu exemplo, escolhi 3 animais que não estão no dataset original (tatu, lontra e lagarto), para carregá-lo no Orange, vamos usar o widget File: 

![widget-File](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-13.png)

No File, você vai clicar no ícone de Pasta e depois escolher o arquivo do Excel dos seus animais: 

![carregando-arquivo](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-14.png)

Novamente, podemos usar o Data Table para checar se está tudo certo com nossos dados, conectando o File ao Data Table. Para classificarmos nossos animais, vamos conectar o File com nosso arquivo ao widget Predictions e também o módelo já criado por nós antes, de Logistic Regression, ao Predictions: 

![conectando-Predictions](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-15.png)

No Predictions podemos ver como ele classificou nossos animais, no caso dos que eu escolhi, o algoritmo não teve problema e classificou todos corretamente:

![Predictions](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20Classifica%C3%A7%C3%A3o%20dos%20animais/Imagens/Imagem-16.png)

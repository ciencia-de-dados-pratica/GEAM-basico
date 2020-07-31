# Análise de imagens com o Orange
Nesse tutorial, usamos um Add-on do Orange para analisarmos imagens e verificarmos qual delas é mais semelhante à uma previamente escolhida. O dataset utilizado pode ser baixado [aqui!](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Paintings.zip) E você pode optar também por um tutorial em [vídeo](https://www.youtube.com/watch?v=w9TUfNiVffA).

![workflow](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/Final.png)

## Instalando o Add-on
Primeiramente, vamos precisar instalar um add-on para trabalharmos com as imagens, clicamos em "Options", em seguida, "Add-ons...":

![add-on](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/1%20-%20add-ons.png)

Ao abrir a tela com os add-ons disponíveis, marcamos a opção "ImageAnalytics" e clicamos em OK para instalar, depois é só reiniciar o Orange:

![image-analytics](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/2%20-%20ImAn.png)

Depois de instalarmos o Image Analytics, na barra à esquerda vão aparecer os novos widgets para trabalharmos com imagens:

![widgetsImAn](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/3%20-%20Barra%20de%20widgets.png)

## Carregando e analisando as imagens
Para carregarmos as imagens utilizamos o widget Import Images, depois clicamos no ícone para selecionar a pasta "Paitings" que foi o dataset baixado:

![import-images](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/4%20-%20ImIm.png)

Para observarmos as imagens conectamos o widget Import Images ao widget Image Viewer:

![conect](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/5%20-%20conect%20ImIm-ImV.png)

Então, é só clicarmos no Image Viewer que ele mostrará as imagens. Vemos que o nosso dataset possui imagens de vários pintores diferentes, com excessão de Monet, que possui duas pinturas e é o que nós vamos tentar identificar:

![image-viewer](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/6%20-%20ImV.png)

## Image Embedding e Neighbors
Agora, nós vamos arrastar o widget Image Embedding para a tela e nele escolhemos o Embedder "Painters", que foi treinado especificamente para reconhecer pintores. Então o Import Images à ele: 

![image-embedding](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/7%20-%20ImEm.png)

Em seguida, conectamos o Image Embedding ao Widget Data Table, no Data Table vamos selecionar a pintura "Monet", que servirá como referência para encontrar a outra pintura:

![data-table](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/8%20-%20Data%20Table.png)

Após isso, podemos comparar nossas imagens, para isso, conectamos o Image Embedding ao widget Neighbors, com nossos dados, e ele vai escolher um número de imagens do nosso conjunto de dados que são semelhantes à que passaremos como referência, então, conectamos o Data Table com a pintura selecionada:

![neighbors-conect](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/9%20-%20ImEm-DT-Neighbors.png)

Double click no Neighbors, nele, mudamos a distância para "Cosine" e colocamos 2 neighbors, que são os dois quadros de Monet, e desmarcamos a opção "Exclude rows (equal to) references", do contrário a imagem de referência seria desconsiderada do dataset:

![neighbors](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/10%20-%20Neighbors.png)

## Resultado
Por fim, conectamos o Neighbors ao widget Image Viewer, para podermos ver quais as duas imagens que o Neighbors declarou serem mais próximas de um Monet:

![resultado](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Kelvy%20-%20An%C3%A1lise%20de%20imagens/Imagens/11%20-%20ImVresultado.png)

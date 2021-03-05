# Introdução ao PostGIS

 Neste tutorial, falamos sobre o PostGIS que é uma extensão do PostgresSQL para dados espaciais. [Aqui](https://youtu.be/riyga9m2Dg0) é possível assistir a esse tutorial em vídeo no nosso canal do Youtube.
 
 O PostGIS é uma extensão espacial gratuita e de código fonte livre. Sua construção é feita sobre o sistema de gerenciamento de banco de dados objeto relacional PostgreSQL, que permite o uso de objetos GIS (Sistemas de Informação Geográfica) ser armazenado em banco de dados. PostGIS inclui suporte para índices espaciais GiST e R-Tree, além de funções para análise básica e processamento de objetos GIS.
 
 ### Instalação
 
 Para instalar o PostGIS no sistema operacional Linux, basta utilizar um dos comandos abaixo.
 
 ![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Introdu%C3%A7%C3%A3o%20ao%20PostGIS/Imagens/Imagem%2001.png)
 
 ### Criação da extensão
 
Uma vez instalado, é possível utilizar o PostGIS, criando uma extensão para ele no seu banco de dados, utilizando o comando abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Introdu%C3%A7%C3%A3o%20ao%20PostGIS/Imagens/Imagem%2002.png)

Após criar a extensão é possível verificá-la utilizando o comando abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Introdu%C3%A7%C3%A3o%20ao%20PostGIS/Imagens/Imagem%2003.png)

### Testando a Extensão

Após ser criada a extensão ela irá criar varias funções, assim como uma tabela no seu banco de dados, podemos testa-la executando a consulta abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Introdu%C3%A7%C3%A3o%20ao%20PostGIS/Imagens/Imagem%2004.png)



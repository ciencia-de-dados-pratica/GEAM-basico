# Jupyter Notebook - Conexão e Primeiros Comandos

<br>

## Iniciando um novo Notebook

### Navegador

Para iniciar o Jupyter Notebook em seu navegador, primeiro abra o terminal do Anaconda. Você pode encontrá-lo a partir da barra de pesquisa do Windows. Com o terminal aberto, basta digitar o comando: 
  <br>
  <br>
  
  > jupyter notebook
  
  <br>
  <img src="imagens/jupyterTerminal.jpeg" width="350">

  A partir daí, a seguinte tela deve abrir no seu navegador:
  
  <img src="imagens/jupyterNavegadorAberto.jpeg" width="480">
  
  Nesta página inicial, você pode encontrar Notebooks previamente criados para editá-los, em uma lista dos arquivos do seu computador. No canto direito, logo acima da lista de arquivos, você pode encontrar o seguinte dropdown:
  
  <img src="imagens/jupyterNewDropdown.PNG" width="300">
  
  Selecionando o kernel para o seu novo Notebook, tudo pronto!
  
  <img src="imagens/jupyterNewNotebook.PNG" width="480">
  
<br>

### VS Code
Para criar um novo notebook no VS Code, basta criar um arquivo .ipynb
<br>
<br>
<img src="imagens/jupyterNotebookNewVSCode.jpeg" width="480">

<br>

## Conexão com o banco de dados (Postgres)
Como é a plataforma mais confortável para mim, vou utilizar o VS Code, mas funciona da mesma forma para o Jupyter Notebook no navegador.
<br>
Esta é uma parte bem mecânica, na verdade. Primeiro, vamos importar as bibliotecas necessárias:

> import psycopg2
> import sqlalchemy

A primeira é a biblioteca do Postgres para Python, e a segunda é necessária para criarmos a engine necessária para a conexão.
<br>
O próximo passo é obter a string do link de conexão. 

> 'postgresql://postgres:SENHA@HOST/DATABASE'

Um exemplo mais prático:

> 'postgresql://postgres:minhasenha123@localhost/Biblioteca'

O próximo passo é criar uma engine com a sua string como parâmetro. Pode passar essa string diretamente ou através de uma variável

> sqlalchemy.create_engine(STRING)

<img src="imagens/connectionStringEngine.PNG" width="600">

Em uma célula diferente, use a palavra mágica a seguir para carregar a sua engine no módulo sql previamente instalado

> %load_ext sql

<img src="imagens/loadExt.PNG" width="800">


No próximo passo, em uma célula diferente, é preciso fornecer a string de conexão criada anteriormente da seguinte forma

> %sql STRING

Usando a string diretamente:

> %sql postgresql://postgres:minhasenha123@localhost/Biblioteca

Usando a variável:

<img src="imagens/sqlCon.PNG" width="700">



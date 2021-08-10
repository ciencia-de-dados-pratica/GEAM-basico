# Analizando dados do Twitter com Orange Data Mining

Podemos usar redes sociais não apenas para diversão, mas também elas são bastantes úteis para podemos analizar o comportamentento das das pessoas, principalmente com o Twitter. Com ele temos acesso aberto aos seus conteúdos, é fácil de analizar tópicos opiniões sobre determinado assunto, redes de amizades, tendências, hashitags e entre outros. 
##
Aqui vamos aprender como recuperar dados do twitter, como pré-processá-los e descobrir tópicos interessantes do corpus.

![preview.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/preview.png)

## Conta de Desenvolvedor
O twitter fornece uma maneira de recuperar tweets, mas primeiro você deve [criar uma conta](https://developer.twitter.com/en/apps) no site do desenvolvedor para obter uma chave de API.

Depois de criar uma conta até em "create an app" e preencha os formulários com as informações necessárias.
Após isso, vá para keys e tokens, copie a API key, e a API secret key e salve-as em algum lugar, pois usaremos elas depois.

## Instalando o Add-on
Primeiramente precisaremos instalar um add-on para termos acesso as ferramentas que vamos utilizar, clicamos em "Options" depois em "Add-ons...":

![Addon-01.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/Addon-01.png)


Ao abrir um janela com add-ons disponíveis procuraremos pela opção "Text" e clicamos em OK para instalar (vai ser necessário reiniciar o Orange após isso):

![Addon-02.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/Addon-02.png)

## 
Após reiniciar o Orange, na barra à esquerda aparecerão novos widgets:

![Addon-03.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/Addon-03.png)


## Carrengando os tweets para a API do Twitter
Utilizaremos o widget Twitter para carregar os tweets, clicamos nele e depois em "Twitter API Key":

![twitter-01.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/twitter-01.png)

##
Aqui preencha com as chaves que foram geradas na sua conta de desenvolvedor do twitter e clique em "OK":

![twitter-02.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/twitter-02.png)

##
Agora digamos que desejamos ver o que é tendência na comunidade de ciência de dados, digitamos "#CiênciaDeDados" no campo em branco. Aqui podemos selecionar a linguagem e informar a quantidade de tweets que queremos recuperar, depois disso clicamos em "Search":

 ![twitter-03.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/twitter-03.png)


## Visualizando os dados de texto
Para obeservar os dados que recuperamos vamos usar o widget "Corpus Viewer":

 ![viewer-01.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/viewer-01.png)

##
Ao clicar no "Corpus Viewer" poderemos ver de todos tweets que conseguimos recuperar com a nossa busca, entretanto, da forma em que os dados estão organizados fica um pouco difícil interpreta-los:

![viewer-02.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/viewer-02.png)

##
Para termos uma visão mais concisa, podemos selecionar apenas o conteúdo dos tweets. Para isso, no lado esquerdo localize a opção "Display features" e clique "Content":

![viewer-03.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/viewer-03.png)

##
Depois selecione todos os tweets no recurso de exibição, use "ctrl + A" se estiver usando o Windows ou Linux e "command + A" se caso estiver no Mac. Agora podemos ler o tweets um por um:

![viewer-04.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/viewer-04.png)


## Nuvem de Palavras
Se em vez de 100 tweets tivessemos milhares de tweets seria praticamente impossível verificar um por um, então, em vez disso vamos observar as palavras que mais se repetem para ver do que se trata o corpus.

Conectaremos o "Word Cloud" ao widget do Twitter e ver o que temos:

![word-01.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/word-01.png)


## Removendo palavras com pré-processamento de texto
Como podemos ver, há várias coisas inúteis em nossa consulta e alguns sinais de pontuação. Vamos remover isso com o widget de "Preprocess Text". Ele já vem pré-definido com letras minúsculas, vamos manter isso e adicionar "Remove urls", pois na núvem de palavras tinha um "https" classificado no topo, mas ela não é uma palavra real então podemos removê-la:

![process-01.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/process-01.png)

##
A próxima etapa é definir a organização certa, em vez de dividir por palavras, usaremos um tokenizador de tweet pré-treinado que é capaz de extrair menções, hashitags e emojis. A desvantagem é que ele também retorna pontuação, mas vamos removê-la usando "regex". A expressão regular predefinida irá remover a maioria dos caracteres de pontuação.

![process-02.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/process-02.png)

##
Agora se dermos uma olhado na nuvens de palavras veremos que agora os dados fazem um pouco mais sentido. Alguma das principais hastags usadas são "#ciênciadedados"l "#cientistadedado", "#inteligenciaartificial" e etc:

![process-03.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/process-03.png)


## Modelagem de tópicos
Finalmente podemos descobrir sobre o que são estes tweets. Para isso ligaremos o widget "Topic Modelling" ao "Preprocess Text" para descobrir os tópicos em latim nos dados.

![topics-01.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/topics-01.png)

##
Existem três métodos para modelagem de tópicos, usaremos "Latent Dirichelet Allocation" (alocação direta em Latin), que é um método generativo baseado na co-ocorrência de palavras para os quais estamos solicitando 10 tópicos. No widget podemos ver as palavras que definem cada tópico:

![topics-02.png](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2021/Igor%20-%20Analizando%20dados%20do%20Twitter/Imagens/topics-02.png)

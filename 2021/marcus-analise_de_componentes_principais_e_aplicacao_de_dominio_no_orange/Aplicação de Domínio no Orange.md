# Análise de Componentes Principais e Aplicação de Domínio no Orange

A PCA (*Principal Component Analysis*) ou análise de componentes é uma técnica de aprendizado de máquina não supervisionado que visa reduzir a quantidade de variáveis de um *dataset* com a menor perca de dados possível. Porém, o que acontece se quisermos adicionar novos dados transformados em um outro PCA? Para responder a essa pergunta irei fazer uma demonstração.

Utilizarei o *dataset Wine* que cataloga três tipos de vinho e suas características. Esse *dataset* possui 13 *features* e 178 *instances*.

Como faremos dois PCAs diferentes (para treino e teste), devemos separar os dados usando o *Widget* *Data Sampler*. Segue a imagem abaixo com as configurações do *widget*.

![01](https://i.imgur.com/1WI67aM.png)

Agora que separamos os dados, iremos conecta-los ao seus respectivos PCAs.

![02](https://i.imgur.com/isg1jnM.png)

Abaixo podemos ver a configuração para ambos os PCAs.

![03](https://i.imgur.com/Xd3bzb4.png)

Quanto menor a porcentagem em *Explained variance* maior será a perca de dados, logo, por esse motivo, iremos colocar em 80%.

Agora, para unir os dados transformados pelos PCAs em um único *dataset*, usaremos o *widget Concatenate*.

![04](https://i.imgur.com/8GxMTnK.png)

É importante prestar atenção se a caixa "*Treat variables with the same name...*" está marcada como na imagem abaixo.

![05](https://i.imgur.com/SJ6ucZC.png)

Feito isso, podemos ver o *Scatter Plot* dos dados.

![06](https://i.imgur.com/dXhKRhX.png)

É notável que os dados ficaram bastante bagunçados, principalmente na parte inferior. Tal fenômeno ocorrera pelo simples fato dos dados terem sido transformados em PCAs diferentes. Embora possuíssem as mesmas configurações, os PCAs, tiveram *output* diferentes.

Para resolver esse problema utilizaremos o *widget Apply Domain*, ele ira substituir o PCA de teste. E por fim ficaremos com o seguinte *Workflow*.

![07](https://i.imgur.com/WBsdwfl.png)

Basicamente o que esse *widget* faz é transformar os novos dados como se eles tivessem sido transformados no mesmo espaço do PCA de treino. Para facilitar a visualização, imagine como se ele pegasse o modelo aplicado pelo PCA de treino e aplicasse nos novos dados, assim não precisaríamos transformar todos os dados quando quiséssemos adicionar novos dados, só precisaríamos transformar os que foram adicionados recentemente.

Para finalizar vamos visualizar o *Scatter Plot* após a aplicação do domínio.

![08](https://i.imgur.com/IMSSUno.png)

É gritante a diferença do gráfico sem e com o *Apply Domain*, podemos ver que agora ficou mais fácil de fazer uma leitura desse gráfico. leitura desse gráfico.

## Link do Video
<a href="https://youtu.be/WJ7ygNxTud4" target="_blank">Análise de Componentes Principais e Aplicação de Domínio no Orange</a>

## Referências
<a href="https://orangedatamining.com/blog/2021/2021-08-13-apply-domain/" target="_blank">Orange Data Mining - Why You Should Use Apply Domain</a><br>
<a href="https://orangedatamining.com/widget-catalog/unsupervised/PCA/" target="_blank">Orange Data Mining -PCA</a><br>
<a href="https://orangedatamining.com/widget-catalog/data/applydomain/" target="_blank">Orange Data Mining - Apply Domain</a><br>
<a href="https://operdata.com.br/blog/analise-de-componentes-principais/" target="_blank">Oper - O que é Análise de Componentes Principais?</a><br>

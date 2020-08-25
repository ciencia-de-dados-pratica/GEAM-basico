# Análise e predição de ações da bolsa de valores usando o Orange

Nesse tutorial mostraremos como funciona uma predição de valores numéricos, ou seja, um problema de regressão. Para isso usaremos modelos de previsão em um dataset de ações do mercado financeiro mais precisamente, as ações da amazon(AMZN).

### entendendo um pouco sobre o data set

Usando o Widget Yahoo finances podemos encontrar as ações da amazon. Definimos as datas e colhemos o resultado.

//amazon 

Ligamos ao DataTable e vemos o resultado

//amzn data table

### Colunas

No mercado financeiro existem várias formas de representar os dados referidos dado um período de tempo. a representação mais famosa é o gráfico de velas.

//candle

Considerando, por exemplo, que cada vela representa um dia, temos a abertura(o preço da unidade da ação no qual o dia iniciou), o fechamento(o preço da unidade da ação no qual o dia encerrou), o preço máximo(pavio superior, o máximo que o preço da ação chegou naquele dia), e o preço mínimo(pavio inferior, o mínimo que o preço da ação chegou naquele dia). Além disso também temos em nosso dataset o volume, que representa a quantidade de ações negociadas naquele dia.

### Previsões de fechamento

Para prosseguirmos, utilizaremos um modelo de classificação chamado regressão linear.
Ligamos ele ao widget Test and Score.

//tas

Como resultado, temos dentro de Test and Score os resultados de acurácia, que de modo geral, dizem respeito ao quão bom é o modelo.

//acurácia

- MAE (erro médio absoluto) representa a diferença entre os valores originais e preditos extraídos pela média da diferença absoluta sobre o conjunto de dados.
- MSE (erro quadrático médio) representa a diferença entre os valores originais e previstos extraídos ao quadrado da diferença média sobre o conjunto de dados.
- RMSE (Root Mean Squared Error) é a taxa de erro pela raiz quadrada de MSE.
- R-quadrado (coeficiente de determinação) representa o coeficiente de quão bem os valores se ajustam em comparação com os valores originais. O valor de 0 a 1 interpretado como porcentagens. Quanto maior for o valor, melhor será o modelo.

essas informações foram tiradas de um site em inglês, recomendo a leitura para quem estiver curioso por mais detalhes.
https://www.datatechnotes.com/2019/02/regression-model-accuracy-mae-mse-rmse.html
 
Finalmente ligamos nosso modelo e datatable ao widget Predictions e podemos ver o resultado que a regressão linear encontrou para cada linha. E assim concluímos.

//predictions


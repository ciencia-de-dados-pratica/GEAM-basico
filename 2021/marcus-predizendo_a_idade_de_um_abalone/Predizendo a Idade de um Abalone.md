# Predizendo a Idade de um Abalone

Neste documento iremos resolver um problema retirado do UCI Machine Learning Repository, onde iremos predizer a idade de um abalone, um gênero de molusco.

## Sobre o Dataset

Temos como atributos de um abalone o sexo, comprimento, diâmetro, altura, peso total, peso sem casca, peso das vísceras, peso da casca e anéis. Para definirmos a idade de um abalone é necessário cortar a concha pelo cone, tingi-la com corantes e contar o número de anéis com o auxílio de um microscópio. No entanto, podemos estimar a idade por meio de uma predição como faremos a seguir.

## Iniciando o Workflow

Para começarmos nosso *workflow* vamos importar o *dataset Abalone*, logo apos, faremos uma função que irá calcular a idade do Abalone. 

![01](https://i.imgur.com/2P82YNc.png)

Para calcular a idade devemos multiplicar o atributo *Rings* por 1.5, pois a cada 1.5 ano o Abalone aumenta um anel. 

![02](https://i.imgur.com/wGZDeA4.png)

Agora, iremos usar o *Select Columns* para tornar o atributo *age* nosso target.

![03](https://i.imgur.com/ow0bboR.png)

![04](https://i.imgur.com/g4DUl7K.png)

Após isso, dividiremos os dados em dois fluxos utilizando o *Data Sampler*, sendo 80% para treino e 20% para realizar o teste.

![05](https://i.imgur.com/yKqnqAW.png)

No fluxo de cima, iremos fazer uma *cross-validation*, onde utilizaremos o *Random Forest* e o *Linear Regression* e logo após ligaremos eles ao *widget Predictions* para efetuar a predição. Já no fluxo de baixo, iremos ligar os dados de teste ao *Select columns* para tornar os atributos *Rings* (anéis) e *Age* (idade) em dados meta e logo após ligaremos ao *widget Predictions*.

![06](https://i.imgur.com/jUq9gN9.png)

Por fim, podemos ver a predição da idade do *Random Forest* e do *Linear Regression*l no próprio *Predictions*.

![07](https://i.imgur.com/rG6g3GW.png)

## Referências
- <a href="https://orangedatamining.com">Orange Data Mining - Data Mining</a>
- <a href="https://archive.ics.uci.edu/ml/datasets/abalone">UCI Machine Learning Repository - Abalone Dataset</a>



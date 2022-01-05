# Ranqueamento de atributos

Em certos momentos quando queremos fazer uma predição, pode acontecer dos resultados serem muito precisos mesmo que não devessem, isso pode ocorrer caso ele já possua a resposta, ou seja, o algoritmo utiliza apenas um ou dois atributos que descartam os demais. Para demonstrar irei fazer um ranqueamento da relevância desses atributos.

## Sobre o Dataset

Utilizaremos o *dataset Abalone*, que foi utilizado no último documento. Os atribuídos desse dataset são:

Nome| Tipo
--------- | ------
Sexo | Categórico
Comprimento | Numérico
Diâmetro | Numérico
Altura | Numérico
Peso total| Numérico
Peso sem casca | Numérico
Peso das vísceras| Numérico
Peso da casca| Numérico
Anéis| Numérico


## Iniciando o Workflow

Vamos começar nosso *workflow* importando o *dataset Abalone* no *widget File* e definir o atributo *Rings* como *Target*, logo depois, iremos conecta-lo ao modelo de predição que será usado, neste documento iremos usar dois modelos para podermos compara-los, sendo eles, o *Random Forest* e o *Linear Regression*, e apos isso conectaremos todos os *widgets* ao *widget Rank* que ira nos dizer a importância dos atributos.

![01](https://i.imgur.com/CgtoHYX.png)

Dentro do *Rank* podemos ver a relevância de cada atributo

![02](https://i.imgur.com/oV4NYJp.png)


Se observamos os dados, podemos ver que o *Linear Regression* está basicamente utilizando um único atributo, o *sex*, que define o sexo do Abalone, já o *Random Forest* está um pouco mais balanceado.

Agora, se removermos os atributos *Sex* e *Shell weight* que são os mais relevantes, teremos uma mudança na distribuição.

![03](https://i.imgur.com/8t4lNBa.png)


Como podemos ver, a relevância ficou mais distribuída entre os atributos, com ênfase no *Linear Regression* que sofreu uma maior mudança. Porem, isso não é necessariamente bom, pois ao removermos atributos tão relevantes, aumentamos a taxa de erro de nosso algoritmo, por isso não é recomendado que isso seja feito em um *workflow* normal, este tem um objetivo demonstrativo.

Para vermos a mudança na taxa de erro irei adicionar o *widget Test and Score*

![04](https://i.imgur.com/wX7uYyC.png)

**Antes da remoção dos atributos**

![05](https://i.imgur.com/otVjR44.png)

**Depois da remoção dos atributos**

![06](https://i.imgur.com/MK8OXN9.png)

É evidente que a taxa de erro aumentou, podemos dar um enfoque no RMSE (Root Mean Square Error), ou raiz quadrada do erro-médio, que é uma boa medida para se considerar.

## Conclusão

Neste texto foi apresentado apenas uma das formas de se usar o *widget Rank*, mas ele é uma ferramenta poderosa que pode ser utilizado de varias outras formas, como por exemplo, seleção de subconjunto de recursos para aprendizado de máquina. Portanto, recomendo a leitura da documentação do *widget*  no site do Orange Data Mining.

## Link do video

- <a href="https://youtu.be/Sowm3bH4VUk">Ranqueamento de atributos</a>

## Referências

- <a href="https://orangedatamining.com">Orange Data Mining - Data Mining</a>
- <a href="https://archive.ics.uci.edu/ml/datasets/abalone">UCI Machine Learning Repository - Abalone Dataset</a>



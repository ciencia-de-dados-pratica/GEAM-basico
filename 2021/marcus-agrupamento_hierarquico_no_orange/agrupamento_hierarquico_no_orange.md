# Agrupamento Hierárquico no Orange

O Hierarchical Clustering, também conhecido como Agrupamento Hierárquico, é uma técnica de análise de agrupamentos muito utilizada, que visa agrupar os dados de forma hierárquica com base em suas características. Neste documento irei demonstrar como um *workflow* usando esse e outros *widgets*.

Para começarmos, vamos usar o *widget* *file* e usaremos o *dataset*  "brown-selected", um conjunto que agrupa dados de genes de fermento de padeiro. 

![01](https://i.imgur.com/m6sGeAd.png)

Agora ligaremos nosso *dataset* ao  *widget distances*, que irá computar a distância entre as linhas e colunas do dataset.

![02](https://i.imgur.com/aExadpP.png)
 
 O cálculo é feito por meio da fórmula da distância euclidiana, como é mostrado na imagem a seguir.
 
![03](https://i.imgur.com/CIRRBaV.png)

Após o *widget* fazer esse cálculo, podemos usar alguns outros *widgets* como por exemplo o *distance map*, ele nós permite visualizar a distância entre os dados com uma maior facilidade, por meio de um mapa de calor.

![04](https://i.imgur.com/MQ0kXUa.png)


Como podemos ver na legenda, quanto mais azul for a cor mais próximo é a distância entre os dados e quanto mais amarelado for, maior é a distância. 

Agora voltando ao tema, podemos realizar o *clustering* conectando os *widgets distances* e *Hierarchical Clustering*.

![05](https://i.imgur.com/lMv5RjG.png)

Esse *widget* exibirá um dendrograma que separa os dados com base na proximidade e semelhança entre eles.

![06](https://i.imgur.com/ihDUG71.png)

Por fim, podemos visualizar os dados com os *widgets data table e box plot*. Vale ressaltar que o *link* deve estar no *selected data*, assim poderemos selecionar a ramificação no *Hierarchical Clustering* que queremos visualizar pressionando *Ctrl* e clicando nas ramificações, essas seleções serão divididas em *clusters*.

![07](https://i.imgur.com/U8tM4ww.png)

![08](https://i.imgur.com/U5nwJb4.png)

![09](https://i.imgur.com/eLmmnkT.png)


## Referência
- <a href="https://orangedatamining.com">Orange Data Mining - Data Mining</a>



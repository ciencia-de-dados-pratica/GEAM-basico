begin
exemplo img:
<img src="2020-04-02-file-widget.png" width="600">



#Pré processamento de dados com Orange

Nesse tutorial, nossa finalidade será fazer a preparação e clusterização de dados.
para exemplificar utilizaremos uma planilha fictícia de funcionários que pode ser acessada por meio deste link: https://docs.google.com/spreadsheets/d/1mN7ifkPZfKT6h0Bel_TyvoHPdJvtK_OY879iheOVZPk/edit?usp=sharing

//img planilha funcionários

Para iniciar, utilizaremos o widget Process

###Widget no. 1: Preprocess

Pode normalizar variáveis de dados numéricos. Digamos que temos um conjunto de dados fictícios de pessoas empregadas em sua empresa. Queremos saber quais funcionários têm mais probabilidade de sair de férias, com base na renda anual, anos de trabalho em sua empresa e total de anos de experiência no setor. Se você plotar isso no mapa de calor, verá uma linha amarela em negrito em "renda anual". Obviamente, isso acontece porque a renda anual tem valores muito mais altos do que anos de experiência ou anos empregados pela sua empresa. Naturalmente, você gostaria que o salário não sobrecarregasse o restante do conjunto de recursos; portanto, a normalização é o caminho a percorrer. A normalização transformará seus valores em termos relativos, ou seja (dependendo do tipo de normalização) em uma escala de 0 a 1. Agora, o Mapa de Calor mostra com nitidez que as pessoas que estão empregadas há mais tempo e têm um salário mais alto costumam ir nos feriados. (este é um conjunto de dados totalmente fictício.)

//img mapa de calor

Pode imputar valores ausentes. A imputação média ou mais frequente do valor ausente pode parecer muito simples, mas na verdade funciona na maioria das vezes. Além disso, todos os alunos que precisam de imputação o fazem implicitamente, para que o usuário não precise configurar mais um widget para isso.
Se você deseja comparar seus resultados com um conjunto de dados misturado aleatoriamente, selecione "Aleatório" ou, se desejar selecionar recursos relevantes, esse é o widget.
O pré-processamento precisa ser usado com cautela e entendimento de seus dados para evitar a perda de informações importantes ou, pior ainda, o ajuste excessivo do modelo. Um bom exemplo é um caso de paramédicos, que geralmente não registram o pulso se for normal. Os valores ausentes aqui, portanto, não podem ser imputados por um valor médio ou número aleatório, mas como um valor distinto (pulso normal). O conhecimento do domínio é sempre crucial para a preparação dos dados.

###Widget no. 2: Discretize

//img

Para determinadas tarefas, você pode querer recorrer ao binning, que é o que o Discretize faz. Ele efetivamente distribui seus valores contínuos em um número selecionado de posições, tornando a variável discreta. Você pode discretizar todas as suas variáveis de dados de uma só vez, usando o tipo de discretização selecionado ou selecionar um método de discretização específico para cada atributo. O legal é que a transformação já é exibida no widget, para que você saiba instantaneamente o que está recebendo no final. Um bom exemplo de discretização seria ter um conjunto de dados de seus clientes com a idade deles gravada. Não faria sentido segmentar os clientes de acordo com cada idade específica, portanto, agrupá-los em quatro faixas etárias (jovem, adulto jovem, meia-idade, sênior) seria uma ótima solução. Além disso, algumas visualizações requerem transformação de recurso - o Diagrama de peneira é atualmente um desses widgets. O Mosaic Display, no entanto, tem a transformação já implementada internamente.

//img

dados originais

//img

Dados discretos com "anos de trabalho" inferiores ou superiores a / igual a 8 (o mesmo para 'renda anual' e 'experiência no setor').

###Widget no. 3: Continuize

Este widget cria essencialmente novos atributos a partir dos seus discretos. Se você tem, por exemplo, um atributo com a cor dos olhos das pessoas, em que os valores podem ser azul, marrom ou verde, você provavelmente desejaria ter três atributos separados 'azul', 'verde' e 'marrom' com 0 ou 1 se uma pessoa tiver a cor dos olhos. Alguns alunos têm um desempenho muito melhor se os dados forem transformados dessa maneira. Você também pode ter apenas atributos nos quais você presume que 0 é uma condição normal e gostaria apenas de registrar desvios do estado normal ('destino ou primeiro valor como base') ou o estado normal seria o valor mais comum ("valor mais frequente como base"). O widget Continuize oferece muito espaço para você jogar. O melhor é selecionar um pequeno conjunto de dados com valores discretos, conectá-lo ao Continuize e depois à Tabela de Dados e alterar os parâmetros. É assim que você pode observar as transformações em tempo real. É útil para projetar pontos de dados discretos na Projeção Linear.

###Widget no. 4: Purge Domain
//img

Enxugue e classifique seus dados. É isso que o Purge Domain faz. Se todos os valores de alguns atributos forem constantes, ele removerá esses atributos. Se você tiver atributos (vazios) não utilizados em seus dados, eles serão removidos. Efetivamente, você obterá um conjunto de dados agradável e abrangente no final.

//img
Dados originais

//img
Colunas vazias e colunas com o mesmo valor (constante) foram removidas. Obviamente, não se esqueça de incluir todos esses procedimentos em seu relatório com o botão "Relatório".

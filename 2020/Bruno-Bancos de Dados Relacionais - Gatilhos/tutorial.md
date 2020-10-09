# Gatilhos em Bancos de Dados Relacionais

Neste tutorial iremos fazer uma introdução sobre os Gatilhos em Bancos de Dados Relacionais e serão apresentadas algumas consultas básicas, [aqui](https://youtu.be/ATd29TCFF8o) é possível assistir a esse tutorial em vídeo no nosso canal do Youtube.

Gatilhos ou Triggers são objetos que determinam ações a serem executadas antes ou depois de um evento em uma tabela. Essas ações podem ser disparadas por comando SQL (statement) ou por linha (row).

Para se criar um gatilho é necessário que já exista uma função (strored procedure), a qual será usada como ação disparada por um evento. E essa função deverá ter o retorno do tipo TRIGGER.

### Criação das tabelas
Para demonstrar como funcionam os Gatilhos, neste tutorial, iremos utilizar como exemplo duas tabelas, a tabela **teste** que irá disparar o Gatilho, e a tabela **teste_log** que será acionada pelo Gatilho.

Segue abaixo os comandos de criação das duas tabelas.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/1-criacao-das-tabelas.png)

### Criação da Função

Para que se possa criar um Gatilho primeiramente deve-se criar uma Função, a qual o Gatilho irá acionar.

Antes de criar  a função deve-se definir  a linguagem a qual a função utiliza, como no exemplo abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/2-deficao-da-linguagem.png)

Abaixo, temos o comando de criação da Função **func_log**, que ao ser acionada registra uma nova tupla na tabela **teste_log**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/3-criacao-da-funcao.png)

### Criação do Gatilho

Agora que temos criada a função, podemos criar o Gatilho. Para criar um Gatilho, deve-se usar o comando **CREATE TRIGGER**, o nome  do Gatilho e  a ação desse Gatilho.

Abaixo, temos o comando de criação do nosso Gatilho. Todas as vezes que for feito um CREATE, um UPDATE ou um DELETE na tabela **teste**, o gatilho é acionado, em seguida ele chama a função **func_log** que registra a ação na tabela **teste_log**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/4-criacao-do-gatilho.png)

### Disparando o Gatilho

Agora que temos o nosso gatilho criado, vamos executar comandos que disparem esse gatilho, que são comandos de inserção, atualização e exclusão na tabela **teste**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/5-operacoes-na-teste.png)

### Resultado

Após a execução dos comandos acima, o gatilho foi disparado e as ações foram registradas na tabela **teste_log**.

Podemos verificar o resultado com o comando abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/6-select-testelog.png)

E o retorno deste comando é a tabela abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bancos%20de%20Dados%20Relacionais%20-%20Gatilhos/Imagens/7-Resultado.png)

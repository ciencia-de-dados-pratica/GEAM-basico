# Sequências em Bancos de Dados

Neste tutorial iremos falar sobre as sequências em Bases de dados e mostraremos um exemplo prático de como elas funcionam. [Aqui]() é possível assistir esse tutorial em vídeo no nosso canal do Youtube.

Uma seqüência gera uma lista serial de números exclusivos para as colunas das tabelas de um banco de dados. Elas simplificam a programação do aplicativo, gerando automaticamente valores numéricos exclusivos para as linhas de uma ou varias tabelas. Por exemplo, vamos assumir que dois usuários estejam inserindo simultaneamente linhas de novos empregados para a coluna EMP_NO nenhum usuário precisa esperar que o outro insira o próximo número disponível de empregado. A sequência gera automaticamente os valores corretos para cada usuário.

### Criação de uma sequência

Para criar uma sequência, é necessário digitar o comando **CREATE SEQUENCE IF NOT EXISTS**, em seguida o nome do arquivo e os parâmetros que definem suas propriedades, como valor máximo e valor mínimo.

A imagem abaixo mostra o comando de criação da sequência **teste_seq**.  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Sequencias_em_Bancos_de_Dados/Imagens/Captura%20de%20tela%20de%202021-01-22%2013-30-27.png)

### Utilizando a sequência

Uma vez criada a sequência ela pode ser utilizada, para isso, basta definir um campo da tabela na qual deseja utilizar a sequência com o comando: **DEFAULT nextval(nome da sequência)**.


A imagem abaixo mostra o comando de criação de uma tabela utilizando a sequência teste_seq no campo **teste_id**.  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Sequencias_em_Bancos_de_Dados/Imagens/Captura%20de%20tela%20de%202021-01-22%2013-30-27%20-%201.png)


### Inserindo valores na tabela

Para inserir valores na tabela, basta passar como parâmetro apenas os campos que não utilizam a sequência, pois ela irá gerar os valores para os campos que a utilizam.

A imagem abaixo apresenta o comando de inserção na tabela apresentada anteriormente, note que o coampo teste_id não é passado como parâmetro.  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20Sequencias_em_Bancos_de_Dados/Imagens/Captura%20de%20tela%20de%202021-01-22%2013-30-29.png)

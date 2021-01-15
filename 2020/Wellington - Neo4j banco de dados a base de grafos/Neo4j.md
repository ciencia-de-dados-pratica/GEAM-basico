# Introdução
  O Neo4j ́e um banco de dados **NoSQL** (Not Only SQL), no qual não utiliza a linguagem de consultas **SQL** (Standard Query Language), pois esse banco de dados tem sua essência
    voltada a grafos como esquema de organização e armazenamento, estes grafos contém **nós** e **arestas**, e no ecossistema do Neo4j os *nodes* (nós), são usados para
    representar as entidades da base de dados gerando uma relação entre si. Junto aos *nodes* existe as *labels* (rotulos), que são utilizadas para moldar o domínio de cada *node*
    os agrupando em conjuntos conforme sua etiqueta, a etiqueta é definida pela *label*, por exemplo, vários *nodes* contem informações sobre um único usuário, então esses *nodes*
    serão rotulados com a etiqueta **usuário**. Essa etiqueta ajuda na hora de consultas ou marcação de estados, fazendo um comparação ao modelo relacional, esses **nodes**
    correspondem aos **index**, que ajudam nas operações do **SGBD** (Sistema de Gereência de Banco de Dados).

# Cypher Query Language
 A equipe do Neo4j decidiu criar uma linguagem própria para a operação do **SGBD**, por ser o primeiro nesse
 mundo dos grafos, ainda não existia uma forma de realizar consultas via comando, por isso foi criado **Cypher**,
 essa linguagem é bem intuitiva e fácil de aprender (um dos propósitos dos desenvolvedores).
 ### Exemplos de consultas com Cypher
 ```
 CREATE (: Pessoa{nome: 'João', idade: 20, estadoCivil: 'Solteiro'})
 ```
 No exemplo acima, temos a criação de um *node*, começando com o comando de criação **CREATE** e definimos uma
 *label* com o nome **Pessoa** e em seguida suas propriedades de nome, idade e estado civil.
 ```
 MATCH (p1: Pessoa{nome: 'João'}), (p2:Pessoa{nome: 'Maria'})
 CREATE (p1)-[:SEGUE}->(p2)
```
No exemplo acima, é realizado a criação de um relaconamento entre João e Maria, denomidado **SEGUE**, significando
que João em uma rede social segue Maria. Esse comando funciona assim, **MATCH** é o comando de busca, p1 e p2 são
*alias* (apelidos) para não necessitar usar sempre a informação por completo, em seguida é feito o filtro do
primeiro *node* onde é buscado uma pessoa com o nome João, e em seguida o segundo filtro buscando uma pessoa com
o nome Maria. Após a consulta, é criado um relacionamento com o comando **CREATE** para ligar p1 a p2. O primeiro
traço indica que é um relacionamento, e entre colchetes é o nome desse relacionamento, em seguida temos uma flecha **->** que direciona o outro ponto do relacionamento.
```
MATCH (p:Pessoa {nome: 'João'})
SET p.estadoCivil = 'Casado'
```
No exemplo acima, é feita uma atualização no dado estado civil do *node*, onde **MATCH** é o comando de busca, p
é um *alias*, **SET** é o comando de atualização dos dados e em seguida, é escrita a propriedade existente que
será atualizada. Caso seja preciso adicionar um novo dado ao *node*, por exemplo a profissão de João, o comando
ficaria da seguinte forma:
```
MATCH (p.Pessoa {nome: 'João'})
SET p += {profissao: 'Progamador'}
```
Em um caso de precisar apagar uma propriedade do *node* pode-se usar o seguinte comando, atribuindo apenas *null*
ao que deseja remover.
```
MATCH (p:Pessoa{nome: 'João'})
SET p.estadoCivil = null
```

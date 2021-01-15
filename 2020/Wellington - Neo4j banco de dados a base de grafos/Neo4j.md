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
 
 

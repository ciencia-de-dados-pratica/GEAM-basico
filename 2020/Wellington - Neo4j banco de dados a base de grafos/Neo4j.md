# Introdução
O Neo4j ́e um banco de dados **NoSQL** (Not Only SQL), no qual não utiliza a linguagem de consultas **SQL** (Standard Query Language), pois esse banco de dados tem sua essência voltada a grafos como esquema de organização e armazenamento, estes grafos contém **nós** e **arestas**, e no ecossistema do Neo4j os *nodes* (nós), são usados para representar as entidades da base de dados gerando uma relação entre si. Junto aos *nodes* existe as *labels* (rotulos), que são utilizadas para moldar o domínio de cada *node* os agrupando em conjuntos conforme sua etiqueta, a etiqueta é definida pela *label*, por exemplo, vários *nodes* contem informações sobre um único usuário, então esses *nodes* serão rotulados com a etiqueta **usuário**. Essa etiqueta ajuda na hora de consultas ou marcação de estados, fazendo um comparação ao modelo relacional, esses **nodes** correspondem aos **index**, que ajudam nas operações do **SGBD** (Sistema de Gereência de Banco de Dados).

# Cypher Query Language
 A equipe do Neo4j decidiu criar uma linguagem própria para a operação do **SGBD**, por ser o primeiro nesse
 mundo dos grafos, ainda não existia uma forma de realizar consultas via comando, por isso foi criado **Cypher**,
 essa linguagem é bem intuitiva e fácil de aprender (um dos propósitos dos desenvolvedores).
 ### Exemplos de comandos com Cypher
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
Em um caso de precisar remover uma propriedade do *node* pode-se usar o seguinte comando, atribuindo apenas *null*
ao que deseja remover.
```
MATCH (p:Pessoa{nome: 'João'})
SET p.estadoCivil = null
```
Para excluir um *node* é bem simples, vejamos o exemplo a seguir:
```
MATCH (p:Pessoa{nome: 'João'})
DELETE p
```
O comando **DELETE** exclui o *node* atribuído a 'p', assim a pessoa que é João é removida da base de dados. Mas,
esse comando só funciona caso o *node* não possua relacionamentos. Caso haja relacionamentos, o comando para
excluir o relacionamento e em seguida o *node* é:
```
MATCH (:Pessoa {nome: 'João'})-[a:ADICIONOU}-()
DELETE a
```
Dessa forma os relacionamentos ligados a João que tenham o dado **ADICIONOU** serão excluídos, pois o filtro de *node* está vazio ou seja, é anônimo. Em seguida o *node* João pode ser deletado normalmente, porém, existe também um comando que pode excluir o *node* e seus relacionamentos de uma única vez.
```
MATCH (p:Pessoa {nome: 'João})
DETACH DELETE p
```
Ao adicionar **DETACH** a linha de comando, possibilida a exclusão do *node* com todos os relacionamentos atribuídos a ele.

# Modelo de Dados
A modelagem de dados do Neo4j funciona como um esboço em um quadro branco, assim é possível discutir e entender
como será criado o banco de dados. Após a ideia estiver mais concretizada, vai ser identificado as conrrespondências dos *nodes* e o formato de relacionamento, tornando o rabisco algo mais formal. Na próxima
etapa, será adicionado os rótulos a cada propriedade dos *nodes*. Nesse momento é feito uma referência para ver
se há uma coerência com a ideia no quadro branco, nessa parte o modelo fica mais consolidade e próximo do projeto final.
E por último, sai o modelo consolidado, o intuito é ser simples e bem visual, para facilitar seu compreendimento
por qualquer pessoa sem nenhum grande esforço. Segue um exemplo do modelo final, no qual mostra três pessoas que
são amigas e o que elas gostam em comum.
![Modelo de Dados Final](https://miro.medium.com/max/875/1*SiIW_VnSNDiawRvuGM3aGA.png)

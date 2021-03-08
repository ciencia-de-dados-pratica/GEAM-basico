# Introdução

<img src="img/cassandra-logo.png" width="250">

O **Cassandra** tornou-se *open source* em 2008 e em 2009 começou a ser mantido pela **Apache Foundatioin**, inicialmente
desenvolvido pelo Facebook para ser utilizado no motor de busca na caixa de mensagens. O modelo de distribuição é baseado
no banco **DynamoDB** que foi desenvolvido pela Amazon, e a forma de organização dos dados é baseado no **BigTable** que
foi desenvolvido pelo Google. **Cassandra** por concepçção foi feito para trabalhar de forma distribuída, sendo que não há
grandes vantagens em trabalhar com ele utilizando apenas uma máquina. Ao utilizar várias máquinas é possível ver o verdadeiro
potencial desse banco de dados.

# Arquitetura
Sua arquitetura é descentralizda, com isso, todos os nós existentes na rede possuem as mesmas funções e capacidades, não há um
ponto único de falha. Dessa forma sua manutenção se torna fácil por não precisar realizar configurações específicas para cada nó.
Os nós também não compartilham entre si nenhum tipo de recurso de hardware como disco, processamento ou memória, esse tipo de
arquitetura evita gargalos no sistema e permite que os nós sejam heterogêneos entre si. Por causa da arquitetura distribuída e
descentralizada, Cassandra é altamente escalável, principalmente para escalar de forma horizontal (conhecida também como escalabilidade
elástica). Se necessário mais performance para o banco de dados, basta adicionar mais nós na rede, descartando a ação de substituir
as máquinas atuais que processam toda a base de dados por máquinas mais poderosas(ou escalar verticalmente). Da mesma forma,
se a demanda de processamento diminuir, é possível remover alguns nós e conomizar na manutenção do sistema.
Os dados das tabelas do Cassandra passam automaticamente por um processo de particionamento utilizando a *partition key* da
tabela que, por padrão, é baseada em chave primária. 

# O Poder do Cassandra
Para detectar nós com indícios de falha, o Cassandra emprega o *gossip protocol*: de tempos em tempos os nós do cluster
trocam mensagens entre si, caso algum nó falhe sucessivamente ao responder as mensagens, ele é marcado como um nó
defeituoso e ações corretivas são disparadas em *background* como replicar os dados que estavam nesse servidor para
outros nós. Cassandra também é capaz de detectar se um dado retornado por um dos nós está desatualizado, assim, outro
nó será consultado em busca da versão mais recente do dado e é disparado um processo secundário para correção do dado
desatualizado.
É importante também entender os níveis de consistência ao ler e gravar dados no Cassandra. Ao fazer a inserção de um registro,
pode-se informar que os dados devem ser imediatamente replicados entre os nós responsáveis (o que é chamado de consistência
forte ou consistência imediata), ou, se a informação não é crítica, pode-se instruir que os dados sejam replicados aos poucos,
conforme a disponilidade do cluster (modo chamado de consistência fraca ou consistência eventual). Esse níveis de consistência
também são aplicáveis ao efetuar comandos de leitura. É importante ter em mente que quanto mais forte o níveo de consistência,
mais oneroso é para o sistema e maior a latência ao executar os comandos.

# A linguagem CQL
A linguagem CQL *(Cassandra Query Language)* é utilizada para as operações do Cassandra. Sua vantagem é que suas sintaxes
sao parecidas com as do SQL, facilitando o uso de quem já utiliza bases de dados relacionais. Como no SQL, os comandos no CQL
são dividios em três categorias básicas, sendo comando para:
* Definição das estruturas de dados; 
* Manipulação dos dados;
* Consultas.

A seguir será mostrado um exemplo de como criar um banco de dados dentro do Cassandra.
```
CREATE KEYSPACE IF NOT EXISTS "my_keyspace"
WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
```
No exemplo acima, primeiramente é criado um novo *keyspace* chamado **my_keyspace** caso ele não exista. Em seguida é informado
como será tratado a replicação dos dados por meio do parâmetro **replication**, que, por sua vez, possui duas propriedades:
* Class: indica qual o método de replicação será utilizado para distribuir as réplicas das partições, podendo ser **SimpleStrategy**,
que é um método padrão, assumindo que o cluster é composto de um único *data center* e irá criar um número de réplicas de
cada partição das tabelas desse *keyspace* igual ao valor especificado no parâmetro **replication_factor**; O **NetworkTopogyStrategy**,
permite que seja definido um fator de replicação para cada *data center* qeu faz parte do cluster, nesse caso, o parâmetro **replication_factor** não é utilizado, sendo necessáiro passar um conjunto de chaves e valores em que a chave é o nome do *data
center* e o valor é a quanitdade de réplicas para o mesmo.
* Replication_factor: indica quantos nós do cluster devem conter uma cópia de cada partição das tabelas deste *keyspace* caso o
método de replicação seja o **SimpleStrategy**.
Com o *keyspace* criado, o próximo passo é adicionar tabelas a ele, no exemplo a seguir temos um exemplo na criação de tabela.
```
CREATE TABLE "my_keyspace"."contacts" (
  contact_id uuid,
  first_name text,
  last_name text,
  phone_number text,
  PRIMARY KEY(contact_id)
);
```
No exemplo vemos a criação de uma tabela com o nome **contacts** dentro do *keyspace* que foi criado anteriormente. Também foi
definido quatro colunas para a tabela, **contact_id**, que é a chave primária e é do tipo **uuid** *(Universally Unique Identifier)*
, assegura que os valores dessa coluna serão únicos. As outras colunas são **first_name**, **last_name** e **phone_number**, todas
do tipo **text**. Como a chave-primária é composta por apenas uma coluna, ela também é uma *partition-key* dessa tabela, o hash
da *partition-key* é o que define em que partição da tabela as linhas serão armazenadas. É perceptível que se parece bastante
com o SQL, facilitando ainda mais o seu uso.

# Introdução
Bancos de Dados **NoSQL** são bancos que não utilizam a linguagem de cosulta **SQL** e sua distribuição é não-relacional,
esses tipos de bancos foram projetados para atender a necessade de *big data*, ou seja, dados em grande volume e
alta velocidade. Com isso, bancos **NoSQL** oferecem funcionalidades nativas para os tipos de bancos não-relacionais,
onde torna uma alternativa eficiente para armazenamento e consulta de dados. As tecnologias NoSQL são bem-vindas e
necessárias no mundo de banco de dados, especialmente por conta do *Big Data*, *key-value, document stores, graph databases* e outros paradigmas de armazenamento de dados não-relacionais permitem velocidade, flexibilidade e escalabilidade ao armazenar e acessar dados.
O site [DB-Engines](https://db-engines.com/en/ranking) relata conteúdos sobre a área de banco de dados, e mostra
um ranking dos *databases* mais usados atualmente sejam bancos relacionais ou não de acordo com a popularidade dos
**DBMS** (*Database Management Systems*).

# Bancos de Dados NoSQL
O movimento NoSQL teve sua origem em junho de 2009, para nomear um encontro promovido por Johan Oskarsson e Eric
Evans, que teve como objetivo discutir o crescente surgimento de soluções *open source* de armazenamento de dados
distribuídos não relacionais. Em outubro do mesmo ano, foi realizada a conferência "no:sql(east)", que redefiniu
o uso do termo NoSQL para descrever soluções de armazenamento de dados não relacionais. Importante entender que
NoSQL não significa "não ao SQL", mas sim "not only SQL" (não só SQL).

### MongoDB
O MongoDB é um banco de dados orientado a documentos ou seja, ele não usa esquema relacional, e sim documentos semelhantes ao formato **JSON** (*Java Script Object Notation*), para armazenar os dados. Esses documentos são
semelhantes a registros, com campos e valores, o **MongoDB** também suporta esquemas dinâmicos e é um software livre
e de código aberto, ele também fornece recursos necessários para um ambiente de produção como, balanceamento de
carga, replicação, indexação, consulta e pode atuar como um sistema de arquivos. Em seguida segue um exemplo
simples da estrutura do arquivo utilizado pelo **MongoDB**.
```
{
  id: "0bjs324dfb2",
  nome: "João",
  idade: 30,
  profissão: "Progamador"
}
```
### Cassandra
Originalmente desenvolvido no Facebook, esse banco de dados tem um mecanismo de banco de dados descentralizado,
distribuído e orientado a coluna. É otimizado para clusters, especialmente aqueles em vários datacenters, e graças
à sua atualização assíncrona e design sem *master*, o Cassandra fornece acesso de baixa latência a clientes. Esse
banco de dados também é gratuito e tem seu código aberto.
Cassandra é um banco de dados orientado por coluna, onde suas linhas realmente contêm dados verticais, que é tradicionalmente realizado em colunas realcionais. A vantagem do design de banco de dados orientado por coluna
é que alguns tipos de pesquisas de dados podem se tornar muito rápidos, uma vez que os dados desejados podem ser
armazenados consecutivamente em uma única linha. Dessa forma, juntamente com o modelo distribuído otimizado e
descentralizado, solidificou a popularidade de Cassandra ao longo dos anos.

### Redis
O Redis é a impletação de chave-valor mais popular e amplamente utilizado, chave-valor é um paradigma simples:
atribuiçaõ de valores às chaves para facilitar o acesso e o armazenamento desses valores, que sempre são encontrados através das suas chaves. O Redis realiza suas operações em memória, tornando seu acesso extremamente
rápido, oferecendo tempos de resposta menores que milissegundos permitindo milhões de solicitações por segundo. O
Redis é bem utilizado em aplicativos de tempo real como Jogos, Ad-Teche, Serviços Financeiros, Assistência Médica
e IoT.
Todos os dados do Redis residem na memória, ao contrário de bancos de dados que armazenam dados em discos ou SSDs. A eliminação da necessidade de acessar discos permite que datasotres na memória, como o Redis, evitem
tempos demorados em suas pesquisas acessando os dados em microssegundos.

### Amazon DynamoDB
O Amazon DynamoDB é um serviço de banco de dados em nuvem oferecido pela AWS (Amazon Web Service). O DynamoDB é
rápido e flexível para todas as aplicações que precisam de latência constante abaixo de 10 milissegundos em
qualquer escala. O serviço é um banco de dados em nuvem totalemnte gerenciado e compatível com modelos de armazenamento de documentos e de chave-valor. O desempenho é confiável e a escalabilidade automática de capacidade de *throughput* (taxa de transferência) fazem desse serviço a opção ideal para aplicações móveis, web e de jogos, tecnologia
de anúncios e IoT, entre muitas outras aplicações.

### Neo4j
Neo4j é um sistema de gerenciamento de banco de dados baseado em grafos (*Graph Database*), sendo o sistema mais
propular desta categoria em uso atualemtne. Um *Graph Database* é baseado em arestas que atuam como relacionamentos entre os vétices que são os *nodes* (nós), relacionando diretamente instâncias de dados com outras. E também, com outras listas, o Neo4j também possui uma implementação de código aberto. Os dados no Neo4j
podem ser acessados e atualizados através da Cypher Query Language, uma linguagem própria do Neo4j parecida com
à linguagem SQL.
Os bancos de dados baseados em grafos têm vantagens em alguns casos de uso, incluindo determinados cenários de
mineração de dados e reconhecimento de padrões, uma vez que as associações entre instâncias de dados são explicitamente declaradas.

# Conclusão
Cerca de aproximadamente 80% de Big Data são dados não estrutuados, armazenar e processar esses dados em bancos
relacionais não é uma tarefa viável, considerando principalmente que eles não foram concebidos com esse objetivo.
Exatamente aí os bancos de dados NoSQL estão sendo usados cada vez mais, para atender aplicações analíticas de Big Data.

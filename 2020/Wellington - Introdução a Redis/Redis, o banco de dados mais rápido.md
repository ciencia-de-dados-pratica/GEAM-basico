# Introdução
O Redis é um banco de dados **NoSQL** *(Not Only SQL)* que armazena suas estruturas de dados em memória, e uma carcterística que dá enfâse a sua história é ser um banco de dados
extremamente rápido. Seu nome significa *REmote DIctionary Server* no qual teve seu projeto iniciado em 2009 que surgiu para atender uma demanda de performace para análises de
logs em tempo real da statup de seu criador. Algumas empresas bem conhecidas utilizam o **Redis** desde suas primeiras versoes como, Twitter, GitHub, Pinterest, Snapchat, StackOverflow, entre outras. O que difere o **Redis** de outros bancos de dados, é que suas operações são feitas em memória, ou seja, não é necessáiro acessar o disco para
consultar ou gravar dados.

# A Capacidade do Redis
O **Redis** agora oferece tempos de resposta menores que milissegundos, permitindo milhões de solicitações por
segundo para aplicativos em tempo real em Jogos, Ad-Teche, Serviços Financeiros, Assistência Médica e IoT. O 
Redis é uma opção popular para armazenamento em cahche, gerenciamento de sessões, jogos, tabelas de classificação,
análises em tempo real, geoespaciais, veiculação de bate-papo, bate-papo/mensagens, streaming de mídia e aplicativos
de pub/sub.

# Como o Redis Funciona?
Todos os dados do Redis residem na memória, ao contrário de banco de dados que armazenam dados em discos ou SSDs.
A eliminação da necessidade de acessar discos permite que datastores na memória, como o Redis, evitem tempos de pesquisa e acessem os dados em microssegundos. O Redis apresenta estruturas de dados versáteis, alta disponibilidade, geoespaciais, scripts Lua, transações, persistência em disco e suporte a cluster, tornando mais
simples a criação de aplicativos em escala de Internet em tempo real.

# Datastore na Memória
Todos os dados do Redis residem na memória principal do servidor, ao contrário de bancos de dados como PostgreSQL,
Cassandra, MongoDB e outros que armazenam a maioria dos dados em discos ou SSDs. Nos bancos de dados tradicionais,
baseados em disco, a maioria das operações exige acesso ao disco. Por outro lado, datastores na memória como o Redis
não têm essa limitação. Dessa forma, os armazenamentos na memória podem oferecer suporte a volumes de operações e tempos de resposta que são uma ordem de magnitude maiores que as demais soluções de armazenamento. O resultado: performance execpcional, com operações de leitura ou gravação demorando em média menos de um milissegundo e suporte
a milhôes de operações por segundo.

# Estruturas Flexíveis de Dados
Ao contrário de datastores de chave-valor simples, que oferecem estruturas de dados limitadas, o Redis oferece
uma grande variedade de estruturas de dados para atender aos requisitos dos aplicativos. Os tipos de dados do
Redis incluem:
  * Strings - dados em texto ou binários com tamanho de até 512 MB
  * Listas - uma coleção de strings na ordem em que foram adicionadas
  * Conjuntos - uma coleção não ordenada de strings com o recurso de executar operações de interseção, união e diferente com outros tipos de conjuntos
  * Hashes - uma estrutura de dados para armazenar uma lista de campos e valores
  * Bitmaps - um tipo de dados que oferece operações com bits
  * HyperLogLogs - uma estrutura de dados probabilística para estimar os dados únicos em um conjunto de dados
  
# Simplicidade e Facilidade de Uso
O Redis simplifica a codificação, reduzindo a quantidade de código necessária para armazenar, acessar e usar
dados em aplicativos. Por exemplo, se o aplicativo tiver dados armazenados em um hashmap e você quiser armazenar
esses dados em um datastore, basta usar a estrutura de dados de hash do Redis para armazenar os dados. Uma tarefa
similar, em um datasotre sem estruturas de dados de hash, exigiria muitas linhas de código para a conversão de um
formato para o outro. O Redis é fornecido com estruturas de dados nativas e várias opções para manipular e interagir com dados. Mais de cem clientes de código aberto estão disponíveis para os desenvolvedores do Redis. As
linguagens compatíveis incluem Java, Python, PHP, C, C++, C#, JavaScript, Node.js, Ruby, R, Go e muitas outras.

# Alta Disponibilidade e Escalabilidade
O Redis oferece uma arquitetura de réplica principal em um único nó principal ou em uma topologia de clusters.
Dessa forma, pode-se criar soluções altamente disponíveis que oferecem performance e confiabilidade consistentes.
Qunado for necessário ajustar o tamanho do cluster, pode-seusar uma das diversas opções de escalabilidade vertical ou horizontal disponíveis. Assim, o cluster pode crescer com a demanda.

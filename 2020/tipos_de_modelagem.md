# Tipos de Modelagem
### Modelo Relacional
  * O modelo relacional foi criado em meados de 1970 e atualmente ele é o mais utilizado em bancos de dados.
  Com a sua chegada no mercado aconteceu uma grande revolução da área de banco de dados, pois era algo bem
  diferente do que se existia na década de 70, e mesmo com diversos outros modelos, o modelo relacional
  continua sendo o favorito de grandes empresas como Microsoft e Oracle.
  * O modelo relacional utiliza comandos da linguagem SQL (*Structured Query Language*) para suas implementações
  e manipulações, mas também promove o mapeamento do modelo de Entidade e Relacionamento (ER) para auxiliar a
  criação e entendimento na fase de projeto lógico do banco de dados.
  * Grandes empresas fornecem um sistema gerenciador de bancos de dados relacional como a IBM, Microsoft, Sybase e
  Oracle que são líderes de mercado na área. Os SGBDs mais populares são o Oracle BD, MySQL, PostgreSQL e Firebird.
  No modelo relacional os dados são representados e visualizados em formas de tabelas, onde cada linha da minha tabela é uma
  informação completa sobre o que está armazenado.
  * Um bom site para mexer com *SQL* é o [SQLite Online](https://sqliteonline.com/). Caso preferir instalar um
  SGBD em sua máquina, recomendo o [PostgreSQL](https://www.postgresql.org/download/) por ser gratuito e com uma
  boa usabilidade.
  
### Modelo de Documentos
  * É um banco de dados não relacional projetado para armazenar e consultar dados como documentos do tipo JSON.]
  Esse tipo de modelagem de dados surgiu para facilitar o trabalho dos desenvolvedores, pois ele segue o mesmo
  formato de código da aplicação que está sendo desenvolvida
  * O banco de dados mais popular para esse tipo de modelagem é o [MongoDB](https://www.mongodb.com/try) somente via
  terminal. Mas caso o ambiente do terminal não seja tão agradável, o MongoDB possui um serviço em ambiente gráfico
  que deve ser instalado fora parte, o [Robo3T](https://robomongo.org/download) é um das ferramentas que podem ser
  utilizado no MongoDB com ambiente gráfico, facilitando o manuseio do mesmo.
  
### Modelo chave-valor
  * É um outro tipo de banco de dados não relacional que usa um método de chave-valor simples para armazenar dados.
  Um banco de dados chave-valor armazena dados como um conjunto em pares que funciona como um identificador exclusivo.
  A chave e os valores podem ser qualquer coisa, desde objetos simples até objetos compostos complexos. Bancos de dados
  desse tipo são altamente particionáveis e permitem [escalabilidade horizontal](https://waldyrfelix.com.br/escalabilidade-vertical-vs-escalabilidade-horizontal-6a3981783477#:~:text=Escalabilidade%20%C3%A9%20a%20habilidade%20de,de%20trabalho%20com%20baixo%20custo.)
  que outros tipos de bancos não conseguem alcançar.
  * Alguns SGBDs que contemplam o modelo chave-valor são o Redis e o Amazon DynamoDB. Pois esse tipo de banco ele
  normalmente é utilizado em várias máquinas ao mesmo tempo, como se fosse um datacenter.
  
### Modelo Orieantado a Objetos
  * Um tipo de banco de dados que guarda as informações em formas de objetos onde os dados só podem ser manipulados
  através de métodos definidos pela classe onde o objeto está. O modelo segue o padrão do conceito de orientação a objetos, 
  proporcionando uma facilidade na sua manutenção, pois os objetos são modulares e mudanças podem ser feitas de forma
  interna sem afetar outras partes do banco. Com isso, aumenta a produtividade e a segurança em seus dados, motivo para projetos
  espaciais, de telecomunicações, áreas cientificas como física de alta energia e biologia molecular utilizarem esse modelo.
  * O modelo OO se torna mais fácil de utilizar do que o modelo relacional nas situações de dados complexos, pois a sua organização
  é mais organizada que a do modelo relacional. Outro motivo para se utilizar este modelo, é sua aplicação ser construída
  em linguagens Orientadas a Objetos como Java, C++, C# entre outras. Seu uso vem se intensificando conforme os dias
  se passam, tornando-se um padrão em várias aplicações de software.
  
### Modelo Hieráquico
  * Primeiro modelo a ser conhecido como modelo de dados, contempla uma estrutura de árvore e sua formação se dá
  através de registros de links, onde cada registro é uma coleção de dados e o link é uma associação entre dois registros.
  Os registros que precedem outros são chamados de registro pai, os demais são chamados de registros filhos. Cada
  registro tem suas ligações, o registro pai pode ter vários filhos (1:N), o registro filho só pode ter um pai.
  * Para acessar seus registros deve-se obedecer aos padrões desse modelo. A navegação deve começar no topo da árvore (root)
  e ler sempre da esquerda para a direita.
  * Alguns bancos de dados que utilizam este modelo são o IMS DBMS da IBM.
  
### Modelo de Redes
  * Surgiu para suprir as deficiências do modelo hieráquico abolindo seu o conceito, pois nesse novo modelo era permitido
  que um registro tenha várias associações aceitando relacionamentos (N:M), nesse caso um filho pode ter mais de um pai,
  trabalhando somente com dados primitivos. E a principal diferença entre o modelo hierárquico para o de redes, é que
  o de redes utiliza grafos ao invés de árvores.
  * Bancos de dados deste modelo são o IDS e o IDMS.
  
### Search Engine
  * Não é uma modelagem de dados, mas é algo bem utilizado na área de banco de dados. É um motor de busca que utiliza
  um conjunto de técnicas que influenciam os algoritmos dos buscadores a definir um ranking de quais palavras são mais
  procuradas em uma página de dados. Uma ferramenta poderosa para buscas e análises de dados é o [Elastcsearch](https://www.elastic.co/pt/),
  que permite a indexação de documentos com grandes volumes de dados para realizar buscas praticamente em tempo real.
  * No momento que documento é indexado, o Elasticsearch separa todos os seus termos em Tokens. Em seguida ele faz uma
  medição para definir quais tokens são relevantes, eliminando assim artigos, preposições etc. Posteriormente é
  feita a organização dos tokens em um índice e informar quais documentos cada token contém. Quando a busca for
  feita ela agirá sobre o índice ao invés de vasculhar cada documento individualmente.
  * Um exemplo são as pequisas realizadas nos browsers como o Google, o mesmo utiliza um serviço de search engine em
  suas pesquisas, para entregar um melhor resultado ao usuário, por isso, as pesquisas no navegador são bem rápidas.
  
### Referências
  * https://www.ic.unicamp.br/~geovane/mo410-091/Ch03-RM-Resumo.pdf
  * https://db-engines.com/en/ranking
  * https://aws.amazon.com/pt/nosql/document/
  * https://www.devmedia.com.br/o-que-e-elasticsearch/40207
  * https://aws.amazon.com/pt/nosql/key-value/
  * http://fsma.edu.br/si/edicao3/banco_de_dados_orientado_a_objetos.pdf

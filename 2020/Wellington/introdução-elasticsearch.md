# Introdução

<img src="img/elasticsearch.jpg" width="250">

O **Elastcsearch** é um software *open source*, poderoso para realizar buscar e analisar dados em grandes
volumes de dados, ele permite indexar e realizar buscas no documentos quase em tempo real para todos
os tipos de dados. Ele possui uma interface RESTful e é capaz de solucionar um número crescente de casos de uso. Existe a Elastc
Stack, na qual contém ferramentas como o **Logstash** e **Beats** que facilitam a coleta, a agregação e o
enriquecimento dos dados armazenados no Elasticsearch. Outra ferramenta desse conjunto é o **Kibama** que
permite a expliração, vizualização e compartilhamento dos dados de forma interativa, de forma que contribua
para o gerenciamento e monitoramento.

# Índices
A proposta do Elastcsearch é ser extremamente rápido nas operações de busca e análise, e para ser mais
completo, ele realiza análise de vários tipos de dados, desde textos não estruturados a dados geoespaciais,
o Elastcsearch pode armazenar e indexar esses dados com eficiência gerando pesquisas rápidas. Na medida
que o volume de dados e consultas crescem, a natureza distribuída do Elasticsearch permite que sua
implantação cresça perfeitamente junto.

Os índeces podem ser configurados em dois níveis, **estático** que pode ser definido no momento da criação
do índice ou em um índice fechado, e **dinâmico** que pode ser alterado em um índice ativo usando a API
*update-index-settings*. Um índice fechado ele é bloqueado para operações de leitura / gravação e não permite
todas as operações permitidas pelos índices abertos. Dessa forma, não é possivel indexar documentos ou pesquisar
documentos em um índice fechado. Para reabrir índices fechados, basta usar a API de índice aberto, se a solicitação
for direcionada a um fluxo de dados, a solicitação reabrirá qualquer um dos índices de apoio que estejam fechados.

# Porque usar Elasticsearch

<img src="img/pq.jpg" width="250">

O Elasticsearch realiza buscar por índice invertido, com isso, o Elasticsearch realiza a separação de todos
os termos em *tokens*. Em seguida é feito uma medição para definir quais *tokens* são relevantes, o próximo
passo é organizar os tokens em um índice e informar a cada token quais documentos ele contém. Agora quando uma
busca for feita, ela sera realizada sobre o índice invertido ao invés de vasculhar cada documento individualmente,
procurando pelos termos buscados. Por causa dessa funcionalidade, o Elasticsearch é um motor de busca em semmi-tempo-real.

# Comandos no Elasticsearch
Como o Elastcsearch disponibiliza uma API REST para sua utilização, de forma padrão ela rebebe métodos
HTTP: (GET, POST, PUT e DELETE), as requisições funcionam pro meio do envio de objetos JSON.

Uma requisição segue a seguinte estrutura:
```
METODO_HTTP endereco_da_api:porta/indice/tipo_documento
```

No exemplo a seguir, é mostrado a indexação de um documento através de uma requisição do tipo POST
para a API.

<img src="img/elasticsearch-post.png" width="500">

Nessa representação acima, onde é enviado uma requisição HTTP do verbo POST ao *endpoint* da API
local do Elasticsearch. Essa operação também pode ser feita através de uma ferramenta como o
[Postman](https://www.postman.com/) ou o [Insomnia](https://insomnia.rest/). O objeto JSON contém
o corpo da requisição que informa os dados que serão indexados como um documento no Elasticsearch.

Em seguida é mostrado a forma mais comum de realizar buscas no Elasticsearch que são as querie, além
de encontrar todos os documentos que possuam o termo buscado, ordena-os por relevância com base em
um cálculo interno.

<img src="img/elasticsearch-get.png" width="500">

No exemplo acima, foi iniciado a abertura de uma query JSON, ela foi definida com a tarefa de realizar
a combinação entre o termo buscado (match) e os termos dos documentos, também é definido o que
está sendo buscando que é um documento que tenha o campo `cargo` com valor igual a `Joao`.

# Conclusão
Vemos a mágica proporção de eficiência do Elasticsearch, ele em si não é uma base dados, mas uma
mecanismo de busca que atua em cima de uma base de dados, onde foi citado o Kibama.

Empresas que utilizam a ferramenta:
  * Audi
  * Adobe
  * Lenovo
  * Walmart
  * Kroger

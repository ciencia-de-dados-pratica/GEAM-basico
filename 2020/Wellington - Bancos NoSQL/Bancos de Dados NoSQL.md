# Introdução
Bancos de Dados **NoSQL** são bancos que não utilizam a linguagem de cosulta **SQL** e sua distribuição é não-relacional,
esses tipos de bancos foram projetados para atender a necessade de *big data*, ou seja, dados em grande volume e
alta velocidade. Com isso, bancos **NoSQL** oferecem funcionalidades nativas para os tipos de bancos não-relacionais,
on de torna uma alternativa eficiente para armazenamento e consulta de dados. As tecnologias NoSQL são bem-vindas e
necessárias no mundo de banco de dados, especialmente por conta do *Big Data*, *key-value, document stores, graph databases* e outros paradigmas de armazenamento de dados não-relacionais permitem velocidade, flexibilidade e escalabilidade ao armazenar e acessar dados.
O site [DB-Engines](https://db-engines.com/en/ranking) relata conteúdos sobre a área de banco de dados, e mostra
um ranking dos *databases* mais usados atualmente sejam bancos relacionais ou não de acordo com a popularidade dos
**DBMS** (*Database Management Systems*).

# Bancos de Dados NoSQL
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

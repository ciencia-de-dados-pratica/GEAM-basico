# Tabelas Temporárias em Bancos de Dados

Neste tutorial iremos fazer uma introdução sobre as tabelas temporárias em bancos de dados, e será apresentado um exemplo prático dessas tabelas. [aqui]() é possível assistir a esse tutorial em vídeo no nosso canal do Youtube.

No decorrer de nossos projetos, há momentos em que a recuperação de dados para um complexo requisito de negócio requer que armazenemos temporariamente um ou mais conjuntos de resultados por um curto período de tempo. Normalmente estas tabelas temporárias são armazenadas no escopo da conexão atual, mas elas também podem precisar estar disponíveis em múltiplas conexões.

As tabelas temporárias são usadas com maior frequência para fornecer espaço de trabalho para os resultados intermediários no processamento de dados dentro de um lote ou de um procedimento. As tabelas temporárias incluem dentre outros aspectos, as tabelas temporárias locais, tabelas globais temporárias, tabelas temporárias persistentes.

### Criação das Tabelas físicas

Para utilizar como exemplo neste  tutorial iremos criar duas tabelas e inserir alguns valores nessas tabelas.

Os comandos abaixo, apresentam a criação e povoamento da tabela **Clientes**, que contem os campos: **id** e **nome**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20Tabelas%20Tempor%C3%A1rias/Imagens/Imagem01.png)

Os comandos abaixo são referentes a segunda tabela, que é a tabela **Compras**, que tem os campos: **id_Cliente** e **valor**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-%20Tabelas%20Tempor%C3%A1rias/Imagens/Imagem02.png)

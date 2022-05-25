# Junções SQL

### Introdução

É impossível deixar todos os dados que se conectam em uma tabela só. Em um banco de dados relacional, as tabelas se interligarão por indicadores que apontam para um valor específico em outras tabelas (chaves estrangeiras). O que as junções (**joins**) fazem, de maneira simplificada, é seguir a trilha entre as tabelas, ver onde elas se conectam e juntar as informações de maneira lógica em uma consulta só.

> **Um JOIN é um meio de combinar colunas de uma (auto-junção) ou mais tabelas, usando valores comuns a cada uma delas. O SQL padrão ANSI especifica cinco tipos de JOIN: INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN e CROSS JOIN.**

### INNER JOIN

> **SELECT** * **FROM** tabelaA **INNER JOIN** tabelaB **ON** tabelaA.key = tabelaB.key;

Esta consulta retorna todas as linhas que satisfazem a condição de junção (**ON** tabelaA.key = tabelaB.key;), juntando as linhas onde a condição é verdadeira em uma nova linha com todas as colunas selecionadas de ambas as tabelas.

Exemplo:



### Fontes:
 > https://www.alura.com.br/artigos/join-em-sql?gclid=CjwKCAjwp7eUBhBeEiwAZbHwkS2P7pzAUPexLtZD-xiNm8R_qNrtdC3WRriCy61UmfgUorlZ27Xw1RoCy2wQAvD_BwE

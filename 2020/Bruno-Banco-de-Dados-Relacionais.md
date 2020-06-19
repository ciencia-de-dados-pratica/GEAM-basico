# Banco de Dados Relacionais - Conceitos de chaves

Um Banco de dados relacional é uma coleção de relações, que são tabelas bidimensionais, onde os dados são armazenados.No modelo relacional os dados são organizados em coleções de tabelas bidimensionais. Essas tabelas são também chamadas de “Relações”.  

O **Relacionamento** é a associação entre as entidades (tabelas), conectadas por chaves primárias e chaves estrangeiras.  

**Chave Primária** (Primary Key / PK): coluna (atributo) que identifica um registro de forma exclusiva na tabela.  

**Chave Estrangeira** (Foreign Key / FK): coluna que define como as tabelas se relacionam umas com as outras. Uma FK se refere a uma PK ou a uma chave única em outra tabela (ou na mesma tabela!).  

A seguir são apresentadas as implementações de três tabelas:  

**CREATE TABLE Aluno(
  **Num_Matricula int Primary Key,
  **Nome_Aluno varchar(20),
  **Sexo_Aluno varchar(1)
**)

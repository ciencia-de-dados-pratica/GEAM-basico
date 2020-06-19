# Banco de Dados Relacionais - Conceitos de chaves

Um Banco de dados relacional é uma coleção de relações, que são tabelas bidimensionais, onde os dados são armazenados.No modelo relacional os dados são organizados em coleções de tabelas bidimensionais. Essas tabelas são também chamadas de “Relações”.  

O **Relacionamento** é a associação entre as entidades (tabelas), conectadas por chaves primárias e chaves estrangeiras.  

**Chave Primária** (Primary Key / PK): coluna (atributo) que identifica um registro de forma exclusiva na tabela.  

**Chave Estrangeira** (Foreign Key / FK): coluna que define como as tabelas se relacionam umas com as outras. Uma FK se refere a uma PK ou a uma chave única em outra tabela (ou na mesma tabela!).  

A seguir são apresentadas as implementações de três tabelas:  

**CREATE TABLE Aluno(**  
  **Num_Matricula int Primary Key,**  
  **Nome_Aluno varchar(20),**  
  **Sexo_Aluno varchar(1)**  
**)**  

**CREATE TABLE Disciplina(**  
	**Codigo varchar(10) Primary Key,**  
	**Nome varchar(15),**  
	**Carga_Horaria int**  
**)**  

**CREATE TABLE Matricula(**
	**Num_Matricula int Primary Key,**
	**Matr_Aluno int references Aluno(Num_Matricula),**
	**Codigo_Disciplina varchar(10) references Disciplina(Codigo)**
 **)**

Na tabela **Aluno** o campo **Num_Matricula** definido como **Primary Key**, é sua chave primaria.  

Na tabela **Disciplina** o campo **Codigo** definido como **Primary Key** é sua chave primaria.  

A tabela **Matricula** tem os campos, **Num_Matricula** que é sua chave primaria, **Matr_Aluno**, que uma chave estrangeira 
(Foreign Key) referente ao **Num_Matricula** da tabela **Aluno** e **Codigo_Disciplina** que é uma outra chave estrangeira 
referente ao **Codigo** da tabela **Disciplina**.

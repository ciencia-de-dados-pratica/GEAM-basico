# Banco de Dados Relacionais - Conceitos de chaves

Um Banco de dados relacional é uma coleção de relações, que são tabelas bidimensionais, onde os dados são armazenados.No modelo relacional os dados são organizados em coleções de tabelas bidimensionais. Essas tabelas são também chamadas de “Relações”.  

O **Relacionamento** é a associação entre as entidades (tabelas), conectadas por chaves primárias e chaves estrangeiras.  

**Chave Primária** (Primary Key / PK): coluna (atributo) que identifica um registro de forma exclusiva na tabela.  

**Chave Estrangeira** (Foreign Key / FK): coluna que define como as tabelas se relacionam umas com as outras. Uma FK se refere a uma PK ou a uma chave única em outra tabela (ou na mesma tabela!).  

A seguir são apresentadas as implementações de três tabelas:  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bacos-de-Dados-Relacionais-Conceitos-de-Chaves/Imagens/Imagem%201.png) 

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bacos-de-Dados-Relacionais-Conceitos-de-Chaves/Imagens/Imagem%202.png) 

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bacos-de-Dados-Relacionais-Conceitos-de-Chaves/Imagens/Imagem%203.png)    

Na tabela **Aluno** o campo **Num_Matricula** definido como **Primary Key**, é sua chave primaria.  

Na tabela **Disciplina** o campo **Codigo** definido como **Primary Key** é sua chave primaria.  

A tabela **Matricula** tem os campos, **Num_Matricula** que é sua chave primaria, **Matr_Aluno**, que uma chave estrangeira 
(Foreign Key) referente ao **Num_Matricula** da tabela **Aluno** e **Codigo_Disciplina** que é uma outra chave estrangeira 
referente ao **Codigo** da tabela **Disciplina**.  

## Inserção

Para realizar a inserção na tabela **Matricula** com valores que não sejam nulos, primeiro deve-se inserir os valores nas tabelas **Aluno** e **Disciplina**, como mostrado a seguir.  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bacos-de-Dados-Relacionais-Conceitos-de-Chaves/Imagens/Imagem%204.png)  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bacos-de-Dados-Relacionais-Conceitos-de-Chaves/Imagens/Imagem%205.png)  

Apos a inserção pode-se inserir a matricula da aluna **Maria** na disciplina de **FUP**, pois elas já existem no Banco de Dados.  

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Bacos-de-Dados-Relacionais-Conceitos-de-Chaves/Imagens/Imagem%206.png)  

Desse modo é possível povoar o Banco de Dados.

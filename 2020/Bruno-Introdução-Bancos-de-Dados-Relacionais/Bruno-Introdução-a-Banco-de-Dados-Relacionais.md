# Introdução a Banco de Dados Relacionais

Um banco de dados é uma aplicação que lhe permite armazenar e obter de volta dados com eficiência. O que o torna relacional é a maneira como os dados são armazenados e organizados no banco de dados.Um Banco de Dados Relacional consiste em uma coleção de tabelas, por sua vez uma tabela é composta por linhas e colunas.

Para criar uma tabela em um Banco de Dados Relacional, deve-se executar o comando Data Definition Language (DDL) CREATE, como  no exemplo da tabela Aluno abaixo.  
  
**CREATE TABLE Aluno(**  
	**Num_Matricula int,**  
    **Nome_Aluno varchar(20),**  
    **Sexo_Aluno varchar(1)**  
**)**    

Após a tabela estar criada no Banco de Dados, pode-se inserir valores nela como no exemplo abaixo.  

**INSERT INTO Aluno (Num_Matricula, Nome_Aluno, Sexo_Aluno) values (1,'João','M'),(2,'Maria','F')**  

É possível buscar a tabela no banco executando o seguinte comando.  

**SELECT * FROM Aluno**  

É possível realizar a exclusão de duas formas.  

No primeiro caso é possível excluir as linhas da tabela com o comando a seguir:  

**DELETE FROM Aluno**  

No segundo caso é possível excluir a tabela do Banco de Dados com comando a seguir:  

**DROP TABLE Aluno**

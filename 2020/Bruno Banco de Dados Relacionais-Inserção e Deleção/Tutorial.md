# Banco de Dados Relacionais - Inserção e Deleção

Neste tutorial serão apresentados  alguns conceitos de inserção e remoção em Banco de Dados relacionais. Para isso serão utilizadas duas tabelas como exemplo:

A tabela  pai que é **Aluno**, e a tabela filha que é **Matricula**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%201.png)  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%202.png)

Observe que a tabela **Matricula** tem uma chave estrangeira referente a matricula do aluno, esse valor na tabela **Matricula** esta definido como **ON DELETE CASCADE**.

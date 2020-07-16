# Banco de Dados Relacionais - Inserção e Deleção

Neste tutorial serão apresentados  alguns conceitos de inserção e remoção em Banco de Dados relacionais. Para isso serão utilizadas duas tabelas como exemplo:

A tabela  pai que é **Aluno**, e a tabela filha que é **Matricula**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%201.png)  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%202.png)

Observe que a tabela **Matricula** tem uma chave estrangeira referente a matricula do aluno, esse valor na tabela **Matricula** esta definido como **ON DELETE CASCADE**.

## Inserção
Para realizar a inserção na tabela **Aluno** é necessário verificar se a chave primaria não esta se repetindo, essa é a única restrição pois a tabela não tem referencia a chaves de outras tabelas.

Observe abaixo o exemplo de uma inserção.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%203.png)

Para inserir valores na tabela **Matricula** é necessário atender a algumas restrições, como a  tabela tem uma chave estrangeira referente a tabela **Aluno** é necessário verificar se o valor a ser inserido na tabela **Matricula** existe na tabela **Aluno**.

O exemplo abaixo mostra uma forma correta de fazer essa inserção.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%205.png)

Uma outra forma de fazer essa inserção é passar um valor nulo no campo da chave estrangeira, pois assim não é necessário que exista o valor na tabela **Aluno**. Como é mostrado no exemplo abaixo.


![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%206.png)

Neste outro exemplo não é possível realizar essa inserção, pois o valor passado na chave estrangeira não existe na tabela **Aluno**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%204.png)

Outra forma da problema na inserção é tentar inserir duas tuplas na mesma tabela com  a chave primaria igual, pois a chave primaria deve ser única na tabela. Observe no exemplo abaixo, neste caso as matriculas nas disciplinas de FUP e ED têm chaves primaria igual.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%205.png)

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%207.png)

## Deleção

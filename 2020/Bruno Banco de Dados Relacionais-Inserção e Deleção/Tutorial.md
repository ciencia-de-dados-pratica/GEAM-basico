# Banco de Dados Relacionais - Inserção e Deleção

Neste tutorial serão apresentados  alguns conceitos de inserção e remoção em Banco de Dados relacionais. [Aqui](https://www.youtube.com/watch?v=Y8t1OUgFqG4) é possível assistir a esse tutorial em vídeo no Youtube.

Para este tutorial serão utilizadas duas tabelas como exemplo:

A tabela  pai que é **Aluno**, e a tabela filha que é **Matricula**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%201.png)  
![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%202.png)

Observe que a tabela **Matricula** tem uma chave estrangeira referente a matricula do aluno, esse valor na tabela **Matricula** está definido como **ON DELETE CASCADE**.

## Inserção
Para realizar a inserção na tabela **Aluno** é necessário verificar se a chave primaria não está se repetindo, essa é a única restrição pois a tabela não tem referencia a chaves de outras tabelas.

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

Para realizar a deleção de tuplas na tabela **Aluno** existe restrições, pois a tabela esta sendo referenciada na tabela **Matricula**. Na definição da tabela **Matricula** a chave estrangeira foi definida com **ON DELETE CASCADE**, desse modo sempre que uma tupla for deletada na tabela **Aluno** é realizada também a deleção de todas as tuplas da tabela **Matricula** que referenciam aquela tupla da tabela aluno.

No exemplo abaixo é apresentada a deleção de uma tupla da tabela **Aluno** com a chave primaria 1, neste caso também são deletadas todas as tuplas da tabela **Matricula** que tenham na chave estrangeira o valor 1.


![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%208.png)

Como não existe nenhuma tabela que referencia a tabela **Matricula**, a deleção de tuplas nesta tabela ocorre de forma simples, como mostrado no exemplo abaixo, pois esse processo não afeta nenhuma outra tabela. 

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20Banco%20de%20Dados%20Relacionais-Inser%C3%A7%C3%A3o%20e%20Dele%C3%A7%C3%A3o/Imagens/Imagem%209.png)

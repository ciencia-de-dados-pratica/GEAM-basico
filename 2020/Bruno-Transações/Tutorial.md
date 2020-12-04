# Transações em Bancos de Dados

Neste vídeo, falamos sobre transações em bancos de dados, são apresentados os conceitos teóricos e um exemplo prático de como elas podem ser usadas. [Aqui](https://youtu.be/4gP4fVUhQ0o) é possível assistir esse tutorial em vídeo no nosso canal do Youtube.

Uma transação geralmente representa qualquer alteração em um banco de dados.

As transações devem garantir as propriedades ACID.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem08.png)

ACID é um conceito que se refere às quatro propriedades de transação de um sistema de banco de dados: Atomicidade, Consistência, Isolamento e Durabilidade.

**Atomicidade** - Trata o trabalho como parte indivisível (atômico). A transação deve ter todas as suas operações executadas em caso de sucesso ou, em caso de falha, nenhum resultado de alguma operação refletido sobre a base de dados. Ou seja, após o término de uma transação (commit ou rollback), a base de dados não deve refletir resultados parciais da transação.

**Consistencia** - A execução de uma transação deve levar o banco de dados de um estado consistente a um outro estado consistente, ou seja, uma transação deve respeitar as regras de integridade dos dados (como unicidade de chaves, restrições de integridade lógica, etc.). 

**Isolamento** - Em sistemas multi usuários, várias transações podem acessar simultaneamente o mesmo registro (ou parte do registro) no banco de dados. Por exemplo, no mesmo instante é possível que um usuário tente alterar um registro e outro usuário esteja tentando ler este mesmo registro. 

**Durabilidade** - Os efeitos de uma transação em caso de sucesso (commit) devem persistir no banco de dados mesmo em casos de quedas de energia, travamentos ou erros. Garante que os dados estarão disponíveis em definitivo. Em um banco de dados relacional, por exemplo, quando um grupo de instruções SQL é executado, os resultados precisam ser armazenados permanentemente (mesmo que o banco de dados falhe imediatamente depois). Para se defender contra a perda de energia, as transações (ou seus efeitos) devem ser registradas em uma memória não volátil.

### Comandos básicos

Para executar as transações usaremos 3 comandos basicos.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem01.png)

**BEGIN** - Da inicio a transação.

**COMMIT** - Finalisa a transação e salva as alterações feitas no Banco de Dados.

**ROLLBACK** - Finalisa a transação desfazendo as alterações feitas no Banco de Dados.

### Criação da tabela

Para este tutorial iremos utilizar a tabela Clientes apresentada abaixo.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem02.png)

### Executando as transações

Primeiramente iremos executar o comando de inserção apresentado abaixo. Ao executar esse comando, o SGBD controla a transação para realização da inserção.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem03.png)

Agora vamos executar uma transação onde podemos controlar, nesse caso iremos dar um COMMIT na transação para que a inserção seja realizada.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem04.png)

O comando abaixo é uma transação como a que vemos acima, a diferença é que executamos um ROLLBACK e a inserção não será salva no Banco de Dados.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem05.png)

### Resultado

Vamos utilizar o comando abaixo para apresentar a tabela após a execução das transações.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem06.png)

A tabela abaixo apresenta o resultado do comando acima.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Transa%C3%A7%C3%B5es/Imagens/Imagem07.png)

# Gerenciamento de Usuários e Permissões no PostgreSQL - parte 1

<br>
<br>
<br>
<br>

### Neste texto, vamos trabalhar com o gerenciamento dos usuários e seus privilégios no Banco de dados PostgreSQL. A princípio vamos ver o básico da construção dos Usuários, grupos (GROUP), papéis/funções (ROLE).


[Criando um Usuário no Banco de Dados](#Criando-um-Usuário-no-Banco-de-Dados) 


<br>

<br>

****

<br>


Em praticamente todos os bancos de dados é encontrado um conjunto de usuários que usam o BD. Porém esses usuários são diferentes dos usuários que são gerenciados pelo o SO (Sistema Operacional) no qual o servidor executa.  Eles possuem objetos de banco de dados (por exemplo,
tabelas, visões etc.), e podem conceder privilégios nestes objetos para outros usuários
controlando, assim, quem pode acessar qual objeto.



<br>
<br>
<br>


## Criando um Usuário no Banco de Dados

<br>

Para Criarmos esse tipo de usuário descrito acima, podemos utilizar o comando em SQL CREATE USER do PostgreSQL. Esse comando adiciona um novo usuário no banco de dados no qual foi executado o script. O mais usual atualmente é o CREATE ROLE em vez do CREATE USER. A única diferença entre os dois é que o CREATE ROLE já implementa a opção **LOGIN** no momento da criação do usuário, além de possuir mais recursos que o CREATE USER.



Segue abaixo as formas possíveis de construir um usuário com as opções, características e permissões que ele irá possuir:

~~~~

CREATE ROLE name [ [ WITH ] option [ ... ] ]

where option can be:

      SUPERUSER | NOSUPERUSER
    | CREATEDB | NOCREATEDB
    | CREATEROLE | NOCREATEROLE
    | INHERIT | NOINHERIT
    | LOGIN | NOLOGIN
    | REPLICATION | NOREPLICATION
    | BYPASSRLS | NOBYPASSRLS
    | CONNECTION LIMIT connlimit
    | [ ENCRYPTED ] PASSWORD 'password' | PASSWORD NULL
    | VALID UNTIL 'timestamp'
    | IN ROLE role_name [, ...]
    | IN GROUP role_name [, ...]
    | ROLE role_name [, ...]
    | ADMIN role_name [, ...]
    | USER role_name [, ...]
    | SYSID uid

~~~~

<br>
<br>

Agora temos três exemplos de criação de usuários onde o usuário alysson tem acesso simples as coisas do banco de dados, o usuário admin que possui poder de criar banco de dados e criar novos usuários e o usuário marcos que é o mesmo tipo do usuário alysson, porém ele tem uma data limite para que o seu login funcione, que é até o primeiro mês do ano de 2022, no caso janeiro:

```sql
CREATE USER alysson  with
	LOGIN
	PASSWORD 'JIJI1J' ;
	
CREATE ROLE admin WITH 
	PASSWORD '2szr3gvdh'
	CREATEDB 
	CREATEROLE;


	CREATE ROLE marcos WITH LOGIN PASSWORD '2lbsyrpxgs' VALID UNTIL '2022-02-01';
 ```


## Removendo um usuário do banco de dados

<br>

Assim como fazemos a remoção de tabelas, views, etc..., usamos o DROP **'nome-do-usuario'** para efetuar a remoção dos usuários. Porém, temos que ter muito cuidado com isso, já que esse comando não remove as views, types, tables entre outros objetos no qual o usuário, caso queira fazer a remoção dos mesmos. Também há a situação de que os bancos de dados criados por esse usuário, ocorrerá um erro na remoção e uma mensagem será mostrada avisando sobre a situação. 

Para fazer a remoção do usuário que possuir banco de dados, devemos primeiro remover o banco de dados ou mudar o seu dono, aí sim podemos remover o usuário sem erros!

```sql 
DROP USER nome_do_usuário

```

<br>
<br>
<br>

## Aplicar alterações em um Usuário

<br>
<br>

Há situações onde será preciso aplicar alterações em um usuário, podendo ser suas permissões de criar bancos de dados, colocar uma nova senha para acesso para esta conta, alterar o nome do usuário, emtre outras coisas. Para que possamos fazer alterações, usamos a seguinte sintaxe: 


> ALTER USER nome_do_usuario [ [ WITH ] opção [ ... ] ]

<br>
<br>
Segue abaixo a lista de todas as características (opções) que podemos usar nessa QUERY:

~~~~
ALTER USER role_specification [ WITH ] option [ ... ]

where option can be:

      SUPERUSER | NOSUPERUSER
    | CREATEDB | NOCREATEDB
    | CREATEROLE | NOCREATEROLE
    | INHERIT | NOINHERIT
    | LOGIN | NOLOGIN
    | REPLICATION | NOREPLICATION
    | BYPASSRLS | NOBYPASSRLS
    | CONNECTION LIMIT connlimit
    | [ ENCRYPTED ] PASSWORD 'password' | PASSWORD NULL
    | VALID UNTIL 'timestamp'



ALTER USER { role_specification | ALL } [ IN DATABASE database_name ] SET configuration_parameter { TO | = } { value | DEFAULT }
ALTER USER { role_specification | ALL } [ IN DATABASE database_name ] SET configuration_parameter FROM CURRENT
ALTER USER { role_specification | ALL } [ IN DATABASE database_name ] RESET configuration_parameter
ALTER USER { role_specification | ALL } [ IN DATABASE database_name ] RESET ALL

where role_specification can be:

    role_name
  | CURRENT_USER
  | SESSION_USER
~~~~

- Exemplo de mudança de nome de um usuário

```sql
ALTER USER nome_do_usuario RENAME TO novo_nome
```

<br>
<br>

- Exemplo de retirar o privilégio de criar um novo banco de dados:


```sql
ALTER USER nome_do_usuario WITH NOCREATEDB

-- exemplo com o usuario Alysson
ALTER USER alysson WITH NOCREATEDB;
```

<br>
<br>
<br>

## Grupos de Usuários no PostgreSQL

<br>
<br>

Como no Unix, os grupos são uma forma de agrupar de forma lógica os usuários para facilitar o gerenciamento de privilégios. Esses privilégios podem ser concedidos ou até revogados de um grupo como um todo. Para criar um grupo, nós usamos o seguinte comando CREATE GROUP com o SQL, com a seguinte sintaxe de exemplo:

```sql
CREATE GROUP nome_do_grupo;
```

<br>

Para fazer adição de usuários em um determinado grupo utilizamos o seguinte código SQL:


~~~~
ALTER GROUP nome_do_grupo ADD USER uname1, ... ;
~~~~

<br>
Para remover um ou mais usuários de um grupo utilizamos o seguinte código SQL:

~~~~
ALTER GROUP name DROP USER uname1, ... ;
~~~~

<br>
Para remover/deletar um grupo usamos o seguinte QUERY:

```sql
DROP GROUP nome_do_grupo
```

* **OBS: Não é possível remover/deletar um grupo caso ele possua usuários. Será preciso remover todos os usuários para fazer isso!**

<br>
<br>
<br>
<br>


## Criando roles no PostgreSQL

<br>

O CREATE ROLE adiciona um novo para os agrupamentos  nos bancos de dados do PostgreSQL. Ele é uma entidade no qual pode possuir os objetos existentes no banco de dados e possuir os todos os privilégios do banco de dados. Devido a um amplo leque de formas de sua construção, ele pode ser considerado como um grupo, usuário, ou até mesmo os dois ao mesmo tempo, de acordo como o Role foi construído e utilizado. 

<br>

> O ROLE pode ser chamado de função ou até mesmo de papel.

<br>

Assim como foi dito no começo do texto, o CREATE ROLE se torna um substituto de CREATE USER e CREATE GROUP, já que o CREATE ROLE possui mais recursos que os dois.

Segue abaixo a listagem de todos os comandos que podemos utilizar com o CREATE ROLE para criar um script para o mesmo:

<br>
<br>


- ### name: o nome da nova ROLE.


<br>
<br>

- ### SUPERUSER | NOSUPERUSER:

  - Essas cláusulas determinam se a nova ROLE é um “ superusuário ” , que pode ignorar todas as restrições de acesso no banco de dados. O status de superusuário é perigoso e deve ser usado apenas quando realmente necessário. Você mesmo deve ser um superusuário para criar um novo superusuário. Se não for especificado, NOSUPERUSERé o padrão.

<br>
<br>

- ### CREATEDB | NOCREATEDB
  - Essas cláusulas definem a capacidade de uma ROLE de criar bancos de dados. Se CREATEDB for especificado, a ROLE que está sendo definida terá permissão para criar novos bancos de dados. A especificação NOCREATEDB negará a uma ROLE a capacidade de criar bancos de dados. Se não for especificado, NOCREATEDB é o padrão.

<br>
<br>

- ### CREATEROLE | NOCREATEROLE
  - Essas cláusulas determinam se uma ROLE terá permissão para criar novas funções (ou seja, executar CREATE ROLE). Uma ROLE com CREATEROLEprivilégio também pode alterar e descartar outras funções. Se não for especificado, NOCREATEROLEé o padrão.

- ### INHERIT | NOINHERIT
  - Essas cláusulas determinam se uma ROLE “ herda ” os privilégios das funções das quais é membro. Uma ROLE com o INHERIT atributo pode usar automaticamente quaisquer privilégios de banco de dados que foram concedidos a todas as funções das quais é membro direta ou indiretamente. Sem INHERIT, a associação em outra função apenas concede a capacidade SET ROLE para essa outra função; os privilégios da outra ROLE só estão disponíveis depois de ter feito isso. Se não for especificado, INHERITé o padrão.


<br>
<br>

- ### LOGIN | NOLOGIN
  - Essas cláusulas determinam se uma ROLE tem permissão para efetuar login; ou seja, se a ROLE pode ser fornecida como o nome de autorização da sessão inicial durante a conexão do cliente. Uma ROLE com o LOGIN atributo pode ser considerada um usuário. Funções sem este atributo são úteis para gerenciar privilégios de banco de dados, mas não são usuários no sentido usual da palavra. Se não for especificado, NOLOGIN é o padrão, exceto quando CREATE ROLE é chamado por meio de sua grafia alternativa CREATE USER .


<br>
<br>

- ### REPLICATION | NOREPLICATION
  - Essas cláusulas determinam se uma ROLE é uma ROLE de replicação. Uma ROLE deve ter este atributo (ou ser um superusuário) para poder se conectar ao servidor no modo de replicação (replicação física ou lógica) e para poder criar ou descartar slots de replicação. Uma ROLE com o REPLICATION atributo é uma ROLE altamente privilegiada e só deve ser usada em funções realmente usadas para replicação. Se não for especificado, NOREPLICATION é o padrão. Você deve ser um superusuário para criar uma nova ROLE com o REPLICATION atributo.

<br>
<br>

- ### BYPASSRLS | NOBYPASSRLS
  - Essas cláusulas determinam se uma ROLE ignora todas as políticas de segurança em nível de linha (RLS). NOBYPASSRLS é o padrão. Você deve ser um superusuário para criar uma nova função com o BYPASSRLS atributo.


<br>
<br>

Observe que o pg_dump será definido row_securitycomo OFFpadrão, para garantir que todo o conteúdo de uma tabela seja despejado. Se o usuário executando o pg_dump não tiver as permissões apropriadas, um erro será retornado. No entanto, os superusuários e o proprietário da tabela que está sendo despejada sempre ignoram o RLS.

<br>
<br>

- ### CONNECTION LIMIT connlimit
  - Se a ROLE pode efetuar login, isso especifica quantas conexões simultâneas a ROLE pode fazer. -1 (o padrão) significa sem limite. Observe que apenas as conexões normais são contadas para esse limite. Nem as transações preparadas nem as conexões de trabalho em segundo plano são contadas para esse limite.


<br>
<br>

- ### [ ENCRYPTED] PASSWORD' password' | PASSWORD NULL
  - Define a senha da ROLE. (Uma senha só é útil para funções com o LOGINatributo, mas você pode definir uma para funções sem ele.) Se você não planeja usar autenticação de senha, pode omitir esta opção. Se nenhuma senha for especificada, a senha será definida como nula e a autenticação de senha sempre falhará para esse usuário. Uma senha nula pode, opcionalmente, ser escrita explicitamente como PASSWORD NULL.

<br>
<br>

**OBS:**
**Especificar uma string vazia também definirá a senha como nula, mas esse não era o caso antes do PostgreSQL versão 10. Em versões anteriores, uma string vazia poderia ser usada, ou não, dependendo do método de autenticação e da versão exata, e a libpq o faria recusar-se a usá-lo em qualquer caso. Para evitar a ambiguidade, deve-se evitar a especificação de uma string vazia.**

<br>
<br>

A senha é sempre armazenada criptografada nos catálogos do sistema. A ENCRYPTED palavra-chave não tem efeito, mas é aceita para compatibilidade com versões anteriores. O método de criptografia é determinado pelo parâmetro de configuração password_encryption . Se a string de senha apresentada já estiver no formato criptografado por MD5 ou criptografado por SCRAM, ela será armazenada no estado em que se encontra password_encryption(uma vez que o sistema não pode descriptografar a string de senha criptografada especificada, para criptografá-la em um formato diferente). Isso permite o recarregamento de senhas criptografadas durante o despejo / restauração.

<br>
<br>

- ### VALID UNTIL' timestamp'
  - A VALID UNTIL cláusula define uma data e hora após as quais a senha da ROLE não é mais válida. Se esta cláusula for omitida, a senha será válida para sempre.


<br>
<br>

- ### IN ROLE role_name
  - A IN ROLE cláusula lista uma ou mais funções existentes às quais a nova ROLE será adicionada imediatamente como um novo membro. (Observe que não há opção para adicionar a nova ROLE como administrador; use um GRANTcomando separado para fazer isso.)


<br>
<br>

- ### IN GROUP role_name | IN GROUP
  - é uma grafia obsoleta de IN ROLE.


<br>
<br>

- ### ROLE role_name
A ROLE cláusula lista uma ou mais funções existentes que são adicionadas automaticamente como membros da nova ROLE. (Isso, na verdade, torna a nova ROLE um " grupo " .)


<br>
<br>

- ### ADMIN role_name
  - A ADMIN cláusula é semelhante ROLE, mas as funções nomeadas são adicionadas à nova função WITH ADMIN OPTION, dando-lhes o direito de conceder a participação nessa função a outras pessoas.


<br>
<br>

- ### USER role_name
  - A USERcláusula é uma grafia obsoleta da ROLEcláusula.


<br>
<br>

- ### SYSID uid
  - A SYSIDcláusula é ignorada, mas é aceita para compatibilidade com versões anteriores.

<br>
<br>
<br>
<br>
<br>



**OBS: Devemos ter cuidado em relação aos privilégios do CREATEROLE. Não existe o conceito de herança para os privilégios do papel com CREATEROLE. Isso quer dizer que que o papel mesmo que não possua um determinado privilégio, mas tenha permissão para criar outros papéis, ele poderá facilmente criar um novo papel com privilégios diferentes do próprio papel (exceto criar papéis com privilégio de super-usuário).**

<br>
<br>

Exemplo de create ROLE:

```sql
CREATE ROLE admin21 with 
SUPERUSER
CREATEDB
CREATEROLE
PASSWORD 'sfj21nm2a';
```

<br>
<br>
<br>

## Remover um role

<br>

```sql 
DROP ROLE admin21
```

<br>
<br>
<br>

```sql
ALTER ROLE admin with 
NOSUPERUSER
NOCREATEDB;
```

Em breve a parte 2:

<br>
<br>

FONTE:

- [Documentação do PostgreSQL](https://www.postgresql.org/docs)
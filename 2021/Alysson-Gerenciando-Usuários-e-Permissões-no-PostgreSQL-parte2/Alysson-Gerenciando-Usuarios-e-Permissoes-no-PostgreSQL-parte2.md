## Gerenciamento de Usuários e Permissões no PostgreSQL - PARTE 2 


<br>
<br>
<br>
<br>

Antes de começarmos o texto, se você não leu ou assitiu o vídeo da primeira parte sobre gerenciamento de usuários, eu recomendo que você leia ou assista. Os links estarão aqui abaixo:

- [Vídeo Gerenciamento de Usuários e Permissões no PostgreSQL - PARTE 1](https://link)
- [Texto Gerenciamento de Usuários e Permissões no PostgreSQL - PARTE 1](https://link)



<br>
<br>
<br>

#


<br>

Na parte 1 deste texto, vimos o básico da construção dos Usuários, grupos (GROUP), papéis/funções (ROLE). Neste texto, vamos começar construir um Banco de dados fazendo o seu gerenciamento de usuários.


<br>
<br>
<br>

O projeto do BD que vamos criar é de uma Universidade, é uma construção básica, porém o suficiente para essa situação. Segue a baixa o Modelo Entidade Relacionamento: 

<br>
<br>

![Diagram](/Diagrama1.png)




<br>
<br>
<br>

Segue o código em SQL para criar o banco de dados:

<br>

```sql




CREATE TABLE IF NOT EXISTS CURSO(
    numcurso serial,
    nome varchar(50),
    totalcreditos INT,
    CONSTRAINT curso_pkey1 PRIMARY KEY (numcurso)
);

CREATE TABLE IF NOT EXISTS Aluno (
    numaluno serial,
    nome VARCHAR(50),
    endereco VARCHAR(100),
    cidade VARCHAR(60),
    telefone VARCHAR(15),
    num_curso INT,
	CONSTRAINT aluno_pkey1 PRIMARY KEY (numaluno),
	CONSTRAINT aluno_fkey1 FOREIGN KEY (num_curso)
	REFERENCES curso(numcurso)
);



CREATE TABLE IF NOT EXISTS professor(
    numprof serial,
    nome VARCHAR(100),
    areapesquisa VARCHAR(100),
    CONSTRAINT professor_pkey1 PRIMARY KEY (numprof)
);

CREATE TABLE IF NOT EXISTS disciplinas(
    numdisc serial,
    nome VARCHAR(100),
    quantcreditos INTEGER,
    CONSTRAINT disciplinas_pkey1 PRIMARY KEY (numdisc)
);



CREATE TABLE IF NOT EXISTS contem(
	num_curso int,
    num_disc int,
    CONSTRAINT contem_fkey1 FOREIGN KEY (num_curso)
    REFERENCES CURSO(numcurso),
    CONSTRAINT contem_fkey2 FOREIGN KEY (num_disc)
    REFERENCES DISCIPLINAS(numdisc)
);


drop table aula

select * from aula;
CREATE TABLE IF NOT EXISTS aula(
    num_aluno INT,
    num_prof INT,
    num_disc INT,
    semestre varchar(10),
    nota real,
    
    CONSTRAINT aula_fkey1 FOREIGN KEY (num_aluno)
    REFERENCES aluno(numaluno),
    
    CONSTRAINT aula_fkey2 FOREIGN KEY (num_disc)
    REFERENCES DISCIPLINAS(numdisc),
    
    CONSTRAINT aula_fkey3 FOREIGN KEY (num_prof)
    REFERENCES PROFESSOR(numprof)

);
```


<br>
<br>

Vamos criar 2 funçõos para esse banco, chamado de adicionarAula e adicionarDisciplina_Curso.





<br>
<br>
<br>

Função adicionarAula
```SQL
CREATE OR REPLACE FUNCTION adicionarAula(num_aluno int, num_disciplina int, num_professor int, semestre_at varchar(10))
RETURNS void AS $$
begin
	perform * from aluno where numaluno = num_aluno;
	if found then
		perform * from disciplina where num_disciplina = numdisc;
		if found then
			perform * from professor where num_professor = numprof;
		if found then
			insert into aula (numaluno,numprof,numdisc,semestre)values (num_aluno, num_professor, num_disciplina, semestre_at);
RAISE NOTICE 'Cadastro do aluno na aula foi feita!' ;
else
RAISE EXCEPTION 'Não foi possível encontrar o aluno!';
end if;
else
RAISE EXCEPTION 'Não foi possível encontrar a disciplina!!';
end if;
else 
RAISE EXCEPTION 'Não foi possível encontrar o Professor!';
end if;
end;
$$
LANGUAGE plpgsql SECURITY DEFINER;
```


<br>
<br>
<br>

Função adicionarDisciplina_Curso

```sql
CREATE OR REPLACE FUNCTION adicionarDisciplina_Curso(numDoCurso int, numDaDisciplina int)
RETURNS void AS $$
begin
	perform * from curso where numDoCurso = numcurso;
	if found then
		perform * from disciplina where numDaDisciplina = numdisc;
		if found then
			insert into contem (num_curso,num_disc)
			values (numDoCurso, numDaDisciplina);
RAISE NOTICE 'Cadastro da Disciplina no Curso foi feita!' ;
else
RAISE EXCEPTION 'O Curso nao consta no registro!';
end if;
else
RAISE EXCEPTION 'Não foi possível fazer o cadastro da Disciplina no Curso';
end if;
end;
$$
LANGUAGE plpgsql SECURITY DEFINER;
```

<br>
<br>
<br>
<br>

**OBS: O SECURITY DEFINER usada na criação das três funções, serve para permitir que todos os usuários acessem essas funções com a mesma permissão de quem as criou.**

Agora, vamos criar as roles desse banco de dados:

```SQL
CREATE ROLE assistente_admin
CREATE ROLE gerente_admin
CREATE ROLE estagiario
```

<br>
<br>
<br>

Antes de dar a permissão de execução para os grupos assistente_admin, gerente_admin e estagiário, deve-se revogar o direito de qualquer usuário do banco executar tais funções.

<br>
<br>


- O assistente_admin pode fazer o cadastro dos alunos nas aulas.
- O gerente_admin tem acesso total a tudo dentro do banco de dados.
- O estagiario só irá possuir acesso a algumas coisas dentro do banco de dados, como algumas com dados limitados

<br>
<br>

Antes de darmos permissões de execução para os Role (papéis) para assistente_admin, gerente_admin e estagiario, precisamos remover o direito de qualquer usuário do banco de dados para impedir que os mesmos possam executar essas funções que foram criadas, no caso a **adicionarDisciplina_Curso** e **adicionarAula**.

Para fazermos isso, usaremos o comando REVOKE para remover essas permições. O código abaixo mostra um exemplo de como isso pode ser feito:

<br>

```sql 

REVOKE ALL ON FUNCTION adicionarAula(int, int, int, varchar(10)) FROM PUBLIC

REVOKE ALL ON FUNCTION adicionarDisciplina_Curso(int, int) FROM PUBLIC

```


<br>
<br>

Após ter sido feito a execução do script acima, agora podemos dar as permições para cada grupo que foi criado, no caso são **assistente_admin**, **gerente_admin** e **estagiario**. O grupo assistente_admin pode usar a função adicionarAula e fazer consultas nas em todas as tabelas do banco de dados. O grupo gerente_admin pode usar as duas funções, modificar e consultar todas as tabelas do banco de dados. Agora o estagiário, só poderá fazer consultas nas tabelas de aula, curso e disciplinas.

```sql

-- dando permissão para consultar e inserir dados de todas as tabelas ao gerente_admin
GRANT SELECT, INSERT ON curso, aluno, contem, aula, disciplinas, professor TO gerente_admin WITH GRANT OPTION;

-- dando permissão para consultar as tabelas aula, curso e disciplinas ao estagiario
GRANT SELECT ON aula, curso, disciplinas TO estagiario WITH GRANT OPTION;

-- dando permissão para consultar todas as tabelas ao assistente_admin
GRANT SELECT ON curso, aluno, contem, aula, disciplinas, professor TO assistente_admin WITH GRANT OPTION;

-- dando permissão para o assistente_admin use a função adicionarAula
GRANT EXECUTE ON FUNCTION adicionarAula(int, int, int, varchar(10)) TO assistente_admin;


-- dando permissão para o gerente_admin use a função adicionarAula e adicionarDisciplina_Curso
GRANT EXECUTE ON FUNCTION adicionarAula(int, int, int, varchar(10)), adicionarDisciplina_Curso(int, int) TO gerente_admin;

```

<br>
<br>
<br>



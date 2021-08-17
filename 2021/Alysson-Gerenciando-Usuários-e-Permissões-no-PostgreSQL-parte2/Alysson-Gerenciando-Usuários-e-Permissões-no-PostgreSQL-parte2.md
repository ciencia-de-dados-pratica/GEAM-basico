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


O assistente_admin 
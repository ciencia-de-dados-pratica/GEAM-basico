# Bancos de Dados Relacionais - Modelo Lógico
Neste tutorial iremos falar sobre diagramas de entidade/relacionamento.[Aqui](https://www.youtube.com/watch?v=FN4wcCk5rWM) é possível assistir a este tutorial em vídeo no nosso canal do Youtube.

Um diagrama entidade relacionamento (ER) é um tipo de fluxograma que ilustra como “entidades”, por exemplo, pessoas, objetos ou conceitos, se relacionam entre si dentro de um sistema. Diagramas ER são mais utilizados para projetar ou depurar bancos de dados relacionais nas áreas de engenharia de software, sistemas de informações empresariais, educação e pesquisa.

## Etapas da construção de um Banco de Dados


![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/Modelo.png)

O primeiro passo para criar um banco de dados é transformar a ideia do cliente em um **Modelo Conceitual**, depois de criado o modelo conceitual ele é transformado em um **Modelo Lógico** e por fim é implementado o **Modelo Físico** no SGBD. 

Neste tutorial iremos ver o **Modelo Lógico**.

## Modelo Lógico

O modelo lógico já leva em conta algumas limitações e implementa recursos como adequação de padrão e nomenclatura, define as chaves primárias e estrangeiras, normalização, integridade referencial, entre outras. Para o modelo lógico deve ser criado levando em conta os exemplos de modelagem de dados criados no modelo conceitual.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/Completo.png)

No modelo lógico as cardinalidades são representadas de forma diferente.

### Cardinalidade 1:1

Na cardinalidade 1:1, não é gerada nenhuma tabela adicional, porém é adicionado um novo campo em uma das tabelas.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/S-1-1.png)

A imagem acima representa a relação no modelo conceitual entre **Aluno** e **Morada**.

A imagem a seguir representa a relação acima no **Modelo Lógico**.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/1-1.png)

Quando temos uma cardinalidade 1:1 no **Modelo Lógico**, uma das tabelas recebe o atributo da outra. Observe que a entidade **Morada** recebeu o campo **Número_Aluno**, referente ao campo **Número** da entidade **Aluno**.

### Cardinalidade 1:N

Na cardinalidade 1:N, assim como na cardinalidade 1:1, uma das entidades recebe o atributo da outra, nesse caso a que tiver a cardinalidade N.

Observe o modelo conceitual a segir.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/S-1-N.png)

A imagem a seguir representa o modelo lógico das entidades acima.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/1-N.png)

Observe que a entidade **Telefone** recebeu o campo **NúmeroAluno**, referente a **Número** da entidade **Aluno**.

### Cardinalidade N:N

A cardinalidade N:N no modelo lógico, gera uma nova tabela que representa a relação.

Observe o modelo conceitual abaixo que representa a cardinalidade N:N entre Professor e Disciplina.    

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/S-N-N.png)

Na imagem abaixo observe que a partir da cardinalidade N:N entre Aluno e Disciplina, surgiu a entidade **Estuda** que herda as chaves primarias de Aluno e Disciplina.

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno-Modelo_Logico/Imagens/N-N.png)

## Considerações finais

O Modelo Lógico é uma ótima técnica para a auxiliar na criação de um Banco de Dados, pois nele é possível modelar o Banco de Dados evitando problemas com a estrutura do Banco durante a implementação do modelo físico.


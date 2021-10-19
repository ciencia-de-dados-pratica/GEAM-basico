# Cross-validation no Orange

Quando vamos fazer uma classificação é comum ficarmos em dúvida,  principalmente iniciantes, sobre qual método utilizar, qual terá a maior acurácia? Para responder é preciso realizar um teste.

Para realizar tal teste, utilizarei um *dataset* famoso, o "Iris", ele cataloga flores do gênero íris.  Dos métodos de classificação utilizarei os *widgets* *Logistic Regression*, *Random Forest Classification* e *SVM*.
![01](https://i.imgur.com/1S6LkKe.png)
Para começar ligaremos tanto o *widget File*, com o *dataset* "Iris", quanto os três métodos ao *widget Test & Score*, para podermos medir a precisão de classificação de cada método. Feito isso, agora podemos ver a pontuação de cada método.
![02](https://i.imgur.com/NwZD0FA.png)
Podemos ver na imagem acima que o *Logistic Regression* obteve a maior pontuação, logo, esperasse que ele erre menos que os demais.
Agora podemos ligar os *widgets Test & Score* e *Confusion Matrix*. O *Confusion Matrix* mostrará uma matriz de acerto e erros, onde sua diagonal principal é os acertos e as diagonais secundarias são os erros. Abaixo podemos ver as matrizes dos três métodos.
![03](https://i.imgur.com/pmIlFTZ.png)
![04](https://i.imgur.com/r7SpkTk.png)
![05](https://i.imgur.com/zqjOuVs.png)
Como era esperado, o que obteve a maior taxa de acertos foi o *Logistic Regression*, logo seria o mais indicado dos três a ser usado em seu workflow.

## Referência
- <a href="https://orangedatamining.com">Orange Data Mining - Data Mining</a>



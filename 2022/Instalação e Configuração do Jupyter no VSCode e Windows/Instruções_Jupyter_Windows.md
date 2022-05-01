# Instalação e Configuração do Jupyter no VSCode e Windows

## Fazendo o download do Pacote Anaconda:

Você pode encontrar o pacote do anaconda clicando [aqui](https://www.anaconda.com/products/distribution).

### O site que deve aparecer é esse: 
![site anaconda](/Imagens/AnacondaSite.jpg)

Como esse tutorial é sobre o Windows, então baixaremos a versão para windows.

## Instalação do Pacote Anaconda:

Após o download, abra o instalador com permissão de administrador.

A primeira tela da instalação:
![Tela01](/Imagens/Tela01.jpg)

* Seguimos com a instalação apertando **Next >**

A segunda tela da instalação:
![Tela02](/Imagens/Tela02.jpg)

* Seguimos com a instalação apertando em **I Agree**

A Terceira tela da instalação:
![Tela03](/Imagens/Tela03-JustMe.jpg)

* Caso queira instalar só para o seu usuário selecione a opção **Just Me**, caso queira instalar para todos os usuários selecione a opção **All Users**.

Tela com a selação **Just Me**:
![Tela04](/Imagens/Tela04-JustMe.jpg)

* Nesa tela pode ser que ocorra um erro na instalação:

    1. Caso seu usuário tenha nome com espaço, caracteres especiais, pode ser que ocorra erro na instalação. Nesse caso o recomentado é desistalar tudo e instalar novamente com a opção **All Users**.

* Para prosseguir com a instalação basta apertar em **Next >**

Tela com a selação **All Users**:
![Tela04](/Imagens/Tela03-AllUser.jpg)

* Após escolher a opção All Users, o anaconda irá fazer uma nova solicitação e abrir uma nova tela.
* Com isso basta apertar em **Next >**

Tela de instalação:
![Tela](/Imagens/TeladaInstalacao.jpg)

* A instalação pode demorar alguns minutinhos.

Tela de instalação:
![Tela](/Imagens/TeladaInstalacsoConcluido.jpg)

* Após a conclusão da instalação você pecisa apertar em  **Next >** para concluir a instalação.

* Na tela seguinta aperte em **Finish** e pronto. Temos a instalação do Pacote Anaconda concluída.

## Abrindo o Jupyter Notebook:

Para abrir o Jupyter Notebook besta apertar a tecla Windows do seu teclado e digitar "Jupyter".

![Tela](/Imagens/ConferindoInstalacao.jpg)

* Como pode notar na imagem acima, o Jupyter Notebook foi instalado com o Pacote Anaconda.
* O **Anaconda Prompt** tem que está aparecendo, caso no seu não esteja algo deu errado na instalação, nesse caso, desinstale tudo e instale novamente.

Abrindo o Jupyter Notebook:
![Tela](/Imagens/TerminalJupyter.jpg)

* O Jupyter Notebook irá abrir juntamente com um terminal, você não pode fechar o terminal ou o Jupyter Notebook será fechado
* O Jupyter Notebook será aberto em uma janela do seu navegador padrão. Então se o Mozilla está como navegador padrão, o Jupyter será aberto nele, no caso da Imagem acima o Jupyter está sendo aberto no Google Chrome.

A tela inicial do Jupyter Notebook:
![Tela](/Imagens/TelaInicialJupyter.jpg)

* Como se pode notar, o jupyter lista as suas pastas do seu computador.

Criando uma nova pasta e renomeandoa:
![Tela](/Imagens/TelaComoCriarPasta.jpg)

* Vá na opção **New**, selecione **Folder**

Pasta sendo criada:
![Tela](/Imagens/TelaPastaCriada.jpg)

* Para renomear a pasta que foi criada basta selecionar ela e apertar no botão **Rename**

* Após renomear a pasta para acessa-la basta que aperte uma vez nela.

Entrando na pasta criada:
![Tela](/Imagens/TelaDaPastaCriada.jpg)

Criando um Aquivo:
![Tela](/Imagens/TelaCraindoArquivo.jpg)

* Aperte na opção **New**
* Selecione **Python 3** e o arquivo será criado

![Tela](/Imagens/TelaArquivoCriado.jpg)

* No arquivo criado é possivel renomea-lo indo onde está escrito **Untitled**.
* Podemos ter a opção de fazer uma célula de python ou markdown.

Exemplos:
![Tela](/Imagens/TesteDasCelulas.jpg)

* A primeira célula é de texto a segunda foi um simples código em python, para executar as célular basta apertar em **Run**

Com isso finalizamos a parte de instalação do Jupyter Notebook.

## Usando o Jupyter Notebook no VS Code:

Para usaro o Jupyter Notebook no VS Code precisamos fazer a instalação de duas extenções (Python e ipynb) no próprio VS Code.

Extensão Python:
![Tela](/Imagens/JupyterVSCODE.jpg)

Extensão IPYNB:
![Tela](/Imagens/JupyterVSCODE-Jupyter.jpg)

## Criando o primeiro arquivo e fazendo o primeiro teste:

![Tela](/Imagens/CriandoPrimeiroArquivoIPYNBVSCode.jpg)

* Após abrir sua pasta de preferência em "Arquivos/abrir pasta" crie um novo aquivo com o nome de sua preferencia usando ".ipynb" ao final. Como no exemplo da imagem acima "teste.ipynb".

Tela após a criação do .ipynb:
![Tela](/Imagens/CriandoCelulasVSCode.jpg)

* Assim como no programa do Jupyter Notebook, no VS Code você também pode ter células de código e markdown.

* No VS Code você pode por para compilar todas as células criadas ou uma célula de sua preferência.

![Tela](/Imagens/ExecutandoVscode01.jpg)

**Com isso finalizamos a instalação do Jupyter Notebook no Windows e VS Code.**
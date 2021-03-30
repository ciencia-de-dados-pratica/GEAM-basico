# Introdução a QGIS

Neste tutorial, falamos sobre o QGIS, um software multiplataforma de sistema de informação geográfica (SIG) que permite a visualização, edição e análise de dados georreferenciados. [Aqui](https://youtu.be/UOirxLhvtXA) é possível assistir a esse tutorial em vídeo no nosso canal do Youtube.

### Introdução

Similar a outros softwares GIS, o QGIS permite ao usuário criar mapas com várias camadas usando diferentes projeções de mapa. Mapas podem ser montados em diferentes formatos e para diferentes usos. QGIS permite compor mapas a partir de camadas raster e/ou vetoriais. Típico deste tipo de software, os dados podem ser armazenados como pontos, linhas, ou polígonos. Diferentes tipos de imagens raster são suportadas e o software tem capacidade de georreferenciar imagens. 

### Funções Avançadas

QGIS provê integração com outros pacotes GIS free/open-source, incluindo PostGIS, GRASS e MapServer para dar ao usuário a capacidade de estender suas funcionalidades. Plugins, escritos em Python ou C++, estendem as capacidades do QGIS. Existem plugins para geocodificar usando a API do Google Geocoding, para realizar geoprocessamento (fTools) similar às ferramentas padrão encontradas no ArcGIS, e para realizar a interface com bases de dados PostgreSQL/PostGIS, SpatiaLite e MySQL. 

### Instalação

É possível instalar o QGIS no Linux utilizando o comando:

**sudo apt-get install qgis**

### Interface

Após a instalação, você pode abrí-lo e terá uma interface semelhante a essa:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20QGIS/Imagens/Imagem01.png)

### Conexão com o PostGIS

Para fazer a conexão com o Banco de Dados, você deve acessar **PostGIS** -> **Novo**. Após isso, irá aparecer uma janela semelhante a essa:

![](https://github.com/ciencia-de-dados-pratica/GEAM-basico/blob/master/2020/Bruno%20-%20QGIS/Imagens/Imagem02.png)

Feito isso, basta inserir os dados pedidos e pronto, é só trabalhar com os dados!


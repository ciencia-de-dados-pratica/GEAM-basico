## Introdução

<br>
<br>

Neste texto irei mostrar como fazer uma conexão com banco de dados PostgreSQL e MySQL usando a linguagem de programação JAVA.

#
<br>
<br>
<br>

Vamos usar o Drive JDBC tanto para PostgreSQL quanto para MySQL. Essa biblioteca já vem incluida quando instalamos o NetBeans IDE 8.2, no qual vamos usar para mostrar as demonstrações em código e fazer a conexão com os Banco de Dados.

<br>
<br>

Primeiramente vamos importar o Diver/Biblioteca JDBC para o MySQL e PostgreSQL para que seja possível a conexão com o BD que você eseteja trabalhando. Para fazer isso, basta ir em **bibliotecas** e clicar nele com o botão direito do mouse e vai aparecer **"Adicionar Biblioteca..."** assim como mostra na imagem abaixo:

![alt](imagens/adicionarDriver.png)

Em seguida vai aparecer essa lista com os Divers/Bibliotecas disponíveis para adicionar ao seu projeto. Escolha aquela que se encaixe com BD que está a usar. Como vou mostrar a conexão nos dois, então irei adicionar os dois.

![alt](imagens/adicionarDriver2.png)

<br>
<br>

Após adicionar o Driver JDBC, vamos criar um pacote para colocar-mos a classe responsável pela conexão com o BD. Eu vou nomear com **"conexao"**, você pode nomear com o nome que queira, porém recomendo colocar um nome que remeta a conexão. O nome da classe que irei usar é o **"connection_DB"**. 


<br>
<br>

Existem diversas formas de você fazer uma conexão com o BD com JAVA e o que irei mostrar é uma das formas de fazer isso. Para fazer a conexão com PostgreSQL e MySql, será preciso nomear alguns atributos finais na classe **"connection_DB"** que guardarão as informações necessárias para a conexão. São elas:
```java
/**
 *
 * @author Alysson Araújo
 */
import java.sql.*;

public class conectar {

    // De acordo com qual BD vc esteja trabalhando, temos esses drivers devifindos para o MySql e PostgreSQL.
    

    private static Connection conexao_MySql = null;
    private static Connection conexao_PostgreSQL = null;


    // local onde o banco de dados está presente. Por padrão, colocarei localhost, mas você
    // pode mudar o local de acordo com sua necessidade.
    private static String localBD = "localhost";

    // Aqui são os LINKS responsáveis pelo local onde o BD estar. é modificável de acordo com suas necessidades
    private static String LINK1 = "jdbc:mysql://"+localBD+":3306/nome do seu banco";
    private static String LINK2 = "jdbc:postgresql://localhost:5432//nome do seu banco";

    // Nome do usuário e senha com permissão de acesso ao BD. Você coloque de acordo com o
    // usuário e senha pertencente ao Banco de Dados
    private static final String usuario = "";
    private static final String senha = "";




    // Método para fazer a conexão com um banco de dados MySql
    public static Connection connectionMySql(){

        try {

            conexao_MySql = DriverManager.getConnection(LINK1, usuario, senha);
            System.out.println("conexão feita!");


        }
        catch (SQLException e){
            throw new RuntimeException("Ocorreu um problema na conexão no BD.", e);
        }

        return conexao_MySql;
    }

    // Método para fazer a conexão com um banco de dados PostgreSQL.
    public static Connection connectionPostgreSQL(){

        try {
            conexao_PostgreSQL = DriverManager.getConnection(LINK2, usuario, senha);
            System.out.println("conexão feita!");
        }
        catch (SQLException e){
            throw new RuntimeException("Ocorreu um problema no BD", e);
        }
        return conexao_PostgreSQL;
    }


    //O closeConnectionMySql fecha a conexão com o banco de dados MySql
    // con.close() é um método de Connection onde fechamos a conexão da aplicação com o banco de dados.
    public static void closeConnectionMySql(){
        try {
            if (conexao_MySql != null) {
                conexao_MySql.close();
                System.out.println("Deu certo fechar");
            }
        } catch (SQLException e) {
            throw new RuntimeException("Ocorreu um problema para encerrar a conexão com o banco de dados.", e);
        }
    }

    //O closeConnectionPostgreSQL fecha a conexão com o banco de dados PostgreSQL
    // con.close() é um método de Connection onde fechamos a conexão da aplicação com o banco de dados.
    public static void closeConnectionPostgreSQL(){
        try {
            if (conexao_PostgreSQL != null) {
                conexao_PostgreSQL.close();
                System.out.println("Deu certo fechar");
            }
        } catch (SQLException e) {
            throw new RuntimeException("Ocorreu um problema para encerrar a conexão com o banco de dados. ", e);
        }
    }
}
```

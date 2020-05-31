# BDIII
Dados teoricos para o terceiro modulo de banco de dados MySql 


## Functions
Geralmente é uma função criada pelo usuario que executa uma função e retorna um dado. 
O uso de functions podem ajudar desenvolvedores de BDAs a optimizar o desempenho de
multiplas consultas ou atualizações de dados , além de melhorar a produtividade de
quem desenvolve .

As funções são muito utilizadas para computar valores, promover reusabilidade e 
facilidade de manutenção e podem ser chamadas a partir de outros blocos PL/SQL 
ou até mesmo por instruções SQL. É muito comum utilizarmos funções em instruções 
SQL para efetuar conversões de dados, formatar datas, contar o total de linhas,etc.

Essas mesmas funções servem para  armazená-la no banco de dados e chamá-la quantas 
vezes quiser em seu programa. Funções definidas pelo usuário podem ser modificadas 
independentemente do código-fonte do programa,além que pode reduzir o trafico de rede.

### Tipos de Funções

- Escalar

    São funções que retornam um valor unico de resultado.
    
  > SUM, DATEADD, COALESCE
  
  > SELECT SUM(Quantity) AS TotalItemsOrdered FROM OrderDetails;
  
 Nesse exemplo é efetuado uma função de SOMA , onde soma todas as 'quantity' as 'Quantidades'
 em 'TotalItemsOrdered' na Tabela 'OrderDetails'
 
 [1](https://raw.githubusercontent.com/jvitorn/BDIII/master/screenshot/1.png)
  
    
- Funções com valor de tabela
O exemplo a seguir cria uma TVF (função com valor de tabela) embutida no banco de dados AdventureWorks2012. A função pega um parâmetro de entrada, um ID cliente (loja), e retorna as colunas ProductID, Namee a agregação das vendas do ano, até a data atual, como YTD Total para cada produto vendido para a loja.

>IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);

- Funções de Sistema

São funções que foram embutidas no comando select para o alguns tipos de dados em determinadas condições.

>   mysql> select now( );

Essa função vai retornar : 2020-05-31 19:51:08 que é a data atual 

> mysql> select dayname(‘2009-01-14’);

Essa função vai retornar : 'Thursday' que é o dia da semana 
                        


## Referencias 

[http://db4beginners.com/blog/voce-sabe-o-que-e-uma-function/]

[https://www.devmedia.com.br/stored-procedures-functions-e-packages-em-bancos-de-dados-oracle/25390]

[https://www.devmedia.com.br/artigo-sql-magazine-51-udfs-e-funcoes-escalares/8179]

[https://www.w3schools.com/sql/trymysql.asp?filename=trysql_func_mysql_sum]

[https://www.portaleducacao.com.br/conteudo/artigos/idiomas/funcao-data-e-hora-em-mysql/7408]

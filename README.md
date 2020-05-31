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
  
    
- Funções com valor de tabela
- Funções de Sistema


## Exemplo 




## Referencias 

[http://db4beginners.com/blog/voce-sabe-o-que-e-uma-function/]

[https://www.devmedia.com.br/stored-procedures-functions-e-packages-em-bancos-de-dados-oracle/25390]

[https://www.devmedia.com.br/artigo-sql-magazine-51-udfs-e-funcoes-escalares/8179]

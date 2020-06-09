# BDIII
Dados teoricos para o terceiro modulo de banco de dados MySql 

## Merge

Onde é informado as tabelas de destino para executar as operações de
Inclusão, exclusão e alteração de dados 

A Clausula MERGE funciona e é utilizada, quando existe uma situação na 
Qual será necessário fazer a sincronização de UPDATE e INSERT ao mesmo tempo
no MYSQL, ou seja, quando precisa fazer a atualização e inserção de linhas em uma
ou varias tabelas na base de dados.

De uma maneira mais crua e bruta seria um INNER JOIN mais poderoso talvez ...


## Sintaxe MERGE

- USING

    Informa as tabelas usadas nas comparações 

- MERGE 

    Informa a tabela de destino das operações (onde as operações de inclusão, exclusão e alteração serão realizadas)

- ON

    Condição que juntam as informações das tabelas (Mesma coisa do ON do INNER JOIN/JOIN)

- WHEN 
    Especifica o tipo de operação 
    exitem varias clausulas dentro do metodo WHEN 
    que seriam para verificar se as condições estão verdadeiras, ou para verificar se existem 
    registros nas tabelas

- OUTPUT
    utiliza de uma variavel global $ACTION para retornar um registro de cada linha de inclusao, alteração ou exclusão

### Conclusao Final

O Conceito MERGE é algo muito interessante pois , ele vai fazer uma serie de verificações ,para verificar a comparação de dados Igualitários , e essa é a principal vantagem , ter como atualizar ou inserir informações
de varias tabelas difentes em vez de criar varios selects ou updates para cada tabela.

### OBSERVAÇÃO 

Também existem um tipo de tablela em sql que é a tabela MERGE,que é um recurso que permite 
"QUEBRAR" ou "DIVIDIR" uma enorme tabela em varias partes da mesma, ou tambem unir duas tabelas 
em uma , bom pelo menos foi isso que consegui entender sobre o conteudo


## Referencias

[https://dev.mysql.com/doc/refman/8.0/en/merge-storage-engine.html]

[https://www.devmedia.com.br/trabalhando-com-os-varios-tipos-de-tabelas-do-mysql/1966]


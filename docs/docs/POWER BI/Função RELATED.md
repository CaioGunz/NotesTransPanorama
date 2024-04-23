# Para saber mais: a função RELATED

É usada em modelos de dados relacionais, como aqueles criados no Power BI e no Excel, para recuperar valores de uma tabela relaciona com base em uma relação estabelecida.

Em modelos relacionais, é comum termos várias tabelas interconectadas, representando diferentes entidades e suas associações. Essas tabelas são vinculadas por colunas comuns, tamém conhecidas como chaves estrangeiras e chaves primárias, que estabelecem as relações entre as entidades.

A função RELATED permite que você acesse informações de uma tabela relacionada a partir de uma tabela atual. Ela é frequentemente usada em colunas calculadas ou medidas, onde você deseja trazer informalções de outra tabela como base em uma relação.

A sintaxe básica da função RELATED é a seguinte:
```
RELATED(TabelaRelacionada[ColunaRelacionada])
```
Onde:
 - "TabelaRelacionada" é o nome da tabela da qual você deseja recuperar os valores.
 - "ColunaRelacionada" é o nome da culna na tabela relacionada que contém os valores que você deseja trazer.

 A função RELATED usa a relação estabelecida entre as tabelas para encontrar a correspondência correta dos valores. É importante lembrar que a relação deve ser definida no modelo de dados para que a função funcione corretamente.

 Exemplo:

 Vamos considerar um exemplo simples como duas tabelas relacionadas:
 "Clientes" e "Pedidos". A tabela "Pedidos" possui uma coluna chamada "ClienteID", que é uma chave estrangeira relacionada a coluna "ClienteID" na tabela "Clientes".

 Suponha que você queira criar uma medida que calcule o valor total dos pedidos para cada cliente. Nesse caso, você pode usar a função RELATED para obter o nome do cliente da tabela "Clientes" com base no "ClienteID" presente na tabela "Pedidos". Nesse contexto, a medida fica da seguinte maneira:
 ```
 ValorTotalPedidos = SUM(Pedidos[Valor])
 NomeCliente = RELATED(Clientes[Nome])
 ```

 A função RELATED é utilizada nesse cenário com o objetivo de buscar o nome do cliente associado ao "ClienteID" na tabela de pedidos, para que então seja possível visualizar o valor total de pedidos para cada cliente pelo seu respectivo nome.

 Em resumo, a função RELATED é uma ferramenta essencial para acessar informações de tabelas relacionadas em modelos de dados do Power BI e Excel. Co ela, você pode enriquecer as suas análises e fazer cálculos enquanto obtem informações contextuais a partir de relações entre tabelas.

Fonte: Alura


 
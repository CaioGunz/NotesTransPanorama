# PAra saber mais: funções que retornam tabelas (Values e Distinct)

Em DAX, as funções que retornam tabelas são ferramentas poderosas para manipulação de dados e análise em modelos de dados do Microsoft Power BI, Excel e outros aplicativos compatíveis com DAX. Duas dessas funções são "VALUES" e "DISTINCT". Elas desempenham um papel fundamental na criação de medidas e colunas calculadas em suas tabelas.

### 1 - Função Values:

A função VALUES é usada para retornar um tabela de valores únicos de uma coluna específica em um contexto de filtro. Ela é frequentemente utilizada para criar uma lista distinta de valores com base nas seleções ou filtros aplicados em outras colunas. A sintaxe básica da função VALUES é:
```
VALUES(tabela[coluna])
```

Onde "tabela" é a tabela que contém a coluna desejada, e "coluna" é o nome da coluna da qual se deseja extrair os valores únicos. O resultado é uma nova tabela contendo os valores únicos. O resultado é uma nova tabela contendo os valores únicos da coluna especificada.

Exemplo:

Suponha que temos uma tabela chamada "Vendas" com as colunas "Produtos" e "Valor". Se quisermos obter uma lista de produtos distintos, podemos criar uma medida usando a função VALUES:
```
Produtos Distintos = VALUES(Vendas[Produto])
```

### 2 - Função DISTINCT:

A função DISTINCT é semelhante à função VALUES, pois também retorna uma tabela de valores únicos de uma coluna específica. No entanto, a função DISTINCT pode ser usada sem a necessidade de especificar uma tabela, tornando-a mais flexível quando você precisa de uma lista de valores únicos sem se referir a uma tabela específica. A sintaxe básica da função DISTINCT é: 
```
DISTINCT(tabela[coluna])
```
Exemplo:

Usando o mesmo exemplo da tabela "Vendas", podemos obter a lista de produtos distintos sem referenciar explicitamente a tabela:
```
Produtos Distintos = DISTINCT(Vendas[Produto])
```
Ambas as funções são especialmente úteis em cenários de criação de relatórios e análises, quando você precisa gerar listas de valores exclusios para criar visualizações específicas ou para realizar cálculos em um contexto de filtro mais refinado. 

em resumo, as funções VALUES e DISTINCT em DAX são ferramentas valiosas para extrair valores únicos de colunas específicas em tabelas, pois permite uma manipulação de dados mais precisa e eficiente em suas análises e relatórios.

Fonte: Alura


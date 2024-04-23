# Para saber mais: as funções iteradoras

As funções iteradoras são uma categoria de funções poderosas em DAX (Data Analysis Expressions), utilizadas para realizar cálculos em cada linha de uma tabela e, em seguida, retornar os resultados em uma nova tabela ou um único valor agregado. Diferentemente das funções agregadoras, que fornecem um único resultado para toda a tabela, as funções iteradoras realizam operações em um nível de granularidade de linha.

Essas funções são muitos úteis para casos em que é necessário realizar cálculos complexos em cada linha e, em seguida, consolidar os resultados em uma nova tabela ou valor. Além disso, elas são frequentemente utilizadas em colunas calculadas, medidas e tpe mesmo em colunas de tabelas para criar lógicas mais avançadas.

As funções iteradoras mais comuns em DAX incluem:

1. SUMX: Calcula a soma de uma expressão em todas as linhas de uma tabela e retorna o resultado agregado.

2. AVERAGEX: Calcula a média de uma expressão em todas as linhas de uma tabela e retorna o resultado agregado.

3. COUNTAX: Conta o número de linhas em uma tabela que atendem a uma condição específica.

4. MINX e MAXX: Encontram o valor mínimo e máximo de uma expressão em todas as linhas de uma tabela, respectivamente.

5. FILTER: Filtra as linhas de uma tabela com base em uma condição e retorna a tabela filtrada.

6. ALLSELECTED: Retorna todas as linhas de uma tabela, ignorando quaisquer filtros aplicados nas visualizações.

Essas funções iteradoras são especialmente úteis em cenários de análise de dados, onde você precisa realizar cálculos em nível de linha ou filtrar dados dinamicamente com base em condições específicas. Elas permitem que você manipule dados em detalhe e crie cálculos mais sofisticados, trazendo flexibilidade e poder analíticos aos seus modelos de dados.

No entanto, é importante ter cuidado ao usar funções iteradoras, pois podem resultar em cálculos mais lentos e recursos cumputacionais mais intensivos, especialmente em grandes volumes de dados. Portanto, é fundamental otimizar o uso dessas funções e entender como elas afetam o desempenho do seu modelo de dados. É recomendável que você utilize as funções iteradoras apenas quando necessário, e sempre busque alternativas mais eficientes, como medidas agregadas, quando possível.

Fonte: Alura


# Para saber mais: Categoria de funções de modificação de filtros em DAX

As funções de modificação de filtros em DAX fazem parte de uma categoria especial de funções que permitem manipular os filtros apolicados em uma tabela ou coluna em um modelo de dados. Essas funções são fundamentais para ajustar o centexto de avaliação de uma fórmula e obter resultados específicos, ignorando ou substituindo filtros existentes.

Quando criamos medidas ou colunas calculadas em DAX, o contexto de avaliaçã é muito importante. Ele determina quais linhas ou valores da tabela são considerados na fórmula. Em algumas situações, precisamos modificar esse contexto para obter resultados mais precisos ou diferentes daqueles gerados pelos filtros padrão aplicados nas visualizações.

As principais funções de modificação de filtros em DAX incluem:

1. ALL: É uma das funções mais usadas nesta categoria. Ela remove os filtros de uma ou mais colunas especificadas, ou mesmo de toda a tabela, garantindo que tpdas as linhas sejam consideradas no cálculo. Isso é especialmente útil quando você quer realizar cálculos ignorando os filtros aplicados em uma visualização específica.

2. ALLEXCEPT: É utilizada para remover os filtros de todas as colunas de uma tabela, exceto aquelas que você deseja manter no contexto de avaliação. Ela permite que você controle quais colunas terão impacto no resultado da fórmula, enquanto outras serão ignoradas.

3. FILTER: É uma função versátil que permite criar filtros personalizados em tempo de cálculo. Ela permite que você especifique condições complexas para filtrar uma tabela e obtenha resultados dinâmicos com base nessas condições.

4. VALUES: É frequentemente utilizada para criar uma lista distinta de valores de uma coluna, removendo qualquer filtro que possa estar aplicado a ela. Ela retorna todos os valores únicos da coluna, independentemente dos filtros nas outras colunas.

Essas funções de modificação de filtros fornecem maior **flexibilidade** e **controle** sobre como os cálculos são realizados em um modelo de dados. Elas são particularmente úteis em relatórios em relatórios interativos, onde os usuários podem aplicar filtros diferentes em várias visualizações e você consegue ajustar o contexto de avaliação para obter resultados precisos e coerentes.

No entanto, é importante usar essas funções com cautela e entender seu impacto no desempenho do modelo de dados. Funções de modificação de filtros podem ser recursos computacionais intensivos, especialmente em grandes volume de dados. Por isso, sempre verifique se a utilização dessas funções é realmente necessária e otimize suas fórmulas para obter o melhor desempenho possível em suas análises.

Fonte: ALura


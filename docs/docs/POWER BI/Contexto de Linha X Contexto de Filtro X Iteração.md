#  Para saber mais: Contexto de linha x Contexto de filtro x Iteração

No Power BI, o DAX (Data Analysis Expressions) desempenha um papel fundamental na criação de fórmulas e expressões para manipulação de dados. Ao trabalhar com o DAX, é importante compreender três conceitos-chave: contexto de linha, contexto de filtro e iterações. Vamos explorar cada um deles.

O contexto de linha refere-se à capacidade do DAX de avaliar as fórmulas em relação a cada linha individual de uma tabela. Isso significa que, ao calcular uma medida ou uma coluna calculada, o DAX considera o valor atual de cada linha como base para o cálculo. Essa funcionalidade do DAX possibilita que você realize operações em nível de linha ou agregue valores com base nas características específicas de cada linha. O contexto de linha é essencial para calcular totais, médias, proporções ou qualquer cálculo que envolva a análise de cada registro individualmente.

Por outro lado, o contexto de filtro refere-se à capacidade do DAX de aplicar filtros a um conjunto de dados antes de realizar um cálculo. Esses filtros podem ser definidos por um usuário ou por condições específicas definidas no modelo de dados. O contexto de filtro é importante quando você deseja restringir os dados de entrada para um cálculo, calculando apenas em um subconjunto específico de registros. Com o contexto de filtro, é possível realizar cálculos condicionais e filtrar dados com base em diferentes critérios, como período de tempo, categorias ou outras características dos dados.

Além disso, o DAX também oferece suporte a iterações, que permitem que você realize cálculos repetitivos em um conjunto de dados. As iterações no DAX são usadas quando você precisa percorrer uma tabela várias vezes para realizar um cálculo mais complexo ou para realizar operações de agregação em um grupo de valores. Por exemplo, você pode usar uma iteração para percorrer cada linha de uma tabela e aplicar uma lógica condicional para calcular uma medida personalizada ou para realizar um cálculo cumulativo.

Alguns exemplos de contexto em funções são:

- A função **AVERAGEX** calcula a média de uma expressão em um contexto especificado. Ela itera por cada linha de uma tabela, aplicando a expressão a cada uma delas e, em seguida, retorna a média desses resultados.
- A função **SUMX** calcula a soma de uma expressão em um contexto especificado. Ela itera por cada linha de uma tabela, aplicando a expressão a cada uma delas e, em seguida, retorna a soma desses resultados.
- A função **ALL** remove todos os filtros aplicados a uma expressão, permitindo que você a avalie em um contexto mais amplo.

Em resumo, entender o contexto de linha, o contexto de filtro e as iterações no DAX do Power BI é essencial para realizar cálculos precisos e avançados. Com esses conceitos em mente, você pode manipular seus dados de forma eficiente e criar medidas personalizadas que atendam às suas necessidades analíticas. O DAX oferece uma ampla gama de funções e recursos para explorar e, à medida que você ganha experiência, poderá aproveitar todo o potencial desta poderosa linguagem de expressão de dados.

Fonte: ALURA



 # Para saber mais: Coluna calculada x Medidas

 Uma coluna calculada é uma coluna adicional que você cria em uma tabela existente com base em uma fórmula ou expressão. Essa coluna é calculada dinamicamente durante a atualização dos dados ou quando você executa uma consulta. As colunas calculadas são úteis quando você precisa derivar novas informações ou realizar cálculos com base em combinações de colunas existentes. Por exemplo, você pode criar uma coluna calculada para calcular a margem de lucro bruto de um produto, subtraindo o custo dos produtos vendidos da receita de vendas.

Por outro lado, as medidas são cálculos que agregam ou resumem valores de uma ou mais colunas em uma tabela. As medidas são criadas usando funções agregadas, como soma, média, máximo, mínimo, entre outras, para fornecer informações resumidas sobre os dados. Diferentemente das colunas calculadas, as medidas são usadas em visualizações interativas, como gráficos e tabelas, permitindo que você explore seus dados em diferentes perspectivas. Por exemplo, você pode criar uma medida para calcular a receita total de vendas ou a contagem de produtos vendidos.

As medidas também são flexíveis e podem responder dinamicamente às interações do usuário, ajustando seus resultados com base nas seleções feitas em filtros ou em outras partes da visualização. Além disso, as medidas podem ser compartilhadas entre diferentes visualizações e relatórios, promovendo a reutilização e a consistência dos cálculos em todo o seu projeto.

No Power BI, você pode criar colunas calculadas e medidas usando a linguagem DAX (Data Analysis Expressions), que oferece uma ampla variedade de funções e operadores para manipular e analisar dados. Através do uso inteligente de colunas calculadas e medidas, você pode enriquecer seus relatórios com cálculos personalizados, indicadores-chave de desempenho (KPIs), métricas e muito mais, proporcionando uma compreensão mais profunda dos seus dados.

As colunas calculadas e as medidas no Power BI têm propósitos diferentes e apresentam algumas diferenças importantes. Aqui estão as principais diferenças entre as duas:

 - **Agregação versus Valor Individual**: As medidas são calculadas para fornecer um valor agregado, como soma, média ou contagem, com base em um conjunto de linhas ou colunas. Por outro lado, as colunas calculadas retornam um valor individual para cada linha da tabela, calculado com base em uma fórmula específica.
 - **Armazenamento**: As colunas calculadas são armazenadas fisicamente no modelo de dados, ocupando espaço no armazenamento. Por outro lado, as medidas são calculadas sob demanda, durante a exibição dos dados, e não ocupam espaço adicional no armazenamento.
 - **Reutilização**: As medidas podem ser reutilizadas em várias visualizações e relatórios. Elas são criadas uma vez e podem ser usadas em diferentes partes do projeto. Por outro lado, as colunas calculadas são específicas para a tabela em que são criadas e não podem ser diretamente reutilizadas em outras tabelas.
 - **Complexidade**: As colunas calculadas são mais adequadas para cálculos simples e fórmulas diretas que podem ser aplicadas a cada linha da tabela. Elas podem usar colunas existentes como base para os cálculos. Já as medidas são mais adequadas para cálculos mais complexos, envolvendo agregações, filtros e contextos mais amplos.
 - **Exibição**: As medidas são projetadas para serem exibidas em visualizações, como gráficos, tabelas e cartões. Elas fornecem informações resumidas e indicadores-chave de desempenho (KPIs). As colunas calculadas, por outro lado, não são projetadas para serem exibidas diretamente em visualizações, porém podem ser usadas como base para cálculos adicionais ou como informações adicionais nos bastidores do modelo de dados.
 - **Contexto**: A coluna calculada trabalha em contexto de linha, pois ela funciona dentro do escopo da linha atual da tabela onde a coluna pertence. Ao fazer referência a uma coluna, o valor correspondente a essa coluna é retornado para a linha em questão. Em contrapartida, a medida trabalha no contexto de filtro, seja do visual ou da consulta. Quando você quiser agregar valores de várias linhas em uma tabela, ao invés de calcular para cada linha, você pode utilizar uma medida.
 
Em resumo, as colunas calculadas e as medidas são recursos poderosos do Power BI que permitem que você realize cálculos personalizados e agregações sobre seus dados. Elas desempenham um papel fundamental na criação de análises e visualizações significativas, fornecendo informações valiosas para a tomada de decisões informadas. Dominar o uso de colunas calculadas e medidas no Power BI capacita você a explorar todo o potencial dos seus dados e apresentá-los de forma clara e impactante.

Fonte: Alura



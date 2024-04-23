# Para saber mais: KeepFilter

A função DAX **KEEPFILTERS** (ManterFiltro, em português) é uma função poderosa no contexto de fórmulas e expressões no Power BI, Power Pivot e outras ferramentas que utilizam a linguagem de fómula DAX. Essa função é usada para preservar os filtros aplicados em uma coluna ou tabela, enquanto você executa cálculos em outra coluna ou tabela. Isso é especialmente útil quando você quer realizar cálculos específicos sem afetar os filtros já aplicados. 

A sintaxe básica da função **KEEPFILTERS** é a seguinte:
```
KEEPFILTERS(expressão)
```

#### 1 - Preservadno Filtros:

A função **KEEPFILTERS** permite que você execute cálculos em uma coluna, mantendo os filtros ativos em outras colunas. Isso é útil quando você deseja realizar cálculos em um subconjunto específico de dados sem afetar os filtros em outras partes do conjunto de dados.

Exemplo:

Suponha que você tenha uma tabela chamada "Vendas" com colunas "Data", "Produto" e "Quantidade". Você deseja calcular a média de quantidades vendidas, mantendo os filtros de data aplicados.
```
MédiaQuantidadeVendida = AVERAGE(KEEPFILTERS('Vendas', 'Vendas'[Quantidade]))
```

#### 2 - Filtros Contextuais

A função **KEEPFILTERS** também pode ser usada para criar cálculos que mantêm filtros específicos durante a avaliação de expressões. Isso ajuda a garantir que os filtros sejam aplicados em cálculos que dependam do contexto.

Exemplo:

Digamos que você queira calcular a porcentagem de vendas de um determinado produto em relação ao total de vendas, mantendo o filtro no produto selecionado.
```
PorcentagemVendasProduto = DIVIDE(SUM(KEEPFILTERS('Vendas', 'Vendas'[Quantidade])), SUM('Vendas'[Quantidade]))
```

Lembre-se de que a função **KEEPFILTERS** pode ser especialmente útil em situações onde você precisa garantir que os cálculos sejam realizados apenas em um subconjunto específico de dados, mantendo os filtros aplicados. Isso ajuda a evitar resultados inesperados ou incorretos em suas análises.

Tenha em mente que as fórmulas DAX podem ser complexas e, às vezes, a ordem de avaliação dos filtros pode afetar os resultados. É improtante entender a lógica subjacente e testar suas fórmulas em diferentes cenários  para garantir que elas estejam produzindo os resultados desejados.

Fonte: Alura


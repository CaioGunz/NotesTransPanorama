# Para saber mais: Contextos

Para entender como é feita a avaliação dos contextos pelo DAX, devemos conhecê-los antes.

**Contexto de Linha**: O contexto de linha se refere ao cálculo que é realizado em cada linha individual de uma coluna. No entanto, ao criar medidas, o cálculo não é efetuado em uma linha específica, mas sim em um contexto mais amplo da coluna como um todo. Duas maneiras são apresentadas para tratar esse contexto de linha:

**Coluna Calculada**: Uma coluna é criada com um cálculo para cada linha da tabela. Isso permite que você realize um cálculo específico para cada linha e retorne o resultado. Essa abordagem é útil quando você precisa de uma coluna adicional com informações específicas para cada linha.

**Funções Iteradoras**: Estas são funções DAX que permite iterar por cada linha da tabela e realizar uma operação, mesmo antes de calcular uma soma, média ou outro tipo de agregação. Um exemplo mencionado é a função SUMX(), que realiza a soma dos valores após iterar por cada linha.

**Contexto de Filtro**: O contexto de filtro é influenciado pelos filtros aplicados nas tabelas. Isso significa que um cálculo agregado, como uma soma, é afetado pelo filtro que foi aplicado à tabela. Por exemplo, a função SUM() aplicada a uma coluna de valores Total será calculada considerando os filtros ativos na tabela.

Com a compreensão desses conceitos, é possível aprofundar o conhecimento na linguagem DAX e criar fórmulas mais complexas. Entender o contexto de linha e de filtro é essencial para evitar erros de lógica ao criar medidas no Power BI e garantir que as métricas calculadas sejam precisas e relevantes para os seus objetivos.

A função **CALCULATE** no Power BI é uma das funções mais poderosas da linguagem DAX, pois ela permite não apenas realizar cálculos, mas também controlar o contexto de filtro em que esses cálculos são aplicados. Isso é o que torna possível tanto sobrescrever um filtro quanto agregar em um filtro já existente. Vamos entender como isso funciona:

#### 1 - **Sobrescrever um Filtro:**

Às vezes, você pode querer realizar um cálculo específico em um contexto de filtro diferente do que está sendo aplicado naturalmente. A função CALCULATE() permite fazer isso. Para sobrescrever um filtro, você pode passar uma ou mais expressões para a função, que serão usadas como critérios para o filtro. Isso basicamente cria um novo contexto de filtro temporário.

Por exemplo, suponha que você tenha uma tabela com vendas e queira calcular a soma das vendas apenas para um determinado ano, independentemente de quaisquer outros filtros aplicados. Você pode fazer o seguinte:
```
TotalVendasPorAno = 
CALCULATE(
    SUM(Vendas[Valor]),
    FILTER(
        ALL(Vendas),
        Vendas[Ano] = 2023
              )
)
```

#### 2 - **Agregar em um Fitlro já Existente**:

Além de sobrescrever filtros, a função CALCULATE() também pode ser usada para agregar cálculos em um filtro já existente. Isso permite que você adicione cálculos às condições de filtro existentes.

Suponha que você tenha uma medida para calcular a média das vendas para um determinado produto, mas deseja calcular essa média apenas para produtos que tiveram mais de 100 unidades vendidas:
```
MediaVendasPorProduto = 
CALCULATE(
    AVERAGE(Vendas[Valor]),
    FILTER(Vendas, Vendas[Quantidade] > 100)
)
```

Nesse caso, a função CALCULATE() está agregando o cálculo da média das vendas à condição de filtro existente (mais de 100 unidades vendidas) sem alterar o filtro original que pode estar aplicado a outros aspectos do relatório.

Em resumo, a função CALCULATE() permite controlar o contexto de filtro no Power BI, dando flexibilidade para sobrescrever filtros ou agregar cálculos em filtros já existentes. Isso é essencial para criar análises precisas e flexíveis nos seus relatórios e dashboards. 

Fonte: Alura


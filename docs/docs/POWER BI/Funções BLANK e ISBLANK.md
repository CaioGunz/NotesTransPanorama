# Utilizando as funções BLANK e ISBLANK

As funções BLANK e ISBLANK no DAX (Data Analysis Expressions) são úteis para trabalhar com valores vazios ou nulos em suas fórmulas. Elas desempenham um papel importante na manipulação e tratamento de dados ausentes ou indefinidos. Vamos explorar como essas funções podem ser combinadas para obter os resultados desejados.

A função BLANK é usada para representar um valor vazio ou nulo em uma expressão. Você pode usá-la para atribuir um valor vazio a uma coluna calculada ou a uma medida. Por exemplo:

```
MinhaColunaCalculada = IF(ISBLANK([MinhaColuna]), BLANK(), [MinhaColuna])
```
Nesse caso, a função ISBLANK é usada para verificar se a coluna [MinhaColuna] esta vazia ou nula. Se sim, a função BLANK é aplicada para atribuir um valor vazio à coluna calculada MinhaColunaCalculada. Caso contrário, o valor da coluna [MinhaColuna] é mantido.

A funlçao ISBLANK, por sua vez, é usada para verificar se um valor está vazio ou nulo. Ele retorna VERDADEIRO se o valor for vazio e FALSO caso contrário. Para avançarmos nessa compreensão, considere o exemplo a seguir:

```
IF(ISBLANK([MinhaColuna]), "Valor Vazio", "Valor Preenchido")
```
Nele, a função ISBLANK é utilizada para verificar se a coluna [MinhaColuna] está vazia. Se sim, a expressão retorna "Valor Vazio", caso contrário, retorna "Valor Preenchido".

Essas combinações de funções são úteis quando você precisa lidar com dados ausentes ou indefinidos em suas análises. Imagine que você está trabalhando em um painel de análise de vendas de uma empresa. Em sua análise, você possui uma coluna que registra os descontos concedidos em cada transação. No entanto, alguns registros podem estar em branco, indicando que nenhum desconto foi aplicado.

Para tratar essa situação, você pode utilizar a função ISBLANK para verificar se o valor na coluna de descontos está vazio ou nulo. Caso seja identificado um valor em branco você pode usar a função BLANK para atribuir um valor vazio a uma coluna calculada ou medida, representando que nenhum desconto foi concedido. Ações como essas permitem que você tenha mais controle sobre como tratar esses valores e manipular os resultados em suas fórmulas. 

Dessa forma, as funções BLANK e ISBLANK são ferramentas valiosas no DAX para trabalhar com valores vazios ou nulos. Ao combiná-las, você pode verificar e tratar dados ausentes de forma eficiente, adptando suas fórmulas para fornecer resultados precisos e significativos em suas análises no Power BI.

Fonte: Alura


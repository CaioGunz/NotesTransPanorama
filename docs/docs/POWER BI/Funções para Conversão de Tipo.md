# Funções para conversão de tipo

A função CONVERT no DAX (Data Analysis Expressions) é usada para converter um valor de um tipo de dados para outro. Ela é útil quando você precisa alterar a representação de um valor para atender às suas necessidades de análise e visualização. A sintaxe básica da função CONVERT é a seguinte:

```
CONVERT(<valor>,<tipo_de_dados>)
```
Onde **<valor.>** é o valor a ser convertido e **<tipo_de_dados>** é o tipo de dados para o qual você deseja converter o valor, incluindo os seguintes tipos: INTEGER, DOUBLE, STRING, BOOLEAN, CURRENCY, DATETIME.

Aqui estão alguns exemplos de uso da função CONVERT:

**INTEGER (Número inteiro):**

```
CONVERT(3.14, INTEGER)
```
Exte exemplo converte o número decimal 3.14 em um número inteiro.

**DOUBLE (Número decimal de ponto flutuante):**

```
CONVERT(42, DOUBLE)
```
Neste exemplo, o número inteiro 42 é convertifo em um número decimal de ponto flutuante.

**STRING(String de texto):**

```
CONVERT(100, STRING)
```
Aqui, o número 100 é convertido em uma string.

**BOOLEAN(Valor lógico):**

```
CONVERT("TRUE", BOOLEAN)
```

Neste exemplo, a string "TRUE" é convertida em um valor booleano.

**DATETIME(Data e hora):**

```
CONVERT("2023-06-15", DATETIME)
```

É importante mencionar que a função CONVERT no DAX tem algumas restrições e limitações em relação à conversão de tipos de dados. Nem todas as conversões são suportadas ou resultam em valores válidos. Portanto, é fundamental garantir que a conversão seja compatível e faça sentido nos dados e na lógica da análise que está sendo realizada.

As funções de conversão de tipo no DAX são ferramentas poderosas para alterar a representação de valores em suas análises no Power BI. Com as funções CONVERT, você pode facilmente converter valores entre diferentes tipos de dados, como números inteiros, números decimais, strings, valores lógicos, valores monetários, datas e horas.

Fonte: Alura


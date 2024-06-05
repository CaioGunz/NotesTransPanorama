# Each e o parâmetro underline

Existem duas expressões extremamente importantes dentro da Linguagem M e que possibilitam a criação de funções anônimas e simples para, por exemplo, referenciar uma coluna de nossa tabela ou agir como um iterador em lista. São elas ```each``` é utiliza para criar de forma simplificada funções anônimas com um parâmetro ```_```. A sintaxe da expressão que gera o ```each``` é a seguinte:

```
(_) => _expressão

//ou 

(_) => expressão
```

***Mas, primeiro, o que são funções anônimas e o que parâmetro ```_``` significa?***

Uma função anônima é uma função que é definida, mas não nomeada, e é utilizada no mesmo local e momento que é criada. Em diversas linguagens, como por exemplo o  Python, essa função é útil para agit tão somente no momento que precisamos, sem ter que guardar seus valores ocupando espaço no código.

Já o parâmetro underline, refere-se a uma variável temporária que, como o própio nome indica, é um tipo de variável que será utilizada apenas no escopo de uma função ou em um dado momento no código. Por se tratarem de variáveis que não serão utilizadas novamente em outro momento no código, o ```_``` age como uma palavra-chave para identidicar essa variável.

Por exemplo, podemos utilizá-la para guardar um valor de uma tabela e executá-la imediatamente após a definição da seguinte forma:

```
let
_ = Table.FromColumns({
{"Daniele", "Ana", "David", "Bruno"},
{1, 2, 3, 4},
{4, 4, 3, 2}},
{"Pessoa", "Matrícula", "Nota"})
in_
     _
```

Percebe-se nesse exemplo que o ```_``` age como uma variável temporária que recebe uma tabela e retorna para nossa consulta a tabela preenchida.

![Each e underline](../ASSETS/eachUnderline.png)

Combinando o uso do underline com a palavra-chave ```each``` criamos uma função simples e ao mesmo tempo poderosa.

Se por exemplo quisermos gerar uma lista de números pares, podemos unir a função ```List.Select()```, que seleciona valores de uma lista a partir de uma função, com o **each** e **under line** juntos. Como na consulta abaixo:

```
let
     Lista = {1 .. 10},
     pares = List.Select(
          Lista,                           // lista com os valores de 1 a 10
          each Number.Mod( _ ,2) = 0     // Retorna o resto da divisão de cada item da lista por 2 e seleciona quem resulta em zero
          )   
in
     pares
```

Aqui o each gera uma função anônima que calcula o resto da divisão entre cada valor da lista ( passado a cada iteração para a variável temporária ```_```) e o número 2 e retorna apenas os valores em que a divisão tenha resto zero, ou seja, os números pares.

Essa combinação também pode ser utilizada para executar uma função nos valores presentes em uma coluna de uma dada tabela, modificando a coluna de acordo com a operação que deseja:

```
#”Nova coluna” = Table.TransformColumns(
               #"Tipo Alterado", {"Temperatura", each #”Função temperatura”( _ )}
               )
```

Neste exemplo, o ```each``` aplica a função presente em ```#"Função temperatura"()``` em todos os valores presentes na coluna ```#Temperatura``` de uma tabela. O ```_``` atua como uma forma de exibir que a operação será aplicada em cada linha da coluna e os valores serão utilizados na função presente em ```#"Função temperatura"()```.

Fonte: **ALURA**
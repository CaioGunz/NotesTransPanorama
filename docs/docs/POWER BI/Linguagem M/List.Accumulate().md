# Para saber mais: List.Accumulate()

Uma outra função muito útil para trabalhar com loops e iterações simples dentro da linguagem M é a função ```List.Accumulate()```.

Esta função recebe uma lista de valores, um valor inicial (semente) e uma função de acumulação, podendo esta ser de soma, multiplicação, divisão ou atá concatenação. A sintaxe da função ```List.Accumulate()```
é a seguinte:

```
List.Accumulate(            // nome da função,
     list as list,            // lista de itens do tipo lista,
     seed as any,             // valor inicial (semente) do tipo any
     accumulator as function  // um acumulador do tipo função
)
```

A execução começa no valor inicial (semente). Na sequência, a função aplica o acumulador no valor inicial repetidamente usando cada item da lista. O usuário pode especificar o tipo de função acumuladora e esta função irá iterar por cada item da lista. Ou seja, cada transformação ocorre por cima da anterior.

Essencialmente , está função realiza a transformação do valor inicial iterando por cada item da lista e, após iterar por todos os elementos, a função retorna o valor acumulado.

Como exemplo, podemos fazer a soma acumulada de uma lista com valores de 1 a 5:

```
let
     Fonte = {1 .. 5},
     Acumulador = List.Accumulate(
          Fonte,                                      // lista com valores a acumular
          0,                                              // valor inicial
          (atual, próximo) => atual + próximo     // acumulador
     )
in
     Acumulador 

// O valor será 15 pela iteração seguindo os seguintes passos
// a partir do acumulador no 3º parâmetro: 
// Passo 1: atual = 0,  próximo = 1 ( Acumulador = 0  + 1 )
// Passo 2: atual = 1,  próximo = 2 ( Acumulador = 1  + 2 )
// Passo 3: atual = 3,  próximo = 3 ( Acumulador = 3  + 3 )
// Passo 4: atual = 6,  próximo = 4 ( Acumulador = 6  + 4 )
// Passo 5: atual = 10, próximo = 5 ( Acumulador = 10 + 5 )

```

Além disso, podemos aplicar o mesmo conceito para diversas aplicações que necessitem de acumulação de valores. Como, por exemplo:

```
let
    Multiplicador = List.Accumulate(
          { 1 .. 5 },                                     // lista com valores a acumular
          1,                                              // valor inicial
          (atual, próximo) => atual * próximo         // acumulador
     ),                         // Retorno = 1 * 1 * 2 * 3 * 4 * 5 = 120

     Divisor = List.Accumulate(
          { 10, 5, 2 },                 
          100,              
          (atual, próximo) => atual / próximo
     ),                         // Retorno 100 / 10 / 5 / 2 = 1

     Concatenador = List.Accumulate(
          { "Meu ", "top ", 5, " filmes", ":" }, 
          "",               
          (atual, próximo) => 
               Text.Combine({atual} & {Text.From(próximo)})
     )                         // Retorno "Meu top 5 filmes:"
in
     Text.From(Multiplicador) & "#(lf)" & Text.From(Divisor) & "#(lf)" & Concatenador
```

Fonte: **ALURA**
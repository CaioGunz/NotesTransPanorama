# Medidas Implícitas e Explícitas
As medidas implícitas são calculadas automaticamente pelo Power BI com base nos dados presentes na tabela. Elas são úteis para realizar operações básicas, como soma, média, contagem, mínimo e máximo. O Power BI identifica automaticamente os campos numéricos na tabela e cria medidas implícitas correspondentes. Essas medidas são atualizadas dinamicamente à medida que os dados são modificados ou filtrados.

Por outro lado, as medidas explícitas são cálculos personalizados criados manualmente pelo usuário. Elas são criadas utilizando a linguagem de fórmulas DAX (Data Analysis Expressions) e permitem realizar cálculos mais complexos e específicos às necessidades do usuário. Com as medidas explícitas, é possível realizar operações matemáticas avançadas, combinar campos de diferentes tabelas, aplicar filtros condicionais e criar métricas personalizadas.

## Exemplo de medida implicita: 
Primeiramente, vamos utilizar a medida implícita. Para isso, você pode adicionar o campo de Faturamento criado anteriormente em um visual, como o de Cartão, por exemplo. Na imagem a seguir, podemos conferir a medida implícita criada:
![medidaImplicita](../assets/medidasImplicitas.png)
Como você pode identificar, ao adicionar o campo “Faturamento” no visual de Cartão, o Power BI automaticamente realiza a soma, por isso o campo está nomeado como “Soma de Faturamento”. Caso você queira modificar o tipo de medida, basta clicar no botão à direita do nome do campo, representado por uma seta apontada para baixo. Um menu então aparecerá com as diversas opções de medidas:
![medidaImplicita2](../assets/medidaImplicita2.png)

## Exemplo de Medida Explicita
Uma outra possibilidade é realizar o cálculo da mesma medida de forma explícita. Nesse caso, podemos utilizar uma fórmula DAX para realizar a soma do faturamento. Para isso, vamos utilizar uma função chamada SUM() com o campo ‘Faturamento’, da seguinte forma:
![medidaExplicita1](../assets/medidaExplicita1.png)
Como você pode notar, o campo adicionado ao visual de Cartão não está mais sujeito a soma, pois trata-se de uma medida criada explicitamente, onde a soma é feita diretamente na fórmula DAX. Para confirmar isso, perceba que as opções de medidas não estão disponíveis para o campo de “Faturamento total” utilizado:
![medidaExplicita2](../assets/medidaExplicita2.png)


[Power BI: medidas implícitas e explícitas](https://www.alura.com.br/artigos/power-bi-medidas-implicitas-e-explicitas?_gl=1*r674sk*_ga*MTI0MjAwNDk0Ni4xNzAyMzg5NTU1*_ga_1EPWSW3PCS*MTcwODk0NzY0MC4xNTcuMS4xNzA4OTQ5Mjc5LjAuMC4w*_fplc*RG4lMkZvWXN5MFhvTlRaUmJYMUNpdzZaQWZSa2QwUkoxT3FzV3BiNkp2MTFaZ1NlVHp0WUxzcjdaVFk2RVV1JTJCY1hTa3NKVTZLUWhEb0t6NFRVQzExcFgyZFk2QmM0RDBRZWhsVW5QUiUyRmNTTzIxZUpBVjNKYmNDY3hEQjFXR25BJTNEJTNE)


# Resumo Método melt() 

O método ```melt()``` é uma ferramenta bastante utilizada para a transformação de dados no Python. Ele faz parte da blibioteca Pandas e é responsável por transformar um DataFrame em um formato mais longo, reorganizando as colunas em linhas, tornando-os mais adequados para análise e visualização de dados. Esse comportamento é o que chamamosde transformação de um DataFrame de "Wide to long" (ampla para longa).

Em um conjunto de dados do tipo "wide", temos muitas colunas com diferentes tipos de informações. Já em um tipo de "long" temos menos colunas e mais linhas, com cada linha contendo várias parcelas de informação. Ao usar ```melt()```, estamos transformando de colunas do nosso DataFrame em linhas para formar um conjunto de dados mais longo.

Para entender esse comportamento, vamos testar em um exemplo. Recebemos o DataFrame abaixo para construir um gráfico de colunas que representa, ano a ano, as vendas de 3 produtos de um mercado. Os dados estão expressos em toneladas.

```
import pandas as pd

# Criando um dataframe
vendas_ton = pd.DataFrame({'Produto': ['Arroz', 'Feijão', 'Açúcar'],
                            '2020': [90, 85, 88],
                            '2021': [92, 94, 89],
                            '2022': [84, 88, 92],
                            '2023': [100, 98, 87]})
vendas_ton
```

Saída:

|   | Produto |	2020  | 2021   | 2022| 2023 |
|:-:| :-----:| :----: | :----: | :--:| :--: |
| 0 | Arroz  |  90    |   92   |  84 | 100  |
| 1 | Feijão |  85    |   94   |  88 | 98   |
| 2 | Açúcar |  88    |   89   |  92 | 87   |

Podemos perceber que temos um DataFrame com cada ano como uma coluna, configurando-o como do tipo "wide". É possível trabalhar com ele dessa forma, mas podemos, por exemplo, trazer os dados dos anos para uma única colunas e seus valores correspondentes em outra colunas se quisermos transformar o nosso conjungto de dados para um formato longo.

Então, podemos utilizar o método ```melt()``` no nosso DataFrame da seguinte forma:

```
vendas_ton_melt = vendas_ton.melt(id_vars='Produto', var_name='Ano', value_name='Toneladas')
vendas_ton_melt
```

Saída:

|   | Produto | Ano	 | Toneladas|
|:-:| :-----: | :--: | :------: |
| 0	| Arroz   | 2020 | 90| 
| 1	| Feijão  | 2020 | 85| 
| 2	| Açúcar  | 2020 | 88| 
| 3	| Arroz   | 2021 | 92|
| 4	| Feijão  | 2021 | 94| 
| 5	| Açúcar  | 2021 | 89| 
| 6	| Arroz   | 2022 | 84| 
| 7	| Feijão  | 2022 | 88| 
| 8	| Açúcar  | 2022 | 92| 
| 9	| Arroz   | 2023 | 100| 
| 10| Feijão  | 2023 | 98| 
| 11| Açúcar  | 2023 | 87| 

Agora, temos o nosso DataFrame devidamente convertido para um tipo "long" e podemos prosseguir para a criação do gráfico requisitado.

Fonte: **ALURA**


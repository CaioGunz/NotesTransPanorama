# Cálculo de Horas no Power BI - Acima de 24h

Estaremos na segunda guia do Power BI, a de Dados, e iremos trabalhar com uma tabela em Excel já importada. Observe a seguir:

![Como cálcular horas - tabela exemplo](../assets/Como-Fazer-Calculo-com-Horas-no-Power-BI-Imagem-1.png.jpg)

A partir daqui, iremos trabalhar com o ambiente temporário do Power Query, o editor de consultas do Power BI. Iremos no menu na parte superior de Página Inicial > Transformar dados. A seguir veremos os passos para realizar os cálculos citados acima.

#### 1. Coluna – Quantidade de horas

O primeiro a se fazer após ter o Power Query aberto é selecionar a coluna de **Fim (necessariamente primeiro)**, e segurando o **Ctrl**, selecionaremos a coluna de **Início**. **Com as duas selecionadas, nessa ordem**, iremos procurar pelo menu **Adicionar coluna > Hora** (símbolo de relógio maior) **> Subtrair.**

Nossa coluna foi criada, mas ela ainda está com formato de horas. Para facilitar nossos cálculos, precisaremos **transformar essas horas para o formato decimal** (número) para depois expor essas horas em uma forma final em horas, minutos e segundos. Para isso, iremos em **Transformar > Duração** (símbolo de relógio menor) **> Total de Horas.**

Para finalizar nossa etapa 1, **renomearemos** a coluna nova criada e transformada com o nome de **“Total de Horas”.**

Observe o resultado:

![Gerar coluna de horas - imagem resultado](../assets/Como-Fazer-Calculo-com-Horas-no-Power-BI-Imagem-2.png.jpg)

Aqui, teremos a nossa nova coluna criada com a diferença de horas entre Fim e Início, nos dando qual foi a quantidade de horas calculada individualmente por cada pessoa, em cada dia apresentado. Iremos na Página **Inicial > Fechar e Aplicar** para continuar fazendo nosso trabalho final.

#### 2. Medida – Quantidade total de horas

Iremos na primeira guia do Power BI **(Relatório), onde vamos criar uma medida**, clicando em qualquer coluna da nossa tabela, no menu à direita, e indo em **Nova Medida**. Como queremos que a **nova medida calcule a quantidade total de horas** daqueles funcionários, iremos fazer a soma da coluna de Total de Horas criada na primeira etapa. Então, sua fórmula será:

```
Total Horas = SUM('Controle de Horas'[Total de Horas])
```

Para visualizar o resultado dessa medida vamos **criar um cartão**, nas visualizações, e **arrastar** a nossa medida criada de **Total Horas** para o campo de **Campos** do cartão. Com isso conseguiremos ver a nossa medida.

 - OBS: Se ela tiver como número inteiro (sem casas decimais), você deve clicar na medida, ir em Ferramentas de medida (ou Modelagem), e alterar a quantidade de casas decimais de Auto para 4. Veremos abaixo que teremos o número **197,9972**:

![Formato em que o calculo vai trazer a hora](../assets/Como-Fazer-Calculo-com-Horas-no-Power-BI-Imagem-3.png.jpg)

#### Variáveis Hora, Minuto e Segundo

Iremos criar **variáveis** para calcular nossa estrutura de horas, minutos e segundos para apresentar da forma que quisermos. Para isso, iremos abrir uma **nova medida**, como no passo 2 do post, e iremos escrever a seguinte fórmula:
```
Horas Trabalhadas =

VAR horas = INT(SUM('Controle de Horas'[Total de Horas]))

VAR minutos = INT((SUM('Controle de Horas'[Total de Horas]) - horas) * 60)

VAR segundos = ROUND(((SUM('Controle de Horas'[Total de Horas]) - horas) * 60 - minutos) * 60,0)

RETURN

VALUE(horas & minutos & segundos)
```

1. Explicação de “horas”:

    Repare que no passo 2 temos as horas como número decimal (quebrado). **Queremos que a nossa variável de “horas” pegue apenas o valor inteiro desse número total de horas calculado na etapa 2**.

    Para isso, usaremos a função **INT**, que nos retornará o inteiro daquele número (Total de Horas), o que nos retornará **197**.

2. Explicação de “minutos”:

    **Queremos que a nossa variável de “minutos” pegue a parte decimal (quebrada) calculada na etapa 2 e multiplique por 60**, para ver quanto aquela parte decimal (de horas) é equivalente em minutos. Fazemos assim porque 1 hora tem 60 minutos, e se temos uma parte decimal de horas, devemos multiplicar por 60 para saber quantos minutos tem naquela “quantidade” decimal.

    Para ter o que queremos de uma forma mais fácil, pegaremos o total de horas (em decimal mesmo) e subtrairemos do que foi calculado por horas, ou seja, a parte inteira das horas. O que sobrará serão nossas horas em decimais, que converteremos em minutos multiplicando por 60.

    Pegaremos apenas a parte inteira (com a função INT) pelo mesmo motivo explicado anteriormente. Ou seja, a parte “quebrada” de minutos será a quantidade de segundos que queremos retornar em seguida. Teremos então **59** minutos.

3. Explicação de “segundos”:

    Iremos **fazer a lógica de cálculo bem parecida para os minutos**, com o adendo de diminuir a quantidade total de minutos, sobrando a parte decimal dos minutos, que é a que converteremos em segundos.

    Ele é mais complicado de visualizar, mas basicamente pegamos o total de horas, diminuímos do total de horas pela parte inteira das horas (calculada pela variável “horas”). Na mesma linha de fórmula pegamos esse valor e diminuímos da parte inteira dos minutos (calculado pela variável “minutos”). O **que sobra aqui é a quantidade decimal (a direita da vírgula) da parte de minutos da nossa “hora original”**.

    Então, o que faremos é pegar esse valor, **multiplicar por 60**, e arredondar com a função **ROUND** para **0** casas decimais, para mostrarmos esse número sem vírgula. Fazendo esse cálculo, teremos **50** segundos.

4. Explicação do “return”:

    Na estrutura da variável, o “return” quer dizer o que o nosso cálculo com variáveis irá retornar ao final do procedimento. Nesse caso, iremos concatenar (juntar) as informações de horas, minutos e segundos.

    OBS: Precisamos colocar a fórmula **VALUE** antes do valor a ser retornado para ele ser visualizado num gráfico, porque até aqui ele será um texto, porque ao usar a função **concatenar**, ela **resulta em um texto**. Nosso resultado então será **1,98 Mi**.

Ué, como assim?

O resultado, apesar de estranho, só está mal formatado, porque ele tentou converter isso em um valor inteiro.

Para começar a mudar isso, iremos clicar na medida **Total de Horas**, ir em **Ferramentas de Medida** (ou Modelagem) e inserir em Formatação um formato personalizado para ela de **“00:00:00”**, como mostramos no vídeo. Aí ficará estranho novamente, como **“02 Mi: : “**.

Para consertar isso, iremos **clicar na visualização do cartão**, iremos na propriedade de **pincel** (formatos), **Rótulo de dados > Exibir unidades** e **trocar de Auto para Nenhum**, para que ele respeite a nossa formatação criada. Estava daquele jeito antes porque ele estava forçando a ser da mesma forma, apesar de termos formatado.

Finalmente teremos o resultado de **197:59:50**, exatamente o que achamos nas variáveis de **“horas”**, **“minutos” e “segundos”**. Observe:

![Formato da hora no KPI após formula](../assets/Como-Fazer-Calculo-com-Horas-no-Power-BI-Imagem-4.png.jpg)

#### Gráfico de colunas para visualização de horas dos funcionários

Para melhor visualizar a quantidade de horas de cada pessoa, podemos **criar um gráfico de colunas**, indo no menu de visualizações e selecionando o quarto ícone. A partir disso iremos arrastar a nossa medida **(Horas Trabalhadas)** para o campo de **Valores** e a coluna **Funcionário** para o campo de **Eixo**.

Ué, que valores são esses nos eixos? É o mesmo caso do passo anterior. O gráfico está forçando a medida a ser mostrada dessa forma.

Para mudar isso, iremos **clicar no gráfico** de colunas, ir em **Eixo Y, Exibir unidades e trocar de Auto para Nenhum**. Assim, teremos todas as informações da forma que queremos. Observe nosso gráfico final, abaixo:

![Gráfico de colunas com horas ](../assets/Como-Fazer-Calculo-com-Horas-no-Power-BI-Imagem-5.png.jpg)


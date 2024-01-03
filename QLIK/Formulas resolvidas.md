# Fórmulas e Resolução de problemas no Qlik Sense e View

Filtro de soma utilizado para o BLITZ RASTREAMENTO (Baseado no ano), Elias achou essa forma de fazer.
```
SUM({<BLITZ.DATA_ANO={'2023'}>} BLITZ.COST)
```

------------------------------------------------------------------------------------------------------------

## Script utilizado para renomear tabelas no Script de carregamento de dados de tabelas de Excel ou Google Sheets

```
  Set dataManagerTables = '','@1';
  //This block renames script tables from non generated section which conflict with the names of managed tables

  For each name in $(dataManagerTables) 
      Let index = 0;
      Let currentName = name; 
      Let tableNumber = TableNumber(name); 
      Let matches = 0; 
      Do while not IsNull(tableNumber) or (index > 0 and matches > 0)
          index = index + 1; 
          currentName = name & '-' & index; 
          tableNumber = TableNumber(currentName) 
          matches = Match('$(currentName)', $(dataManagerTables));
      Loop 
      If index > 0 then 
              Rename Table '$(name)' to '$(currentName)'; 
      EndIf; 
  Next; 
  Set dataManagerTables = ;
```

### Vamos decompor o código para entender sua funcionalidade:
```
Set dataManagerTables = '','@1';
```
⏫  Esta linha inicializa uma variável nomeada **dataManagerTables** com uma lista de nomes de tabelas separados por vírgulas. Parece ser uma lista de tabelas a serem gerenciadas ou renomeadas.

```
For each name in $(dataManagerTables)
```
⏫ Isso inicia um loop que itera sobre cada nome de tabela na **dataManagerTables** lista.

```
    Let index = 0;
    Let currentName = name; 
    Let tableNumber = TableNumber(name); 
    Let matches = 0; 
```
⏫ Estas linhas inicializam diversas variáveis: **index** é definida como 0, **currentName** é definida como o nome da tabela atual, **tableNumber** é o número da tabela atual (se existir) e **matches** é inicializada como 0.

```
    Do while not IsNull(tableNumber) or (index > 0 and matches > 0)
        index = index + 1; 
        currentName = name & '-' & index; 
        tableNumber = TableNumber(currentName) 
        matches = Match('$(currentName)', $(dataManagerTables));
    Loop 
```
⏫ Este é um loop, o qual é executado desde que **tableNumber** não seja nulo ou ambos **index** sejam maiores que 0 e **matches** maiores que 0. No loop, o **index** é incrementado e o **currentName** é atualizado anexando o índice ao nome original. Os **tableNumber** e **matches** são atualizados de acordo.

```
    If index > 0 then 
            Rename Table '$(name)' to '$(currentName)'; 
    EndIf; 
```
⏫ Se **index** for maior que 0, significa que foi encontrado um conflito e a tabela original foi renomeada para nova **currentName**.
```
Next; 
```
⏫ Isso fecha o loop e o processo é repetido para a próxima tabela da **dataManagerTables** lista.

```
Set dataManagerTables = ;
```
⏫ Finalmente, a **dataManagerTables** variável é redefinida, possivelmente para limpá-la para uso posterior.

 -> Em resumo, esse script é usado para gerenciar ou renomear tabelas no script de carregamento de dados do Qlik Sense, lidando especificamente com casos em que pode haver conflitos com nomes de tabelas existentes. O script anexa um índice ao nome da tabela para resolver conflitos e, em seguida, renomeia a tabela conflitante.

------------------------

## Script utilizado no Dash BLITZ RASTREAMENTO para contagem de APTO e INAPTO

```
COUNT(DISTINCT{<
	[BLITZ.DATA_ANO]={$(=If(IsNull(DATA_ANO), '2024', DATA_ANO))}
    //[BLITZ.DATA_MES]={"$(=MONTH(TODAY()))"}
>}
[BLITZ.ID])
``` 
### Vamos decompor o código para entender sua funcionalidade:

O código em questão realiza uma contagem distinta dos IDs no campo **[BLITZ.ID]**. Para isso, são aplicadas condições temporárias utilizando o modificador **{< ... >}**.

A primeira condição 
```
([BLITZ.DATA_ANO]={$(=If(IsNull(DATA_ANO), '2024', DATA_ANO))})
``` 
define que, se o campo **[BLITZ.DATA_ANO]** estiver nulo, ele será ajustado para o valor **'2024'**. Caso contrário, será mantido o valor original de **[BLITZ.DATA_ANO]**. Isso é alcançado por meio da função condicional If.

A segunda condição 
```
([BLITZ.DATA_MES]={"$(=MONTH(TODAY()))"})
```
embora esteja comentada e, portanto, inativa, parece destinada a condicionar o campo **[BLITZ.DATA_MES]** para que seja igual ao mês atual, utilizando a função **MONTH(TODAY())**.

Dessa forma, o código globalmente contabiliza a quantidade única de IDs em **[BLITZ.ID]**, levando em consideração as condições especificadas para **[BLITZ.DATA_ANO]** e **[BLITZ.DATA_MES]** (ainda que a condição para o mês esteja atualmente desativada). Vale ressaltar que as especificidades podem variar dependendo das regras de negócios específicas e da versão do Qlik sendo utilizada.

---------------------------

## Erro de campo não encontrado
```
20240102T091313.248-0300      Error: Field 'F43' not found 
```
### Descrição
Primeiro verifiquei se a conexão puxava o campo não encontrado.
![resolução 001](/ASSETS/Outros/resolução%20qlik%20001.png)

Segundo apaguei o campo não encontrado do Script

![resolução 002](/ASSETS/Outros/resolução%20qlik%20002.png)

E por ultimo carreguei os dados novamente com a coluna "ID" e a coluna "43" e concatenei com a primeira conexão.
```
  Concatenate([ESTADIAS])
  LOAD
      RowNo()	AS id_1,
      @43 as TIPO
  FROM [lib://CONTROLE_ESTADIAS (g10_tp.dev_3)]
  (html, utf8, no labels, table is @1)
  where @1 > 1;
```




-------------------------------------------------------
[Volta Página Principal](/README.md)
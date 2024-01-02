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

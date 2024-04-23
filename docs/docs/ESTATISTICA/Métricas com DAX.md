# Para saber mais: médtricas com DAX

## Tornover

Turnover mede a **taxa de rotatividade**, ou seja, esse indicador é capaz de analisar a quantidade de colaboradores que permanecem na empresa em determinado período.

Abaixo, podemos analisar os tipos de Turnover que estaremos aplicando no nosso projeto (projeto do curso).

#### Turnover Geral
```
TurnoverGeral = DIVIDE (
    ( [Admissoes] + [Movimentações] ) / 2,
    [ColaboradoresAtivos]
)
```

#### Turnover Desligamento
```
TurnoverDesligamentos = DIVIDE (
    [Movimentações],
    [ColaboradoresAtivos]
)
```

#### Meta
```
MetaTurnoverGeral = 0.1
```
**Observação:**quanto **menor** for a taxa de turnover, maior é a retenção de colaboradores e sua respectiva produtividade, evitando também gastos por alta rotatividade.

## Absentísmo

É uma métrica relacionada a **pontualidade** das pessoas colaboradoras. Com esse indicador podemos analisar a **falta ou atrasos** das pessoas de uma empresa, sendo muito importante para evidenciar problemas no ambiente de trabalho. Logo a seguir, podemos notar detalhadamente a métrica mencionada em ação.
```
Absenteismo = CALCULATE (
    COUNT ( Tb_contratacoes[NomeColaboradores] )
        * SUM ( Tb_contratacoes[Faltas] )
        / (
            COUNT ( Tb_contratacoes[NomeColaboradores] ) * 20
        ),
    Tb_contratacoes[MotivoSaida] = "Continua Empregado"
)
```

#### Meta

No caso do absenteísmo, a meta é de 0.05 conforme podemos observar abaixo:
```
MetaAbsenteismo = 0.05
```

#### Movimentações

Referente às Movimentações, elas estão relacionadas aos colaboradores que não estão mais ativos na empresa.
```
Movimentações = CALCULATE (
    COUNTROWS ( Tb_contratacoes ),
    Tb_contratacoes[Status] <> "Ativo"
)
```
#### Admissões

Admissões contabilizam novas pessoas colaboradoras contratadas pela empresa.

O acompanhamento dessa informação pode ser verificada em nosso projeto conforme o código abaixo:
```
Admissoes = CONTROWS (Tb_contratacoes)
```

#### Saldo

Saldo é o balanço entre as movimentações e as admissões
```
Saldo = [Admissoes] - [Movimentações]
```

#### Colaboradores Ativos

Para a contabilização das pessoas colaboradoras ativas podemos contar com uma medida acumulada entre as admissões e as movimentações.
```
ColaboradoresAtivos = VAR AdmissoesAcumulado =
    CALCULATE (
        [Admissoes],
        FILTER (
            ALL ( Tb_contratacoes ),
            [DataContratacao]
                <= MAX ( Tb_contratacoes[DataContratacao] )
        )
    )
VAR DesligamentosAcumulado =
    CALCULATE (
        [Movimentações],
        FILTER (
            ALL ( Tb_contratacoes ),
            [DataContratacao]
                <= MAX ( Tb_contratacoes[DataContratacao] )
        )
    )
RETURN
    AdmissoesAcumulado - DesligamentosAcumulado
```

Bom que você finalizou a leitura deste conteúdo. Nele podemos verificar as descrições das medidas que irão nos auxiliar para a conjunção do projeto. Lembrando que todas elas foram construídas utilizando a linguagem DAX.

Fonte: Alura


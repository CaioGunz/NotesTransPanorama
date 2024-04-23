# Tipos de Junção na Mesclagem do Power BI

No Power BI, uma das principais funcionalidades é a capacidade de mesclar dados de diferentes fontes em um único conjunto de dados para análise. Essa mesclagem é possível graças ao recurso de junções, que permite combinar informações com base em critérios específicos. Existem diferentes tipos de junções disponíveis no Power BI, cada uma com suas características e finalidades. Neste texto, vamos conhecer os tipos de junções mais comuns utilizados na mesclagem de dados no Power BI.

![Tipos de Junção](../assets/aula4_img_tipos_de_juncao.jpg)

 - Esquerda Externa (Left Outer Join): Retorna todas as linhas da tabela esquerda e as linhas correspondentes da tabela direita com base em um critério de correspondência dos relacionamentos entre chaves primárias e estrangeiras das tabelas. Se não houver correspondência na tabela direita, os valores serão preenchidos com nulos.

 - Direita Externa (Right Outer Join): Retorna todas as linhas da tabela direita e as linhas correspondentes da tabela esquerda com base em um critério de correspondência. Se não houver correspondência na tabela esquerda, os valores serão preenchidos com nulos.

 - Completa Externa (Full Outer Join): Retorna todas as linhas das duas tabelas, combinando registros com base em um critério de correspondência. Se não houver correspondência em uma das tabelas, os valores correspondentes serão preenchidos com nulos.

 - Interna (Inner Join): Retorna apenas as linhas correspondentes das duas tabelas com base em um critério de correspondência. As linhas não correspondentes são excluídas do resultado final da mesclagem.

 - Anti Esquerda (Left Anti Join): Retorna apenas as linhas da tabela esquerda que não possuem correspondência com base em um critério de correspondência. As linhas correspondentes da tabela direita são excluídas do resultado.

 - Anti Direita (Right Anti Join): Retorna apenas as linhas da tabela direita que não possuem correspondência com base em um critério de correspondência. As linhas correspondentes da tabela esquerda são excluídas do resultado.

 Esses tipos de junções de mesclagem no Power BI são extremamente úteis para combinar e analisar dados de diferentes fontes, permitindo obter insights valiosos e tomar decisões informadas.

Caso tenha interesse em complementar seus estudos sobre mesclagem, recomendo a leitura do artigo [Power BI: Mesclando consultas no Power Query](https://www.alura.com.br/artigos/power-bi-mesclando-consultas-no-power-query?_gl=1*1nua6sj*_ga*MTI0MjAwNDk0Ni4xNzAyMzg5NTU1*_ga_1EPWSW3PCS*MTcwOTU3OTQ1Ni4xODkuMS4xNzA5NTgxNTUxLjAuMC4w*_fplc*MGtpZ3VJcWI4MmRsRjJ4RFJkVVhuJTJCb0lkSFk5anhGOGElMkJMblJqdVJvVXdsbENKbDUzdEpNdnBxVzRsc00zVUoybG04RlY0JTJCTHp4a1k3QW93RmV2MWhxVUhvZ1dXbHRFSVBNTFFFOVZXOFFWeFp0bk1GUnRNRUtUSnZNMUl3JTNEJTNE), que explica os tipos de mesclagem e o comportamento de cada um deles, além de pontuar como a mesclagem por ajudar a reduzir o tempo de carregamento dos dados e evitar relacionamentos desnecessários.

Fonte: ALURA


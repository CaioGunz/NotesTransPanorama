# Para saber mais: características da Fato e Dimensão

Na modelagem de dados, as tabelas **Fato** e **Dimensão** são usadas para representar os dados de maneira otimizada para consulta e análise. Existem várias características das tabelas de fatos e dimensões na modelagem de dados, como você pode ver a seguir:

- As tabelas **Fato** contêm **dados quantitativos**, que geralmente são numéricos e podem ser agregados ou resumidos. Elas são **organizadas em torno de um tema central**, como vendas ou estoque, e podem conter uma dimensão de data para permitir que os **dados sejam analisados ao longo do tempo**.

- As tabelas **Dimensão** contêm **dados qualitativos** que fornecem **contexto e informações** básicas para as medidas na tabela Fato. Elas geralmente são organizadas em torno das entidades que estão sendo mantidas, como produtos, clientes, ou locais. Além disso, **podem conter uma dimensão de tempo**.

- Tabelas **Fato e Dimensão** são normalmente projetadas para **oferecer suporte a consulas e análises rápidas**. Elas geralmente são **projetadas usando técnicas de desnormalização e modelagem de dados** para otimizar o desempenho e facilitar a extração de insights dos dados.

- As **tabelas Fato** geralmente **são maiores e contém linhas** do que as tabelas de dimensões, pois contêm dados agregados. As **tabelas Dimensão** são normalmente **menores e contêm menos linhas**, pois contêm informações detalhadas sobre as enteidades que estão sendo medidas.

- Em um modelo de dados, as **tabelas Fato e Dimensão** são normalmente **organizadas em um esquema em estrela ou floco de neve**, o que permite que os dados sejam facilmente consultados e analisados.

- As tabelas Fato e Dimensão precisam estar de acordo com algumas regras para que o relacionamento ocorra. Uma **tabela Fato deve se relacionar diretamente apenas com tabelas Dimensão**, enquanto que uma **tabela Dimensão deve se relacionar diretamente apenas com tabelas Fato**.

Essas características são importantes para entendermos como os modelos são esquematizados.

fonte: **ALURA**
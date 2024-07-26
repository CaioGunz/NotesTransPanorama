# Para saber mais: USERNAME() e USERPRINCIPALNAME()

As funções DAX ```USERNAME()``` e ```USERPRINCIPALNAME()``` são utilizadas no Power BI e no Microsoft Excel Power Pivot para trabalhar com informações de segurança, filtragem, e personalização em modelos de dados. Vamos explorar essas funções em detalhes, destacando seuas diferenças e casos de uso.

### **1 - ```USERNAME()```**

A função ```USERNAME()``` retorna o nome do usuário do Windows do contexto de segurança atual. Esse nome de usuário é obtido a partir das credenciais com as quais o usuário se autenticou no sistema operacional. A função ```USERNAME()``` é frequentemente usada para criar medidas ou colunas calculadas que as ajustem com base no usuário atual. Ela é útil quando você deseja personalizar as vesualizações de dados ou restringir o acesso a certos dados com base nos usuários.

**Exemplo de Uso do ```USERNAME()```:**

Suponha que você está criando um painel no Power BI que mostra dados de vendas. Você deseja calcular uma medida que mostra as vendas totais apenas para o usuário atual. Nesse caso, você pode usar a função ```USERNAME()``` em conjunto com outras funções DAX para criar uma medida personalizada que realiza esse cálculo.

### **2 - ```USERPRINCIPALNAME()```:**

A função ```USERPRINCIPALNAME()``` também é usada para trabalhar com segurança e personalização em modelo de dados, mas ela retorna o nome do usuário principal do usuário atual em um formato de endereço de email(por exemplo, user@domain.com). Geralmente, essa função é usada em cenários em que a identificação precisa ser feita com base no endereço de email do usuário, como quando se integra o Power BI com o Azure Active Directory ou outras fontes de autenticação.

**Exemplo de uso do ```USERPRINCIPALNAME()```:**

Imagine que você está desenvolvendo um painel no Power BI que exibe informações de recursos humanos. Você deseja criar uma medida que mostra a contagem de funcionários, mas deseja que essa medida seja filtrada automaticamente com base no usuário conectado. Utilizando a função ```USERPRINCIPALNAME()```, você pode criar essa medida de maneira que cada usuário veja apenas a contagem de funcionários relevantes para eles.

### Diferença e Casos de Uso:

 - **Formato de Saída:**
    - ```USERNAME()```: Retorna o nome de usuário do Windows.
    - ```USERPRINCIPALNAME()```: Retorna o nome de usuário principal (endereço de email) do usuário.
 - **Autenticação:**
    - ```USERNAME()```: Baseia-se nas credenciais de autenticação do sistema operacional.
    - ```USERPRINCIPALNAME()```: Pode ser vinculado a fonte de autenticação mais abrangentes, como Azure Acitive Directory.
- **Personalização e Filtragem:**
    - Ambas as funções podem ser usadas para personalizar medidas e visualizaç~ies com base no usuário atual.
    - ```USERNAME()```: é mais apropiado quando a personalização é baseada no nome de usuário do Windows.
    - ```USERPRINCIPALNAME()```: é mais apropiado quando a personalização é baseada no endereço de email e pode ser mais útil em ambientes corporativos.

Em resumo, as funções ```USERPRINCIPALNAME()``` e ```USERNAME()``` são poderosas ferramentas para personalização e controle de segurança em modulos de dados no Power BI e no Excel Power Pivot. Ao escolher entre as duas, considere o contexto e as necessidades específicas do seu projeto, incluindo o tipo de autenticação e a forma como você deseja filtrar ou personalizar os dados para usuários.

**Fonte: ALURA**
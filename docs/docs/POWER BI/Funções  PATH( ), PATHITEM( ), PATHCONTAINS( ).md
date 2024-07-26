# Para saber mais: PATH( ), PATHITEM( ), PATHCONTAINS( )

As funções DAX (Data Analysis Expressions) são uma parte fundamental do Power BI, permitindo realizar cálculos complexos em conjuntos de dados. As funções PATH(), PATHITEM() e PATHCONTAINS() são úteis quando você está lidando com hierarquias de dados e deseja realizar análises em caminhos específicos dentro dessas hierarquias. Vamos explorar cada uma delas com exemplos para entender melhor.

### **1. Função PATH()**

A função PATH() é usada para criar um caminho de concatenação de valores a partir de colunas específicas em uma tabela. Ela é geralmente usada para criar uma representação hierárquica de elementos, onde cada elemento é concatenado com o elemento pai que o precede.

**Exemplo: Organização Hierárquica**

Suponha que você tenha uma tabela chamada "Organização" que representa a estrutura hierárquica de uma empresa, com colunas como "Departamento" e "Funcionário". Você pode usar a função PATH() para criar um caminho hierárquico para cada funcionário.

```Hierarquia = PATH(Organização[Departamento], Organização[Funcionário])```

### **2. Função PATHITEM()**

A função PATHITEM() é usada para acessar um elemento específico de um caminho gerado pela função PATH(). Isso é útil quando você deseja extrair um elemento específico de um caminho hierárquico.

**Exemplo: Extração de Elementos**

Continuando com o exemplo anterior, suponha que você queira extrair o nome do segundo nível de hierarquia para cada funcionário.

```NomeNível2 = PATHITEM(Organização[Hierarquia], 1)```

### **3. Função PATHCONTAINS()**

A função PATHCONTAINS() é usada para verificar se um caminho específico contém um valor ou uma sequência de valores. Isso é útil para filtrar dados com base em caminhos hierárquicos.

**Exemplo: Filtragem de Dados Hierárquicos Agora, imagine que você deseja filtrar os funcionários que estão em um determinado caminho hierárquico, como "Departamento A > Equipe 1".**

```FuncionáriosEquipe1 = FILTER(Organização, PATHCONTAINS(Organização[Hierarquia], "Departamento A/Equipe 1"))```

Esses exemplos ilustram como as funções PATH(), PATHITEM() e PATHCONTAINS() podem ser usadas para lidar com hierarquias de dados e realizar análises específicas em caminhos dentro dessas hierarquias. Elas são especialmente úteis em situações onde você precisa trabalhar com estruturas hierárquicas complexas e executar análises precisas em diferentes níveis.

**Fonte: ALURA**
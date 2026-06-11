# O projeto e a avaliação

> Esse projeto será avaliado com base em uma rúbrica. As rúbricas ficam disponíveis nas lições dos projetos, onde cada pessoa estudante consegue entender como será avaliado. Você usará esse material para avaliar!

> A pessoa estudante vai entrega um link do google sheets e dentro dela deve existir:

#### Critérios de avaliação


##### **Precisão técnica:**

- [ ]  Dados originais preservados
- [ ]  Limpeza documentada e justificada
- [ ]  Cálculo correto de todas as métricas
- [ ]  Gráficos tecnicamente corretos e bem rotulados

##### **Qualidade profissional:**

- [ ]  Abas organizadas e com nomes descritivos
- [ ]  Relatório estruturado e fácil de ler
- [ ]  Insights relevantes para o negócio identificados
- [ ]  Recomendação específica e viável

##### **Demonstração das habilidades do módulo:**

- [ ]  Identificação de estruturas de dados
- [ ]  Reconhecimento e correção de tipos de dados
- [ ]  Técnicas de limpeza aplicadas corretamente
- [ ]  Uso correto de funções de agregação
- [ ]  Criação de visualizações básicas eficazes
- [ ]  Comunicação clara da metodologia e dos resultados


---

## Projeto - Limpeza e resumo de dados em planilhas

### O Desafio: dados da VentaExpress

Você recebeu um arquivo de vendas com informações valiosas, mas que apresenta vários problemas comuns do mundo real:

- Dados com formato inconsistente
- Valores duplicados e ausentes
- Colunas desorganizadas
- Informações que precisam ser divididas ou combinadas
- Falta de documentação clara

Sua missão é transformar esses dados caóticos em um **relatório profissional e compreensível** que responda às principais perguntas do negócio.

### Dataset do projeto

Contexto do negócio:

A VentaExpress vende produtos de tecnologia (laptops, celulares, fones de ouvido e tablets) por meio de sua plataforma online em diferentes cidades do Brasil.

Período de análise: O dataset contém todas as vendas de **outubro a dezembro de 2024 (4º trimestre de 2024)**.

Arquivo base: `vendas_q4_2024_bruto.csv`.

[Dataset disponibilizad para pessoas estudantes](https://docs.google.com/spreadsheets/d/15I6CHI-qcfbv6gjg1bA9C6xVS_frG5qV/edit?usp=sharing&ouid=118287703665760720712&rtpof=true&sd=true)

---

### Objetivos do projeto

Ao concluir este projeto, você terá demonstrado sua capacidade de:

1. **Identificar e documentar problemas** em um dataset real
2. **Aplicar técnicas de limpeza** de forma sistemática e justificada
3. **Organizar dados** seguindo boas práticas profissionais
4. **Calcular métricas-chave** relevantes para decisões de negócio
5. **Criar visualizações** que comuniquem insights de forma eficaz
6. **Estruturar um relatório** claro e útil

---

### Parte 1: Exploração e diagnóstico inicial (30 minutos)

1. **Observe o dataset e explore-o para conhecê-lo.**
2. **Renomeie as abas:**
    - De `ventas_q4_2024_bruto` para `Dados_Originais` → para preservar os dados sem modificar
    - De `Página1` para `Dados_Limpos` → onde você fará a limpeza
    - De `Página2` para `Análise` → para cálculos e métricas
    - De `Página3` para `Visualizações` → para os gráficos
    - De `Página4` para `Relatório_Executivo` → para o resumo final

Recomendamos ter uma aba extra para cálculos auxiliares. Você pode excluí-la ao final.

---


### Parte 2: Limpeza e preparação dos dados (45 minutos)

Na aba `Dados_Limpos`, aplique as seguintes transformações:

#### 🧹 **Tarefas obrigatórias de limpeza:**

1. **Remover duplicados completos:**
    - Use `Dados > Limpeza de dados > Remover duplicados`
    - Documente na aba `Relatório_Executivo` quantos duplicados foram encontrados
2. **Formatar colunas de valores monetários:**
    - Aplique formato de moeda nas colunas:
        - `Preço Unitário`
        - `Valor Total`
    - Formato esperado: **$ xxxx.xx** (ex: $ 104.30)
3. **Padronizar os nomes das cidades:**
    - Crie uma nova coluna chamada `Cidade corrigida` ao lado da coluna `Cidade`
    - Use uma fórmula para deixar:
        - Primeira letra maiúscula
        - Restante minúscula
    - **Função útil:** `PROPER()` / `PRI.MAIÚSCULA()`
4. **Dividir a informação dos produtos:**
    - Use a função **“Dividir texto em colunas”**
    - Separe a coluna `Produto` em 3 novas colunas:
        - `Categoria`
        - `Tipo`
        - `Especificações`
    - **Importante:** mantenha a coluna original `Produto`
    
    **Exemplo:**
    

| Produto | Categoria | Tipo | Especificações |
| --- | --- | --- | --- |
| Laptop-Gaming-16GB | Laptop | Gaming | 16GB |
1. **Tratar valores ausentes:**
    - Identifique células vazias em:
        - `Preço Unitário`
        - `Valor Total`
    - Documente quantos valores ausentes existem na aba `Relatório_Executivo`
    
    💡 **Dica:**
    
    - Se faltar **Preço unitário** → calcule: `Valor total ÷ Quantidade`
    - Se faltar **Valor total** → calcule: `Quantidade × Preço unitário`

#### ✅ **Validação dos dados limpos**

Checklist de qualidade:

- [ ]  Não há duplicados
- [ ]  Tipos de dados estão corretos
- [ ]  Nomes das cidades estão padronizados
- [ ]  Valores ausentes foram tratados corretamente


### Parte 3: Análise e cálculo de métricas (30 minutos)

Na aba `Análise`, calcule as seguintes métricas:


#### 📊 **Totais:**

Calcule as seguintes métricas:

1. **Vendas totais do trimestre:**
    - Função: `=SOMA(intervalo_dos_valores_totais)`
2. **Venda média por transação:**
    - Função: `=MÉDIA(intervalo_dos_valores_totais)`
3. **Número total de transações:**
    - Função: `=CONT.NÚM(intervalo_de_transações)`

#### **📊 Métricas por categoria, cidade e mês:**

Agora calcule totais e médias para dados filtrados:

1. **Categoria mais vendida (por quantidade)**
2. **Cidade com maiores vendas totais**
3. **Mês com melhores vendas totais**
4. **Preço médio por categoria de produto**

💡 **Importante:** Quando você aplica filtros, funções como `=SUM()` / `=SOMA()` e `=AVERAGE()` / `=MÉDIA()` **não consideram apenas os dados visíveis automaticamente**.

Mas não se preocupe — aqui estão **3 formas de resolver isso**:

#### 3 formas de calcular somas e médias com dados filtrados

a. *(Recomendado) Use o cálculo automático que aparece na barra inferior do Google Sheets ao selecionar a coluna filtrada. Ele calcula apenas os dados visíveis.*

b. *Copie os dados filtrados e cole em uma nova aba, depois aplique:*

- `=SUM()` / `=SOMA()`
- `=AVERAGE()` / `=MÉDIA()`

c. *Utilize uma **tabela dinâmica (pivot table).** Você aprenderá isso no próximo módulo.*


### Parte 4: Visualização de dados (25 minutos)

Na aba `Visualizações`, crie **no mínimo 2 gráficos** que respondam às perguntas de negócio:

**📈 Gráficos obrigatórios:**

1. **Gráfico de barras: Vendas por cidade**
    - Dados: Cidade vs. Vendas totais
    - Objetivo: Comparar o desempenho entre mercados
2. **Gráfico de linhas: Evolução das vendas mensais**
    - Dados: Mês vs. Vendas totais
    - Objetivo: Identificar tendências ao longo do tempo

**📋 Requisitos técnicos:**

- Títulos claros e descritivos
- Eixos corretamente identificados
- Cores apropriadas e profissionais
- Dados organizados de forma lógica

**🎯 Perguntas que seus gráficos devem responder:**

- Em qual cidade a VentaExpress tem melhor desempenho?
- Como as vendas evoluíram ao longo do trimestre?
- Existem padrões sazonais evidentes?


### Parte 5: Relatório executivo e documentação (30 minutos)

Na aba `Relatório_Executivo`, responda de forma clara e baseada em dados às seguintes **perguntas de negócio**:

1. Qual foi o produto mais vendido (em quantidade)?
2. Qual cidade gerou o maior volume de vendas totais?
3. Qual é o preço médio por categoria de produto?
4. Escolha um desses insights e adicione uma **recomendação diretamente derivada** dele
- *Exemplo:* “As vendas estão concentradas em Campinas, responsável por 38% do total. Recomenda-se priorizar campanhas promocionais nessa cidade no próximo trimestre.”

Metodologia de limpeza:

- Liste os problemas encontrados nos dados originais

Limitações:

- Que informações adicionais seriam úteis para aprofundar a análise?

---

### Recursos de apoio

#### 🔧 Funções úteis para o projeto

Limpeza de dados:

- `PROPER()` / `PRI.MAIÚSCULA()`: padronizam o uso de maiúsculas e minúsculas
- `SPLIT()`: divide texto em colunas

**Análise de dados:**

- `SOMA()`, `MÉDIA()`, `CONT.NÚM()`, `MÁXIMO()`, `MÍNIMO()`: realizam agregações básicas
- **Filtros automáticos:** segmentam os dados antes da aplicação das funções

**Organização:**

- Filtros automáticos (`Dados > Criar um filtro`)
- Ordenação (`Dados > Classificar intervalo`)
- Formatação condicional para destacar padrões

### 📋 Estratégia de análise com filtros

**Para calcular métricas por segmento:**

- Aplique filtros automáticos à sua tabela limpa
- Filtre pela categoria que deseja analisar (ex.: cidade = “Curitiba”)
- Para não alterar os dados limpos, recomenda-se copiar os dados filtrados e colá-los em uma nova aba em branco
- Aplique a função correspondente sobre os dados
- Documente o resultado antes de mudar o filtro
- Repita o processo para outras categorias

**Exemplo prático:**

- Para vendas por cidade:
Filtre **“Cidade = Curitiba”** → `=SOMA(coluna_dos_valores_visíveis)`
- Para o produto mais vendido:
Filtre cada produto → `=SOMA(coluna_da_quantidade_visível)` → compare os resultados

---
## Rubrica - critérios de avaliação

| **Parte do projeto** | **Pergunta** | **✅ Excelente 9-10** | **🟡 Recomendação 7-8** | **❌ Falha 5-7** |
| --- | --- | --- | --- | --- |
| **Parte 1: Configuração do projeto** | Você renomeou corretamente as abas do arquivo? | Todas as abas foram renomeadas exatamente como indicado. | Faltam 1-2 abas renomeadas ou há pequenos erros. | As abas não foram renomeadas ou estão incorretas. |
| **Parte 2: Limpeza sistemática** | Você removeu duplicatas e documentou a quantidade encontrada? | As duplicatas foram removidas corretamente e a quantidade foi documentada no Relatório Executivo. | As duplicatas foram removidas, mas a quantidade não foi documentada ou a documentação é ambígua. | As duplicatas não foram removidas ou a etapa foi ignorada. |
| **Parte 2: Limpeza sistemática** | Os formatos de data estão padronizados (DD/MM/AAAA)? | Todas as datas estão no formato correto e como tipo "Data". | Algumas datas estão corretas, mas há inconsistências ou pequenos erros. | As datas não estão padronizadas ou possuem múltiplos formatos incorretos. |
| **Parte 2: Limpeza sistemática** | Os valores monetários têm formato correto (R$ xxxx.xx)? | Todos os valores têm formato consistente e profissional. | A maioria está correta, mas há células com símbolos inconsistentes ou sem formatação. | Não foi aplicado formato monetário ou há vários erros de consistência. |
| **Parte 2: Limpeza sistemática** | Os nomes das cidades estão limpos? | Nomes padronizados, sem espaços extras ou caracteres especiais. | A maioria dos nomes está limpa, mas há 1-2 erros visíveis. | Nomes com erros evidentes, espaços ou caracteres não corrigidos. |
| **Parte 2: Limpeza sistemática** | Você dividiu corretamente as informações dos produtos? | Todos os campos compostos foram divididos corretamente. | Divisão parcial ou incompleta; faltam detalhes ou há pequenos erros. | A informação não foi dividida ou o formato continua confuso. |
| **Parte 2: Limpeza sistemática** | Tratamento adequado de valores ausentes? | Valores ausentes foram substituídos pela mediana e justificados. | Foram substituídos sem justificativa clara ou há inconsistências. | Não foram tratados adequadamente ou ficaram em branco. |
| **Parte 2: Validação dos dados limpos** | A planilha de dados limpos atende aos critérios de validação? | Atende a todos os itens de validação definidos na lista. | Atende parcialmente; há 1-2 erros menores. | Há vários erros que afetam a qualidade da análise. |
| **Parte 3: Métricas-chave** | Você calculou corretamente todas as métricas necessárias? | Todas as métricas estão presentes, corretas e com fórmulas visíveis. | Faltam 1-2 métricas ou há pequenos erros. | Várias métricas estão ausentes ou incorretas. |
| **Parte 4: Visualização de dados** | Você criou pelo menos 2 visualizações com qualidade técnica? | Gráficos tecnicamente corretos, com títulos e eixos bem definidos. | Gráficos presentes, mas com pequenos erros de apresentação. | Não há gráficos ou estão incorretos. |
| **Parte 4: Visualização de dados** | Os gráficos respondem às perguntas de negócio? | Os gráficos respondem claramente às perguntas propostas. | Têm relação, mas não respondem completamente. | Não contribuem para responder questões-chave. |
| **Parte 5: Relatório executivo** | Você estruturou um relatório claro e profissional? | Estrutura clara, seções completas e redação profissional. | Estrutura confusa ou faltam pequenas seções. | Relatório incompleto, desorganizado ou ausente. |
| **Parte 5: Relatório executivo** | Você documentou os achados com dados específicos? | Achados claros e sustentados por dados concretos. | Achados vagos ou com pouca evidência. | Não foram documentados ou estão incorretos. |
| **Parte 5: Relatório executivo** | Você incluiu ao menos uma recomendação baseada em dados? | Recomendação específica, viável e baseada em um achado. | Recomendação vaga ou sem conexão com os dados. | Não há recomendação ou não está relacionada à análise. |
| **Parte 5: Relatório executivo** | Você justificou a metodologia de limpeza aplicada? | Documentação clara dos problemas encontrados e das ações tomadas. | Justificativa incompleta ou pouco clara. | A metodologia não foi documentada. |
| **Parte 5: Relatório executivo** | Você identificou ao menos uma limitação da análise? | Limitação claramente definida e relevante. | Limitação superficial ou pouco clara. | Nenhuma limitação foi identificada. |
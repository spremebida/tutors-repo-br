# O projeto e a avaliação

> Esse projeto será avaliado com base em uma rúbrica. As rúbricas ficam disponíveis nas lições dos projetos, onde cada pessoa estudante consegue entender como será avaliado. Você usará esse material para avaliar!

> A pessoa estudante vai entrega um link do google sheets e dentro dela deve existir as seguintes abas obrigatórias:
    - **`README`** completo (objetivo, tabelas, KPIs, validações de QA e observações adicionais).
    - **`Resumo`** com resposta para cada pergunta de negócio e a recomendação (implicação).
    - **`Dashboard`** com filtro por departamento, 2 KPIs dinâmicos (ou seja, atualizados conforme o departamento selecionado) e um gráfico para cada KPI.
    - **`Pivot`** com os cálculos dos 2 KPIs para o período de 2012 agrupados por departamento.
    - **`clean_vendas`** com as colunas integradas/enriquecidas.
    - **`raw_vendas`**, **`raw_departamento`** e **`raw_lojas`**.

  
---
## Projeto - Resumo executivo de vendas da Walmart

### Recrutamento na Walmart: previsão de vendas nas lojas

> esses datasets ainda estão em espanhol! Estamos traduzindo e será atualizado aqui.

[Dataset | Aluno](https://docs.google.com/spreadsheets/d/11-S5rmn1_xGpSa0IUf5TU3zC0bSsEDidhgh5Gf5VBJ4/edit?usp=sharing)

[Dataset | Solução](https://docs.google.com/spreadsheets/d/19t72RP6RLzAJrbrZQWpgVHhB2W7d9009kCsdzkzW034/edit?usp=sharing)


---

#### Introdução

Imagine que você é analista na Walmart, e a Diretoria Comercial precisa de um **resumo executivo** para decidir ajustes de orçamento e estoque.

Seu desafio será limpar, organizar e analisar os dados de vendas semanais de 2012, com o objetivo de responder perguntas estratégicas do negócio usando KPIs bem definidos e visualizações claras.

Este projeto colocará à prova suas habilidades em:

- limpeza e preparação de dados;
- criação de métricas de negócio (KPIs);
- construção de dashboards interativos;
- comunicação executiva usando o método **C-F-I** (*Context, Finding, Implication*).

---

#### Dataset do projeto

##### Arquivos disponíveis

- **`sales.csv`** → colunas: `Store`, `Dept`, `Date`, `Weekly_Sales`, `IsHoliday`
- **`stores.csv`** → colunas: `Store`, `Type` (A/B/C), `Size`
- **`departments.csv`** → colunas: `Dept`, `dept_name`

---

#### Contexto do negócio

A Diretoria Comercial da Walmart deseja responder duas perguntas principais:

1. **Quais categorias de departamento foram mais eficientes para gerar vendas em 2012?**
    - **KPI 1: Vendas por metro quadrado (eficiência):** `Vendas / Tamanho`.
2. **Quais departamentos contribuíram mais para o negócio e quais ficaram abaixo do potencial?**
    - **KPI 2: Participación del departamento:** `VendasDepartamento / VendasTotais`.

---

#### Objetivos do projeto

Ao concluir este projeto, você terá demonstrado sua capacidade de:

1. **Preparar dados** para análise
(limpeza, enriquecimento e documentação)
2. **Construir KPIs-chave** para avaliar eficiência e participação
3. **Criar dashboards dinâmicos** com filtros e visualizações úteis para stakeholders
4. **Comunicar insights executivos** usando o método C→F→I
5. **Aplicar QA (Quality Assurance)** para garantir qualidade e rastreabilidade da análise
---
#### Instruções do projeto

##### Processo em etapas

- **LIMPAR:** preparar os datasets para análise.
- **ENRIQUECER:** unir tabelas em uma única fonte integrada.
- **RESUMIR:** criar tabelas dinâmicas com os KPIs.
- **DASHBOARD:** desenvolver um dashboard com filtros e visualizações.
- **RESUMO:** escrever um relatório no formato C-F-I.
- **QA:** documentar validações de qualidade e criar um `README`.

---

#### Parte 1: Limpeza de dados (20–30 min)

**Aba: `clean_vendas`**

1. Copie a aba `raw_vendas` e renomeie para `clean_vendas`. Marque esta aba na cor verde.
2. Normalização das colunas (`Data`, `vendas_semanais`):
    1. `Data`: Garanta que os valores estejam formatados como moeda:
    2. `vendas_semanais`: Garanta que os valores estejam formatados como moeda: R$ xxxx,xx (Exemplo, R$ 1.005,05)

**Resultado esperado:** A aba `clean_vendas` deve estar pronta para análise com as seguintes colunas: 
`loja | dept | data | vendas_semanais | eh_feriado | semana_limpa`

---

#### Parte 2: Enriquecimento (20–30 min)

**Aba: `clean_vendas`**

**O que você deve fazer:** adicionar na aba `clean_vendas` as colunas:

- `tipo`
- `tamanho`
- `nome_dept`

usando informações dos outros datasets.

**Por quê:** essas colunas serão necessárias para: calcular eficiência, construir KPIs e criar relatórios mais claros para stakeholders.

**Funções úteis:**

Inglês

`=VLOOKUP(valor_procurado; matriz_tabela; número_índice_coluna; FALSO)`

Português (Google Sheets/Excel)

`=PROCV(valor_procurado; matriz_tabela; número_índice_coluna; FALSO)`

**Resultado esperado:** você deverá obter uma tabela consolidada com todas as colunas principais:

> `loja | dept | data | vendas_semanais | eh_feriado | semana_limpa | tipo | tamanho | nome_dept`
> 

---

#### Parte 3: Resumo com tabelas dinâmicas (20–30 min)

**Aba: `Pivot`**

**O que você deve fazer**: Construir uma tabela dinâmica para cada KPI.

**Por quê**: As tabelas-resumo serão a base do dashboard dinâmico.

1. **KPI 1: Vendas por m²**
    
    **Passo 1**: Crie uma tabela agrupada por departamento contendo:
    
    - `SOMA` das vendas semanais de 2012
    - `MÉDIA` do tamanho da loja
    
    **Passo 2**: Crie o campo calculado
    
    - Clique em: **Valores → Adicionar campo → Campo calculado**
    - Dê um nome ao campo, por exemplo: **`vendasxmetro2`.**
    
    Inglês
    
    ```
    =SUM(vendas_semanais) / MÉDIA(tamanho)
    
    ```
    
    Português
    
    ```
    =SOMA(vendas_semanais) / MÉDIA(tamanho)
    ```
    
    **Configuração importante**
    
    - No painel lateral da tabela dinâmica:
        - encontre o novo campo calculado;
        - altere a opção **Resumir por** para:
        
        > **Personalizado** (*Custom*)
        > 
    
    **Passo 3**: Filtre apenas o ano de 2012
    
    - Adicione um filtro. Mostre apenas linhas onde:
    
    > `semana_limpa` contém `2012`
    > 
    
    **Resultado esperado: Tabela dinâmica com 4 colunas:**
    
    Exemplo:
    
    | nome_dept | SOMA de vendas_semanais | MÉDIA de tamanho | vendas_por_m2 |
    | --- | --- | --- | --- |
    | Mercearia e Básicos | 85.052.985,90 | 130.287,6 | 652,8 |
    | departamento 2 | valor | valor | valor |
    | departamento 3 | valor | valor | valor |
2. **KPI 2: Participação por departamento**
    - Crie uma tabela dinâmica com:
        - soma das vendas semanais por departamento em 2012;
        - exibindo os valores como:
            
            > `% do total geral`
            > 
    - Use:
        
        > `SOMA(vendas_semanais)`
        > 
    - Depois altere:
        
        > **Mostrar como → % do total geral**
        > 
    - Assim como no KPI anterior, aplique filtro para mostrar apenas vendas de 2012
    
    **Resultado esperado:** Tabela dinâmica com 2 colunas.
    
    Exemplo:
    
    | nome_dept | SOMA de vendas_semanais |
    | --- | --- |
    | Mercearia e Básicos | 15,23% |
    | Alimentos Frescos | 10,66% |

---

#### Parte 4: Dashboard (20–30 min)

**Aba: `Dashboard`**

**O que você deve fazer**: Construir um dashboard interativo.

**Por quê**: O dashboard será a área onde diferentes stakeholders poderão:

- filtrar departamentos,
- visualizar KPIs automaticamente,
- e analisar os resultados em tempo real.

##### 4.1 Criar a célula de seleção (entrada do usuário)

1. Na aba `Dashboard`, escolha uma célula. Exemplo: `B2`
2. Crie um menu suspenso com os nomes dos departamentos.
- **Como criar o dropdown:**
    - Menu: Dados → Validação de dados
    - Em **Critérios**: selecione a coluna contendo os nomes dos departamentos
        
        > Exemplo: `raw_departments!B2:B15`
        > 
    - Agora, a célula `B2` permitirá selecionar qualquer departamento.

##### 4.2 Fórmulas para trazer os KPIs ao dashboard

Na aba `Dashboard`, use: `VLOOKUP`/ `PROCV` para conectar o departamento selecionado aos KPIs das tabelas dinâmicas.

1. Vendas por metro quadrado
    - Crie uma fórmula que procure o nome do departamento selecionado em `B2`; busque esse valor na Pivot de vendas por metro quadrado; retorne o valor da coluna: `vendasxmetro2`
2. Participação do departamento
    - Crie uma fórmula que procure o departamento selecionado em `B2`; busque esse valor na Pivot de participação; retorne a coluna: `SOMA de vendas_semanais`

**Funções úteis:**

Inglês

`=VLOOKUP(valor_procurado; matriz_tabela; número_índice_coluna; FALSO))`

Português

`=PROCV(valor_procurado; matriz_tabela; número_índice_coluna; FALSO))`

##### 4.3 Formatação dos KPIs

1. Utilize **formatação condicional** para destacar valores importantes.

**Exemplo**

- participação menor que `5%` → vermelho
- valores altos → verde
- desempenho médio → amarelo

##### 4.4 Visualização dos KPIs

**KPI 1: Vendas por metro quadrado**

- Crie um **gráfico de barras** que mostre as *vendas/m²* por departamento.
- Dica: ordene a tabela dinâmica do maior para o menor para que as barras apareçam nessa ordem e destaquem os departamentos mais eficientes.

---

**KPI 2: Participação do Departamento**

- Crie um **gráfico de barras empilhadas** que mostre a proporção de cada departamento sobre o total de vendas.
- Cada departamento deve ter uma cor diferente.
- Assim, será possível visualizar não apenas a participação individual, mas também a comparação entre os departamentos.

O resultado final deve ser semelhante ao exemplo abaixo:

!image.png

---

#### 🎨 Dicas de design para dashboards no Google Sheets

1. **Estrutura clara (layout)**

- Divida a planilha em **três áreas principais**:
    - 🟦 Superior → título e filtro de seleção (por exemplo: menu suspenso de departamento).
    - 🟩 Central → KPIs principais em “cartões” grandes.
    - 🟨 Inferior → gráficos de apoio (tendências semanais, comparações) *(opcional)*.

Use: bordas suaves, caixas sombreadas e espaçamento consistente para separar visualmente cada seção.

---

**2. Cartões de KPI**

- Cada KPI deve ficar em seu próprio bloco, contendo:
    - título em **negrito e cinza escuro (**Exemplo: *Vendas por metro quadrado)*
    - valor em **fonte grande (18–24 pt)**;
    - cor de destaque;
    - fundo suave (cinza claro, azul claro ou verde claro).

---

**3. Cores com propósito**

- Evite usar muitas cores 🎨. Prefira uma paleta consistente de 2–3 cores.
- Sugestão:

| Cor | Uso |
| --- | --- |
| Azul | métricas neutras/positivas |
| Verde | crescimento/desempenho forte |
| Vermelho | alertas ou baixo desempenho |

1. **Remova excesso visual**

Elimine:

- linhas extras,
- colunas vazias,
- grades desnecessárias,
- elementos que não ajudam na leitura.

**Resultado esperado**

Quando o usuário selecionar: **“Snacks & Bebidas”** no menu suspenso, o dashboard deverá atualizar automaticamente:

| KPI | Valor esperado |
| --- | --- |
| Vendas por metro quadrado | R$ 272,06 |
| Participação do departamento | 6,35% |

Tudo conectado às tabelas dinâmicas previamente calculadas.

---

#### Parte 5: Resumo Executivo (C → F → I) (20–30 min)

**Aba: `Resumo`**

**O que fazer**: Produzir um resumo executivo curto e acionável que responda às 4 perguntas de negócio usando o método **Context → Finding → Implication (C→F→I).** Cada resposta deve incluir a **evidência visual** (gráfico ou tabela) que a sustenta.

##### O que entregar na aba `Resumo`

Exemplo de linha (modelo real de entrega)

- **Pergunta:** P1 — Quais foram as lojas mais eficientes de 2010?
- **KPI:** vendas por metro quadrado.
- **Contexto:** Vendas de 2010, todos os departamentos, todas as semanas.
- **Insight:** As lojas XXX apresentam vendas por metro quadrado = R$ XXXXX (top 25% em comparação com as demais).
- **Implicação:** Priorizar estoque e orçamento para a loja XXX.

---

#### Parte 6: QA (Quality Assurance)

**Aba: `README`**

**O que fazer:** Documentar o projeto e verificar integridade dos dados, exatidão dos cálculos, e funcionamento do dashboard.

Documente: verificações realizadas, resultados encontrados e ações tomadas.

**Por que**: Para que qualquer colega consiga entender o conteúdo do arquivo, como ele foi construído, e quais validações foram aplicadas.

#### O que entregar na aba `README`

- **Descrever o objetivo geral do arquivo**
    - Escreva uma frase curta explicando: o que está sendo analisado e para que o dashboard serve.
- **Listar todas as abas do arquivo**
    - Complete a tabela incluindo as abas faltantes: `Pivot` , `Dashboard`  e `Resumo`
- **Documentar os KPIs**
    - Complete a documentação do KPI 2 — Participação percentual do departamento
- **Definir validações de QA**
    - Verificações obrigatórias:
        - Existem lojas sem departamento atribuído?
        - Existem vendas negativas ou nulas?
        - Existem tamanhos em m² com valor 0?
    - Aplique as validações na tabela `clean_vendas`.

---

#### Lista de verificação para entrega (para envio)

- Planilha Google Sheets com as abas obrigatórias:
    - **`README`** completo (objetivo, tabelas, KPIs, validações de QA e observações adicionais).
    - **`Resumo`** com resposta para cada pergunta de negócio e a recomendação (implicação).
    - **`Dashboard`** com filtro por departamento, 2 KPIs dinâmicos (ou seja, atualizados conforme o departamento selecionado) e um gráfico para cada KPI.
    - **`Pivot`** com os cálculos dos 2 KPIs para o período de 2012 agrupados por departamento.
    - **`clean_vendas`** com as colunas integradas/enriquecidas.
    - **`raw_vendas`**, **`raw_departamento`** e **`raw_lojas`**.

---

#### Reflexão final

Ao concluir este projeto, você terá:

- Importado e enriquecido dados (`Raw` → `Clean`);
- Construído agregações (`Pivot`);
- Criado visualizações úteis (`Dashboard`);
- Comunicado insights executivos (`Resumo C→F→I`).

Este projeto integra as habilidades essenciais de um analista de dados: limpeza de dados, construção de KPIs, visualização e comunicação executiva.

---
## Rubrica

| Parte | Critério | ✅ Concluído | 🟡 Recomendação | ❌ Não concluído |
| --- | --- | --- | --- | --- |
| **Parte 1: Configuração do projeto** | Renomeou e criou todas as abas obrigatórias? (`raw_vendas`, `raw_lojas`, `raw_departamento`, `clean_vendas`, `Pivot`, `Dashboard`, `Resumo`, `README`) | Todas as abas estão presentes e corretamente nomeadas. | Faltam 1–2 abas ou existem pequenos erros nos nomes. | Várias abas estão ausentes ou incorretamente nomeadas. |
| **Parte 2: Limpeza sistemática** | Normalizou as colunas em `clean_vendas`? (`loja`, `departamento`, `data`, `vendas_semanais`, `eh_feriado`, `semana_limpa`) | Todas as colunas limpas e com formato correto. | Algumas colunas corretas, mas faltam pequenas padronizações. | As colunas continuam desorganizadas ou com formatos inconsistentes. |
| **Parte 2: Limpeza sistemática** | Uniu corretamente as informações de lojas e departamentos em `clean_vendas`? | Colunas `tipo`, `tamanho`, `nome_departamento` adicionadas corretamente com XLOOKUP/PROCX. | As junções foram feitas, mas com erros pontuais ou incompletas. | Os dados de `raw_lojas` ou `raw_departamento` não foram integrados. |
| **Parte 2: Limpeza sistemática** | Tratamento adequado de valores ausentes ou anômalos? | Valores ausentes corrigidos com critérios claros; valores extremos documentados. | Alguns valores tratados, mas faltam justificativas ou consistência. | Valores ausentes e extremos não foram tratados. |
| **Parte 3: Pivots / KPIs** | Calculou o KPI 1 — Vendas por metro quadrado? | Campo calculado correto, usando vendas e tamanho da loja. | Fórmula presente, mas com pequenos erros. | KPI não calculado ou fórmula incorreta. |
| **Parte 3: Pivots / KPIs** | Calculou o KPI 2 — Participação do departamento? | Tabela dinâmica com % do total de vendas. | Cálculo presente, mas com erros de formatação ou percentual incorreto. | KPI ausente ou implementado incorretamente. |
| **Parte 3: Pivots / KPIs** | Calculou o KPI 3 — Volatilidade (CV)? | Campo calculado = DESVPAD/MÉDIA correto e validado. | Cálculo presente, mas com erros de fórmula ou interpretação. | KPI ausente ou mal estruturado. |
| **Parte 4: Dashboard** | Incluiu um menu suspenso por departamento e KPIs dinâmicos? | O filtro funciona e os 3 KPIs mudam corretamente. | Menu presente, mas com erros na atualização dos KPIs. | Não existe menu suspenso ou os KPIs são estáticos. |
| **Parte 4: Dashboard** | Incluiu pelo menos 3 visualizações relevantes (uma para cada KPI)? | Gráficos claros, bem formatados e alinhados às perguntas de negócio. | Gráficos presentes, mas com problemas de formatação ou pouca clareza. | Gráficos ausentes ou irrelevantes. |
| **Parte 5: Resumo executivo** | Respondeu às perguntas usando o método C→F→I? | Cada insight possui contexto, descoberta e recomendação clara. | Respostas parciais ou com contexto incompleto. | Resumo ausente ou sem estrutura C→F→I. |
| **Parte 5: Resumo executivo** | Documentou os KPIs com fórmulas e interpretação? | Todos os KPIs explicados com clareza. | Explicação parcial ou pouco clara. | KPIs não documentados. |
| **Parte 6: QA / Validação** | Completou a tabela de validações na aba `README`? | Todos os checks estão presentes com fórmulas e resultados claros. | Checks presentes, mas incompletos ou sem fórmulas. | Não existem validações documentadas. |
| **Parte 6: QA / Validação** | Foram identificadas limitações ou notas finais? | Limitações e premissas documentadas no `README`. | Notas presentes, mas superficiais. | Não há notas nem limitações documentadas. |
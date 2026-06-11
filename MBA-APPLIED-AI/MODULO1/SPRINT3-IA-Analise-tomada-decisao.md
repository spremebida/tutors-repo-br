# O projeto e a avaliação

> Esse projeto será avaliado com base em uma rúbrica. As rúbricas ficam disponíveis nas lições dos projetos, onde cada pessoa estudante consegue entender como será avaliado. Você usará esse material para avaliar!

> A pessoa estudante vai entregar um link que deve conter:
**Entregável 1 — Registro de análise com IA** (`analise_processo.md`)
Documentação do processo completo: qual ferramenta foi usada em cada etapa, quais prompts foram enviados, quais outputs foram recebidos e como cada output foi validado antes de ser usado.

**Entregável 2 — Relatório executivo** (`relatorio_executivo.md`)
Uma página para o board. Gerado com IA, validado com a Matriz de Confiança e acompanhado de nota de confiança.

**Entregável 3 — Registro de custo** (`custo_analise.md`)
Estimativa documentada do custo de tokens de cada chamada de IA feita durante o projeto, com justificativa da escolha de modelo em cada etapa.

---

## Descrição do projeto
## Do Dado ao Relatório Executivo: Análise de Churn com IA

## Contexto

O Beta Bank está perdendo clientes. Mês a mês, a base diminui — e a liderança percebeu que reter um cliente custa menos do que conquistar um novo.

Você foi contratado para apoiar a análise desse problema. Sua entrega não é um modelo estatístico. É uma análise estruturada, conduzida com ferramentas de IA, que termina em um relatório que o board consegue ler, entender e usar para decidir.

Esse projeto integra tudo que você aprendeu na Sprint 3. Você vai escolher a ferramenta certa para cada etapa, construir prompts eficientes, estimar o custo de cada chamada, validar os outputs antes de usá-los e comunicar os resultados para três audiências diferentes.

## Os dados

O Beta Bank disponibilizou o seguinte relatório interno de análise da base de clientes. Esses são os dados com os quais você vai trabalhar — não há arquivo para baixar. Sua tarefa é usar esses dados como insumo para os prompts de IA em cada etapa da análise.

### Relatório interno — Base de clientes Beta Bank

**Período de referência:** janeiro a dezembro de 2024
**Data de extração:** 31/12/2024

**Visão geral da base**

Total de clientes ativos no período: 10.000
Clientes que encerraram o relacionamento no período: 2.080
Taxa de churn anual: 20,8%
Ticket médio mensal por cliente (receita de tarifas e produtos): €250
Custo médio de aquisição de novo cliente: €180
Receita total mensal da base ativa: €1.984.000

**Distribuição geográfica**

| País | Clientes | Taxa de churn |
| --- | --- | --- |
| França | 5.014 | 17,7% |
| Alemanha | 2.509 | 33,2% |
| Espanha | 2.477 | 14,6% |

**Distribuição por faixa etária**

| Faixa etária | Clientes | Taxa de churn |
| --- | --- | --- |
| 18–30 anos | 1.820 | 8,7% |
| 31–40 anos | 2.950 | 12,3% |
| 41–50 anos | 2.870 | 17,0% |
| 51–60 anos | 1.680 | 37,9% |
| Acima de 60 anos | 680 | 65,9% |

**Distribuição por número de produtos bancários**

| Produtos | Clientes | Taxa de churn |
| --- | --- | --- |
| 1 produto | 5.084 | 30,5% |
| 2 produtos | 4.590 | 5,2% |
| 3 produtos | 266 | 100,0% |
| 4 produtos | 60 | 100,0% |

**Distribuição por saldo da conta**

| Faixa de saldo | Clientes | Taxa de churn |
| --- | --- | --- |
| €0 (sem saldo) | 3.617 | 14,5% |
| €1 a €50.000 | 1.243 | 20,1% |
| €50.001 a €100.000 | 2.374 | 19,7% |
| Acima de €100.000 | 2.766 | 30,2% |

**Status de atividade**

| Status | Clientes | Taxa de churn |
| --- | --- | --- |
| Membro ativo | 5.151 | 8,9% |
| Membro inativo | 4.849 | 33,8% |

Membros inativos representam aproximadamente 79% do total de cancelamentos no período.

**Distribuição por gênero**

| Gênero | Clientes | Taxa de churn |
| --- | --- | --- |
| Feminino | 4.543 | 31,3% |
| Masculino | 5.457 | 12,3% |

**Pontuação de crédito — estatísticas descritivas**

Média: 650 pontos
Mediana: 652 pontos
Mínimo: 350 pontos / Máximo: 850 pontos
Clientes com score abaixo de 500: taxa de churn ligeiramente superior à média
Sem correlação forte identificada na análise descritiva isolada.

**Tempo de relacionamento com o banco**

| Tempo de relacionamento | Clientes | Taxa de churn |
| --- | --- | --- |
| Menos de 1 ano | 1.080 | 20,9% |
| 1 a 3 anos | 2.940 | 21,1% |
| 4 a 6 anos | 3.120 | 20,6% |
| 7 a 10 anos | 2.860 | 20,3% |

Sem variação significativa de churn por tempo de relacionamento.

**Salário estimado — estatísticas descritivas**

Média: €100.090
Mediana: €100.194
Distribuição uniforme entre €11.580 e €199.992
Sem correlação significativa com a taxa de churn identificada na análise descritiva.

**Cruzamento de variáveis — perfis de maior risco**

Clientes com as três condições simultaneamente (acima de 50 anos + saldo acima de €100.000 + membro inativo): 487 clientes, taxa de churn estimada em torno de 70%.

Clientes com 1 produto + membro inativo: 2.218 clientes, taxa de churn de aproximadamente 45%.

Clientes na Alemanha + acima de 50 anos: 412 clientes, taxa de churn superior a 55%.

**Meta do projeto:** com base nesses dados, identificar o perfil dos clientes com maior risco de churn, estimar o impacto financeiro para o banco e recomendar uma ação específica para o board aprovar.

**Como usar os dados**

O arquivo `Churn_BetaBank.csv` está disponível para download junto com este enunciado. Ele contém os 10.000 registros individuais de clientes com todas as variáveis descritas acima.

Você não precisa processar o CSV com código. Use-o como insumo para os prompts de IA: cole uma amostra das primeiras linhas para dar ao modelo a estrutura real dos dados, ou use as estatísticas do relatório interno acima diretamente nos seus prompts. Os dois caminhos são válidos — o que será avaliado é a qualidade da análise e dos prompts, não a forma como os dados foram fornecidos à ferramenta.

Se quiser colar uma amostra no prompt, as primeiras 5 a 10 linhas do CSV são suficientes para contextualizar a estrutura. Adicione junto as estatísticas agregadas do relatório para que o modelo entenda os padrões da base completa, não apenas dos registros individuais.

Arquivo: Churn_BetaBank.csv

## O que você vai entregar

**Entregável 1 — Registro de análise com IA** (`analise_processo.md`)
Documentação do processo completo: qual ferramenta foi usada em cada etapa, quais prompts foram enviados, quais outputs foram recebidos e como cada output foi validado antes de ser usado.

**Entregável 2 — Relatório executivo** (`relatorio_executivo.md`)
Uma página para o board. Gerado com IA, validado com a Matriz de Confiança e acompanhado de nota de confiança.

**Entregável 3 — Registro de custo** (`custo_analise.md`)
Estimativa documentada do custo de tokens de cada chamada de IA feita durante o projeto, com justificativa da escolha de modelo em cada etapa.

## Critérios de avaliação

O projeto será avaliado em quatro dimensões.

**Processo de análise:** o problema de negócio foi formulado corretamente? A ferramenta foi escolhida com critério para cada etapa? Os prompts seguiram os quatro pilares (Persona, Contexto, Objetivo, Formato)?

**Validação crítica:** os outputs foram validados antes de serem usados? Qual técnica da Matriz de Confiança foi aplicada e por quê? Existe pelo menos um exemplo documentado de output questionado e corrigido?

**Custo:** o custo foi estimado antes de cada chamada? A escolha do modelo foi justificada com base na complexidade da tarefa? A tabela de custo está preenchida corretamente?

**Comunicação:** o relatório executivo segue os seis elementos universais? Está adequado para a audiência do board? Inclui nota de confiança com as limitações da análise?

## Instruções

### Etapa 1 — Formulação do problema

Antes de abrir qualquer ferramenta de IA, escreva com suas próprias palavras:

Qual é o problema de negócio que o Beta Bank precisa resolver? O que uma análise bem-sucedida vai entregar? Quais perguntas os dados precisam responder?

Essa etapa existe por uma razão direta: IA sem direção gera análise sem propósito. O profissional que define o problema antes de abrir o chat entrega um resultado diferente do que cola os dados e espera que a ferramenta descubra o que importa.

Registre suas respostas no `analise_processo.md`. Não precisa ser longo — três parágrafos são suficientes.

### Etapa 2 — Exploração dos dados com IA

Com o problema formulado, escolha a ferramenta para a exploração inicial e justifique a escolha no seu registro.

Use o perfil de dados fornecido para construir um prompt de EDA seguindo os quatro pilares. O prompt deve pedir ao modelo que identifique os padrões mais relevantes nos dados, aponte quais variáveis têm maior relação com o churn e levante hipóteses sobre o comportamento dos segmentos de maior risco.

**Prompt de referência — adapte com suas próprias escolhas:**

`Você é um cientista de dados sênior especializado em
análise de risco de retenção no setor bancário.

Tenho um dataset com 10.000 clientes do Beta Bank.
A taxa de churn atual é de 20,4%. Os dados disponíveis
por cliente incluem: pontuação de crédito, país de
residência, gênero, idade, tempo de relacionamento,
saldo da conta, número de produtos bancários, posse
de cartão de crédito, status de atividade e salário
estimado.

Informações já identificadas:
- Clientes com mais de 50 anos e saldo acima de
  €100.000 têm churn 2,3x maior que a média
- Clientes com apenas 1 produto têm 40% mais
  probabilidade de sair nos próximos 90 dias
- Membros inativos representam 63% dos cancelamentos

Com base nesses dados, realize uma análise exploratória.
Identifique os três segmentos de maior risco de churn,
as variáveis com maior poder preditivo e as hipóteses
que explicam o comportamento de cada segmento.

Apresente o resultado em formato de relatório estruturado
com seções claras. Linguagem orientada a negócio,
não a estatística.`

Depois de receber o output, aplique o **Sanity Check**: o que foi gerado faz sentido dado o que você já sabe sobre o problema? Existe alguma afirmação que parece plausível mas contradiz os dados fornecidos?

Registre no `analise_processo.md`: o prompt enviado, o output recebido resumido e o resultado do Sanity Check — o que foi aceito, o que foi questionado e por quê.

### Etapa 3 — Aprofundamento por segmento

Com os segmentos de risco identificados, aprofunde a análise do segmento de maior prioridade. Use um prompt encadeado — não recomece do zero, continue a partir do output anterior.

O objetivo desta etapa é entender o perfil completo do segmento crítico e estimar o impacto financeiro do churn nesse grupo.

Para estimar o impacto financeiro, peça ao modelo que calcule com base nos seguintes parâmetros: ticket médio mensal de €250 por cliente, custo de aquisição de novo cliente de €180 e base atual do segmento crítico conforme identificado na etapa anterior.

Aplique o **Reverse Validation** no resultado: os números do impacto financeiro estão baseados nos dados que você forneceu ou o modelo introduziu valores que não estavam no contexto? Verifique cada número antes de usar no relatório.

Registre o prompt encadeado, o output e o resultado da validação.

### Etapa 4 — Registro de custo

Para cada chamada de IA realizada nas etapas anteriores, preencha a tabela abaixo no `custo_analise.md`.

| Etapa | Ferramenta | Modelo | Tokens entrada (est.) | Tokens saída (est.) | Custo (USD) | Justificativa do modelo |
| --- | --- | --- | --- | --- | --- | --- |
| Formulação do problema |  |  |  |  |  |  |
| EDA e segmentação |  |  |  |  |  |  |
| Aprofundamento por segmento |  |  |  |  |  |  |
| Geração do relatório executivo |  |  |  |  |  |  |
| **Total** |  |  |  |  |  |  |

**Como estimar:** use a proporção de 600 palavras por 1.000 tokens para texto em português. Prompts longos com contexto detalhado tendem a ter 800 a 1.500 tokens de entrada. Respostas analíticas completas tendem a ter 500 a 1.000 tokens de saída.

**Pergunta de reflexão obrigatória:** com base nos custos registrados, qual seria o custo mensal se essa análise fosse repetida semanalmente para monitorar o churn da base? O modelo escolhido se justifica para todas as etapas ou seria possível usar um modelo mais econômico em alguma delas sem perda de qualidade?

Registre sua resposta no `custo_analise.md`. Não existe resposta certa — o que é avaliado é o raciocínio.

### Etapa 5 — Relatório executivo

Esta é a entrega de maior visibilidade do projeto. O relatório vai para o board do Beta Bank. A audiência não quer metodologia, não quer termos técnicos e não quer listas de variáveis. Quer saber o que está acontecendo, por que importa e o que precisa ser decidido.

**Passo 1 — Gere o rascunho**

Use o prompt abaixo no Claude, substituindo os campos entre colchetes pelos seus resultados reais das etapas anteriores:

`Você é um especialista em comunicação executiva com
experiência no setor bancário.

Com base nos dados abaixo, gere o rascunho de um
relatório executivo de uma página para ser apresentado
ao board do Beta Bank.

Estrutura obrigatória:
1. Situação atual (o que os dados revelam)
2. O que descobrimos (perfil do cliente em risco)
3. Impacto financeiro (estimativa concreta)
4. Recomendação (ação específica e viável)
5. Decisão necessária do board

Dados da análise:
- Taxa de churn atual: 20,4%
- Segmento de maior risco identificado: [seu resultado]
- Principal fator preditivo: [seu resultado]
- Impacto financeiro estimado: [seu resultado]
- Ação recomendada: [sua hipótese]

Tom: direto, sem jargão técnico, máximo uma página.
Comece pela conclusão, não pela metodologia.
Inclua pelo menos uma limitação da análise.`

**Passo 2 — Valide com a Matriz de Confiança**

Para cada afirmação do rascunho, posicione-a na matriz. Afirmações sobre impacto financeiro caem no Quadrante 3 (alto risco, alta verificabilidade) — recalcule os números de forma independente antes de incluir no documento final. Afirmações sobre o perfil do segmento de risco caem no Quadrante 4 (alto risco, baixa verificabilidade) — triangule com os dados originais fornecidos no enunciado antes de afirmar com certeza.

Documente no `analise_processo.md` quais afirmações foram verificadas, como foram verificadas e se alguma foi alterada após a validação.

**Passo 3 — Adicione a nota de confiança**

`Nota metodológica: este relatório foi estruturado com
suporte de IA generativa a partir dos dados resumidos
fornecidos pelo Beta Bank. As estimativas de impacto
financeiro são projeções baseadas no ticket médio e
custo de aquisição informados — devem ser tratadas
como indicativas e validadas contra os dados reais
do sistema financeiro antes de embasar decisões de
orçamento. A análise foi conduzida sobre um resumo
estatístico da base, não sobre os dados individuais
dos clientes.`

### Etapa 6 — Adaptação para três audiências

O relatório executivo está pronto para o board. Agora adapte o mesmo insight para mais duas audiências, com no máximo um parágrafo cada.

**Versão para o gerente de relacionamento:** a pessoa que vai operacionalizar a ação recomendada. Precisa entender o que fazer, com quais clientes e qual resultado esperar.

**Versão para a equipe de dados:** as pessoas que vão monitorar o churn mensalmente. Precisam entender quais variáveis acompanhar, qual métrica sinaliza deterioração e o que dispara um alerta.

Registre as três versões no `relatorio_executivo.md` com os cabeçalhos: "Para o board", "Para o gerente de relacionamento" e "Para a equipe de dados".

## Estrutura de entrega

`projeto_sprint3/
│
├── analise_processo.md     # Registro do processo completo
├── relatorio_executivo.md  # Relatório para o board + 3 versões
└── custo_analise.md        # Tabela de custo + reflexão`

## Checklist de revisão

**Processo de análise**

- [ ]  Problema de negócio formulado antes de abrir qualquer ferramenta
- [ ]  Justificativa de escolha de ferramenta registrada para cada etapa
- [ ]  Prompts seguem os quatro pilares (Persona / Contexto / Objetivo / Formato)
- [ ]  Prompt encadeado usado na etapa de aprofundamento

**Validação crítica**

- [ ]  Sanity Check aplicado e documentado na EDA
- [ ]  Reverse Validation aplicado nos números de impacto financeiro
- [ ]  Matriz de Confiança usada na revisão do relatório executivo
- [ ]  Pelo menos uma afirmação questionada e corrigida está documentada

**Custo**

- [ ]  Tabela de custo preenchida para todas as etapas
- [ ]  Justificativa de modelo registrada para cada chamada
- [ ]  Pergunta de reflexão respondida com raciocínio explícito

**Relatório executivo**

- [ ]  Segue os seis elementos universais
- [ ]  Máximo uma página, linguagem executiva
- [ ]  Começa pela conclusão, não pela metodologia
- [ ]  Inclui pelo menos uma limitação da análise
- [ ]  Nota de confiança presente com ressalvas reais
- [ ]  Três versões produzidas (board / gerente / equipe de dados)

## Critério de aprovação

O projeto será aprovado quando os três entregáveis estiverem completos e o relatório executivo estiver estruturado com os seis elementos, validado com a Matriz de Confiança e acompanhado de nota de confiança.

Um processo bem documentado sem relatório adequado não é uma entrega completa. Um relatório bem escrito sem registro de validação também não é. Os três entregáveis precisam estar presentes.

O Beta Bank não vai tomar uma decisão com base em qual ferramenta você usou. Vai tomar uma decisão com base no que você comunicar — e em quanto você confia no que está comunicando.

Esse projeto existe para construir os dois.

### Saiba mais sobre o processo de revisão 📌

---
| **Critério** | **Excelente** 🟢
**9–10** | **Bom** 🟡
**7–8** | **Precisa Melhorar** 🟠
**5–6** | **Ausente** 🔴
**0–4**  |
| --- | --- | --- | --- | --- |
| **Processo de análise** | Problema de negócio formulado antes de abrir qualquer ferramenta. Prompts seguem os 4 pilares em todas as etapas. Prompt encadeado usado no aprofundamento. | Problema formulado de forma genérica. Prompts com a maioria dos pilares, com lacunas em um ou dois. | Problema não formulado separadamente. Prompts sem estrutura clara. | Nenhum registro de processo. Prompts ausentes ou colados sem análise. |
| **Validação crítica** | Sanity Check documentado com pelo menos uma afirmação questionada e desfecho registrado. Reverse Validation aplicado nos números financeiros. Matriz de Confiança usada com registro de alterações. | Validação aplicada mas com documentação superficial. Nenhuma afirmação efetivamente corrigida. | Validação mencionada mas sem evidência de output questionado. | Nenhuma validação crítica aplicada. |
| **Relatório executivo** | Segue os 6 elementos, em uma página, começa pela conclusão, nota de confiança com ressalvas reais, linguagem executiva. Três versões produzidas (board / gerente / equipe de dados). | Relatório estruturado com pequenas lacunas. Não começa pela conclusão ou falta nota de confiança. Versões com variação de qualidade. | Fora dos 6 elementos ou com linguagem técnica. Apenas uma ou duas versões produzidas. | Relatório ausente ou ilegível para o board. |
| **Custo** | Tabela de custo preenchida para todas as etapas com justificativa de modelo específica. Reflexão sobre custo mensal respondida com raciocínio explícito. | Tabela preenchida mas justificativas repetitivas ou pouco específicas. | Tabela incompleta ou reflexão ausente. | Nenhuma tabela de custo. |
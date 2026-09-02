# Nota do Tutor — Exemplo Excelente (Sprint 8)

**Nota final: 97/100 — Aprovado**

| Critério | Nota | Justificativa |
|---|---|---|
| 1. Ferramentas externas e memória | 20/20 | Tool testada de verdade (incluindo teste de falha proposital), memória com regra clara de expiração e decisão explícita do que guardar/não guardar. |
| 2. Auditoria de credenciais | 20/20 | Escopo restrito com justificativa explícita, e ainda testou tentando burlar o escopo pra confirmar que a restrição funciona. Vai além do mínimo esperado. |
| 3. Lógica de decisão | 20/20 | Cobre os três casos com ordem justificada e testada (inverteu de propósito pra provar o erro). Padrão exemplar de evidência. |
| 4. Guardrails, aprovação humana e fallback | 19/20 | Aprovação humana no lugar certo, fallback testado com simulação de falha real. Pequena perda por não detalhar quanto tempo o colaborador espera até a aprovação do gestor. |
| 5. Apresentação executiva | 18/20 | Responde as três perguntas com clareza para público não técnico, com estimativa de custo razoável e comparação de valor (tempo economizado vs. custo de operar). Pequena perda pela estimativa de custo não vir com a fonte do cálculo (quantos tokens, qual preço por token). |

**O que destacar para o aluno:** o tratamento do caso de borda "colaborador mora a exatamente 100km" (arquivo 05) é o ponto mais forte — em vez de o aluno decidir arbitrariamente uma interpretação, ele reconheceu a ambiguidade da política e programou o agente para escalar, em vez de assumir uma regra que não estava escrita. Isso é exatamente o tipo de julgamento que separa um bom desenho de agente de um automático demais.

**O que faltou para 100:** detalhamento da fonte da estimativa de custo (arquivo 06) e SLA de tempo de resposta do gestor no fluxo de aprovação (arquivo 04).

# Etapa 5 — Teste, Avaliação e Documentação Operacional

**Cenários testados:** (1) colaborador novo, mora a 130km, sem exceção prévia — registrou corretamente. (2) colaborador com exceção já ativa perguntando de novo — não duplicou o registro. (3) caso de borda: colaborador mora a exatamente 100km — o agente escalou para o RH em vez de decidir sozinho, já que a política não deixa claro se "100km" é inclusive ou exclusive, e essa ambiguidade eu decidi tratar como caso de escalonamento, não de decisão automática.

**Métricas que vou acompanhar depois do lançamento:** taxa de sucesso no registro (linha realmente aparece na planilha), tempo de resposta do agente, e número de vezes que o agente precisou escalar por ambiguidade — se esse número for alto, é sinal de que a política interna precisa de mais clareza, não que o agente está mal configurado.

**Documentação para outra pessoa manter:** este documento e os anteriores (Etapas 1 a 4) cobrem tool conectada, credencial, lógica de decisão e guardrails o suficiente para outra pessoa dar manutenção sem depender de mim.

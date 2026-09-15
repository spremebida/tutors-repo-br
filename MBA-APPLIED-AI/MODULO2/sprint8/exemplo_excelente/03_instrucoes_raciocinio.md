# Etapa 3 — Instruções de Raciocínio Documentadas

**Lógica de decisão completa, cobrindo os três casos:**

1. **Se o colaborador já tem exceção registrada** (verificado primeiro, consultando a planilha): informar que já está ativa, não registrar de novo.
2. **Se não tem exceção e mora a mais de 100km:** registrar a solicitação via tool do Make e notificar o gestor.
3. **Se não tem exceção e mora a até 100km:** explicar que a condição não se aplica, não registrar nada.

**Por que essa ordem:** verificar duplicidade antes de verificar distância evita registrar duas vezes a mesma exceção para quem já tem uma ativa. Testei invertendo a ordem de propósito (verificando distância primeiro) e confirmei que isso realmente gerava um segundo registro indevido para um colaborador que já tinha exceção — por isso fixei a ordem correta.

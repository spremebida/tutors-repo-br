# Nota do Tutor — Exemplo Excelente (Sprint 7)

**Nota final: 96/100 — Aprovado**

| Critério | Nota | Justificativa |
|---|---|---|
| 1. Escolha e justificativa da tarefa | 20/20 | Cobre as quatro condições com dados concretos do próprio contexto (15-20 perguntas/semana, 1h30 semanais de impacto). Nada genérico. |
| 2. Qualidade e segurança da base | 19/20 | Os três crivos aplicados explicitamente, e a decisão de excluir a lista de exceções da base (guardrail na origem) é exatamente o padrão que o curso ensina. Ponto de atenção: não descreveu o processo de quem vai lembrar de reanexar a política se ela mudar. |
| 3. Instrução de sistema | 19/20 | Os quatro elementos claros e específicos para esse agente. Testou a fronteira do que não está coberto e documentou o resultado. Só faltou detalhar o formato exato da citação de regra na saída esperada. |
| 4. Guardrails e teste adversarial | 20/20 | Três tentativas diferentes, incluindo tentativa de override de instrução, todas documentadas com resultado. Exatamente o padrão esperado. |
| 5. Avaliação final honesta | 18/20 | Reporta uma falha real (recuperação ruim numa seção mal titulada) e a correção aplicada, não só sucesso. Pequena perda por não ter testado se a correção resolveu 100% ou só nos casos testados. |

**O que destacar para o aluno:** a decisão de tirar a lista de exceções da base antes mesmo de configurar qualquer guardrail (arquivo 02) é o ponto mais forte deste projeto. É a aplicação correta do princípio "guardrail na origem é mais forte que guardrail na instrução", que muitos alunos só aplicam depois de ver o problema, não antes.

**O que faltou para 100:** documentação de um plano simples de manutenção do documento (quem atualiza, quando) e evidência de reteste após a correção do título da seção.

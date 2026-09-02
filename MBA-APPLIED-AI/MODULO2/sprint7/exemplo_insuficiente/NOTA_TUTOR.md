# Nota do Tutor — Exemplo Insuficiente (Sprint 7)

**Nota final: 42/100 — Reprovado, retorna para revisão**
**⚠️ Critério eliminatório acionado: dado sensível (lista de exceções) colocado diretamente na base, sem nenhum tratamento, e nenhum teste adversarial foi feito.**

| Critério | Nota | Justificativa |
|---|---|---|
| 1. Escolha e justificativa da tarefa | 8/20 | Tarefa plausível, mas a justificativa não cobre nenhuma das quatro condições de forma explícita. Não há dado concreto (frequência, tempo economizado, nível de risco). Parece ter sido escrita depois de fazer o projeto, não antes de escolher a tarefa. |
| 2. Qualidade e segurança da base | 2/20 | **Problema grave:** a lista de nomes com exceção aprovada foi colocada na mesma base, dado sensível de outros colaboradores exposto sem nenhum tratamento. Essa é exatamente a falha que o exercício de guardrails da seção 7.6 foi desenhado pra evitar. |
| 3. Instrução de sistema | 6/20 | Cobre só uma versão solta de "Papel" e "Regra" implícita ("seja prestativo"). Não define Contexto nem Saída Esperada. Não há regra de admitir desconhecimento nem proibição explícita de revelar dado sensível — o que se conecta diretamente ao problema do critério 2. |
| 4. Guardrails e teste adversarial | 4/20 | Guardrails listados de forma genérica, sem nenhuma tentativa de teste adversarial documentada. "Testei perguntando algumas coisas" não é um teste adversarial, é uma checagem superficial de funcionamento básico. **Aciona o critério eliminatório do documento de rubrica.** |
| 5. Avaliação final honesta | 5/20 | Puramente promocional, sem nenhum ponto de melhoria ou falha identificada. Não responde de fato às três perguntas esperadas (o que funcionou, o que a base agregou, o que quebrou). |

**Ponto crítico para a devolutiva ao aluno:** o problema central deste projeto não é qualidade de escrita, é uma decisão de segurança de dado real (lista de exceções na base). Isso deveria ser a primeira coisa mencionada na devolutiva, antes de qualquer comentário sobre estilo ou profundidade de texto — é o tipo de erro que, em produção real, gera o mesmo tipo de problema que os cases reais da sprint descrevem (dado sensível saindo de onde não deveria).

**O que pedir para o aluno corrigir, em ordem de prioridade:**
1. Remover a lista de exceções da base imediatamente.
2. Reescrever a instrução de sistema cobrindo os quatro elementos, incluindo a regra de não revelar dado individual.
3. Rodar pelo menos duas tentativas de teste adversarial reais e documentar o resultado.
4. Refazer a avaliação final respondendo às três perguntas com honestidade, incluindo o que não funcionou.

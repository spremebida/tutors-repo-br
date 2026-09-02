# Nota do Tutor — Exemplo Insuficiente (Sprint 8)

**Nota final: 38/100 — Reprovado, retorna para revisão**
**⚠️ Critério eliminatório acionado no Sprint 7 correspondente deste aluno já indicava problema com dado sensível; aqui o problema se repete em credenciais (arquivo 02), padrão de negligência de segurança se mantém.**

| Critério | Nota | Justificativa |
|---|---|---|
| 1. Ferramentas externas e memória | 6/20 | Tool conectada, mas sem nenhum teste documentado (nem de sucesso, nem de falha). Memória configurada para guardar "o histórico completo de cada conversa", exatamente o erro apontado na seção 8.3.4: guardar mais do que a tarefa exige, sem regra de expiração nenhuma. |
| 2. Auditoria de credenciais | 2/20 | **Problema grave:** acesso total ao Drive inteiro do RH, justificado por conveniência futura ("assim não preciso reconfigurar depois"), o oposto exato do princípio do menor privilégio ensinado em 8.2.2. |
| 3. Lógica de decisão | 5/20 | Cobre só um dos três casos esperados (mora a mais de 100km). Não trata o caso de quem já tem exceção registrada (risco de duplicidade) nem o caso de quem mora a menos de 100km. |
| 4. Guardrails, aprovação humana e fallback | 4/20 | Não define nenhum ponto de aprovação humana novo para a ação de registrar (diferente da Sprint 7, que só informava). Não há fallback para falha de ferramenta. "Não precisei mudar nada" ignora que a etapa de ação nova (registrar) tem risco diferente de só informar. |
| 5. Apresentação executiva | 3/20 | Cheia de jargão técnico (RAG, API, arquitetura multi-step, prompt engineering) para uma audiência que o próprio enunciado define como não técnica. Não responde nenhuma das três perguntas obrigatórias: não diz que problema resolve em termos de negócio, não menciona risco controlado, não estima custo. |

**Ponto crítico para a devolutiva ao aluno:** o padrão de negligência de segurança se repete entre os dois projetos (dado sensível na Sprint 7, credencial de acesso total aqui). Vale conversar diretamente sobre isso como um padrão de comportamento a corrigir, não como dois erros isolados.

**O que pedir para o aluno corrigir, em ordem de prioridade:**
1. Restringir a credencial ao escopo mínimo necessário (arquivo 02).
2. Completar a lógica de decisão para os três casos, não só um (arquivo 03).
3. Definir um ponto de aprovação humana para a nova ação de registro, e um fallback de falha (arquivo 04).
4. Reescrever a apresentação executiva em linguagem de negócio, respondendo às três perguntas obrigatórias (arquivo 06).

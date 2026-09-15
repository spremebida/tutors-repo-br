# Rubrica de Avaliação — Projetos do Módulo 2 (Sprints 7 e 8)

Documento de referência para o tutor avaliar os dois projetos que fecham o Módulo 2: o projeto da Sprint 7 (7.7, agente simples com RAG e guardrails) e o projeto final da Sprint 8 (8.8, expansão desse mesmo agente com ferramentas, memória e operação).

## Como usar esta rubrica

- Cada projeto tem **5 critérios**, cada um valendo até **20 pontos**, total de **100 pontos**.
- Cada critério tem 4 níveis de desempenho, com a descrição do que caracteriza cada nível. Avalie critério por critério, não dê uma nota geral de impressão.
- **Nota mínima de aprovação: 70/100**, com o critério eliminatório abaixo.
- **Critério eliminatório:** independente da pontuação total, se o guardrail de dado sensível não foi testado de forma adversarial (nem no projeto da Sprint 7, nem na Etapa 4 do projeto da Sprint 8), o projeto retorna para revisão antes de qualquer nota final. Não é uma questão de nota, é uma questão de risco de segurança não verificado — o mesmo padrão que o curso ensina ao aluno se aplica à correção.
- Ao devolver feedback, aponte pelo menos um ponto forte e um ponto de melhoria por critério, mesmo nos projetos com nota alta. O objetivo da devolutiva não é só justificar a nota, é reforçar o hábito de auditoria que o curso constrói.

---

## Projeto da Sprint 7 (seção 7.7) — Agente com RAG e Guardrails

### Critério 1 — Escolha e justificativa da tarefa (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | A tarefa é real e recorrente do trabalho do aluno. A justificativa cobre as quatro condições de 7.4.1 (repetição, informação disponível, impacto, tolerância ao erro) com exemplos concretos do próprio contexto do aluno. |
| Satisfatório | 13-17 | Tarefa real, mas a justificativa cobre só parte das quatro condições, ou trata alguma delas de forma genérica. |
| Em desenvolvimento | 6-12 | Tarefa plausível, mas com sinais de ser adaptada ou simplificada para caber no exercício, não uma tarefa que o aluno de fato enfrenta. |
| Insuficiente | 0-5 | Tarefa fictícia, genérica, ou copiada de exemplo do curso sem adaptação real. |

### Critério 2 — Qualidade e segurança da base de conhecimento (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Base segue os três crivos de 7.3.5 (verdadeira, atualizada, com permissão de uso). Nenhum dado sensível não tratado. Documentos bem estruturados, com títulos que facilitam a recuperação. |
| Satisfatório | 13-17 | Base atende aos três crivos, mas a estruturação dos documentos é fraca (títulos vagos, informação pouco concentrada), prejudicando a precisão das respostas. |
| Em desenvolvimento | 6-12 | Base tem algum problema de atualidade ou permissão de uso, mas sem dado sensível exposto. |
| Insuficiente | 0-5 | Base contém dado sensível sem tratamento, ou informação claramente desatualizada/contraditória sem nenhum controle. |

### Critério 3 — Instrução de sistema (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Cobre os quatro elementos (Papel, Contexto, Regras, Saída Esperada) de forma específica para a tarefa escolhida. O agente demonstravelmente admite o que não sabe, em vez de alucinar. |
| Satisfatório | 13-17 | Cobre os quatro elementos, mas algum deles é genérico o suficiente para servir a qualquer agente, não esse especificamente. |
| Em desenvolvimento | 6-12 | Falta pelo menos um dos quatro elementos, ou a regra de "admitir desconhecimento" não está clara. |
| Insuficiente | 0-5 | Instrução vaga, sem estrutura reconhecível nos quatro elementos, ou o agente visivelmente alucina em teste simples. |

### Critério 4 — Guardrails e teste adversarial (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Cobre os três tipos (Ação, Escopo, Custo). Guardrail de dado sensível resolvido na origem (removido da base), não só na instrução. Teste adversarial documentado com pelo menos duas tentativas diferentes e o resultado de cada uma. |
| Satisfatório | 13-17 | Cobre os três tipos e testou adversarialmente, mas o guardrail de dado sensível depende só da instrução, sem reforço na origem. |
| Em desenvolvimento | 6-12 | Guardrails definidos, mas o teste adversarial é superficial (uma tentativa só, ou óbvia demais para revelar falha real). |
| Insuficiente | 0-5 | Sem teste adversarial documentado, ou guardrail falhou no teste e não foi corrigido antes da entrega. **Aciona o critério eliminatório.** |

### Critério 5 — Avaliação final honesta (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Responde com honestidade às três perguntas de 7.7.6, incluindo o que quebrou ou não funcionou como esperado, não só o que deu certo. |
| Satisfatório | 13-17 | Responde às três perguntas, mas com pouca profundidade sobre o que falhou, focando mais no sucesso. |
| Em desenvolvimento | 6-12 | Responde parcialmente, faltando uma das três perguntas ou tratando a avaliação de forma superficial. |
| Insuficiente | 0-5 | Avaliação ausente ou puramente promocional ("tudo funcionou perfeitamente"), sem nenhum ponto de melhoria identificado. |

---

## Projeto Final do Módulo 2 (seção 8.8) — Expansão do Agente

Este projeto expande o mesmo agente da Sprint 7. Se o projeto da Sprint 7 desse aluno já teve nota baixa nos critérios 2, 3 ou 4 acima, verifique se os mesmos problemas persistem aqui antes de avaliar os pontos abaixo.

### Critério 1 — Ferramentas externas e memória (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Conecta de fato uma ferramenta externa real (não simulada) e configura memória de longo prazo com regra clara de expiração/revisão, decidindo explicitamente o que guardar e o que não guardar. |
| Satisfatório | 13-17 | Ferramenta conectada de verdade, mas a configuração de memória não define regra de expiração, ou guarda mais do que a tarefa exige. |
| Em desenvolvimento | 6-12 | Ferramenta descrita mas não efetivamente conectada/testada (ex: print de configuração sem teste rodando), memória tratada superficialmente. |
| Insuficiente | 0-5 | Ferramenta e memória apenas mencionadas na instrução, sem nenhuma configuração real demonstrada. |

### Critério 2 — Auditoria de credenciais (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Credencial configurada com escopo mínimo necessário, com justificativa explícita de por que aquele é o escopo certo para a tarefa (não "porque pode ser útil"). |
| Satisfatório | 13-17 | Escopo razoavelmente restrito, mas a justificativa é vaga ou não menciona o princípio do menor privilégio explicitamente. |
| Em desenvolvimento | 6-12 | Escopo mais amplo do que a tarefa exige, sem justificativa clara do porquê. |
| Insuficiente | 0-5 | Credencial com acesso total ou não documentada, sem nenhuma auditoria demonstrada. |

### Critério 3 — Lógica de decisão (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Cobre todos os casos relevantes da tarefa, com ordem de verificação explícita e justificada (por que essa ordem evita um erro específico, como duplicidade). |
| Satisfatório | 13-17 | Cobre os casos principais, mas a ordem de verificação não é justificada, ou falta tratamento de um caso de borda. |
| Em desenvolvimento | 6-12 | Lógica de decisão incompleta, deixando pelo menos um caso relevante sem tratamento definido. |
| Insuficiente | 0-5 | Sem lógica de decisão estruturada, ou o agente decide de forma inconsistente em teste simples. |

### Critério 4 — Guardrails, aprovação humana e fallback (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Retoma os três tipos de guardrail e define claramente o ponto de aprovação humana, no lugar de maior risco da decisão. Fallback definido para quando uma ferramenta falha (não assume sucesso automático). |
| Satisfatório | 13-17 | Guardrails e aprovação humana definidos, mas o fallback de falha de ferramenta não está claro ou é genérico. |
| Em desenvolvimento | 6-12 | Aprovação humana posicionada no lugar errado (ex: antes de uma verificação que o próprio fluxo deveria resolver), ou fallback ausente. |
| Insuficiente | 0-5 | Sem ponto de aprovação humana definido em uma ação de risco real, ou sem teste do comportamento em caso de falha. **Aciona o critério eliminatório se envolver o guardrail de dado sensível.** |

### Critério 5 — Apresentação executiva (20 pts)

| Nível | Pontos | Descrição |
|---|---|---|
| Excelente | 18-20 | Responde com clareza, para público não técnico, às três perguntas: que problema resolve, que risco controla, quanto custa operar. Sem jargão técnico desnecessário. |
| Satisfatório | 13-17 | Responde às três perguntas, mas com linguagem técnica demais para o público-alvo, exigindo tradução. |
| Em desenvolvimento | 6-12 | Responde parcialmente, faltando uma das três perguntas (geralmente a de custo, que costuma ser omitida). |
| Insuficiente | 0-5 | Apresentação ausente, ou focada só em funcionalidades técnicas, sem tratar problema, risco ou custo. |

---

## Observações gerais para o tutor

- **Erro mais comum no critério de custo:** alunos tendem a pular a estimativa de custo por tarefa (Sprint 8, critério 5) porque não sabem calcular isso com precisão. Aceite uma estimativa aproximada e bem justificada — o objetivo é demonstrar que o aluno pensou sobre isso, não que acertou o valor exato.
- **Diferença entre "testado" e "descrito":** em vários critérios (guardrails, ferramentas, lógica de decisão), a diferença entre Satisfatório e Insuficiente costuma estar em o aluno ter *rodado* o teste (com print ou registro do resultado) ou só ter *descrito* o que deveria acontecer. Priorize evidência de execução real.
- **Projetos que reaprovam:** quando um projeto fica abaixo de 70 pontos ou aciona o critério eliminatório, a devolutiva deve apontar exatamente qual critério travou a aprovação e pedir a correção pontual daquele critério, não pedir que o aluno refaça o projeto inteiro.

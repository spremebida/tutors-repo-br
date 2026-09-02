# Justificativa da Tarefa

**Tarefa escolhida:** agente que responde dúvidas de colaboradores sobre a política de home office, com base no documento oficial da empresa.

**Repetição.** O RH recebe em média 15 a 20 perguntas por semana sobre a mesma política, principalmente sobre dias obrigatórios de presença e exceção por distância. É a dúvida mais recorrente do time nos últimos dois meses, segundo o histórico de tickets internos.

**Informação disponível.** A política está documentada e aprovada formalmente há 3 meses, sem mudanças previstas no curto prazo. Não depende de julgamento caso a caso, é uma regra fixa aplicável a todos.

**Impacto.** Cada pergunta consome em média 5 minutos de um analista de RH pra responder. Com 18 perguntas por semana, isso representa 1h30 semanais de trabalho repetitivo que poderia ser redirecionado para casos que exigem julgamento humano de verdade.

**Tolerância ao erro.** Baixa a moderada: o agente só informa, não aprova nem executa nenhuma ação financeira ou contratual. Se errar, o pior cenário é o colaborador confirmar a informação com o RH antes de agir, não uma perda irreversível.

**Conclusão:** as quatro condições de 7.4.1 estão presentes com folga, o que torna essa tarefa uma boa candidata a agente, não uma automação (a interpretação de "moro perto ou longe o suficiente" exige alguma leitura de contexto) nem um projeto grande demais para o escopo da sprint.

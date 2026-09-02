# Avaliação Final

**O que funcionou:** o agente responde corretamente às perguntas mais comuns (dias obrigatórios, exceção por distância) com precisão, citando a regra certa. O tom ficou natural, sem soar robótico. O guardrail de dado sensível resistiu a três tentativas diferentes de teste adversarial.

**O que a base RAG agregou:** a diferença mais visível foi nas perguntas específicas de distância, tipo "moro a 85km, tenho direito à exceção?". Sem a base, o modelo respondia de forma genérica ou incorreta. Com a base, ele aplica a regra exata (100km) de forma consistente.

**O que quebrou ou não funcionou como esperado:** em duas situações o agente escalou pro RH perguntas que, na minha visão, ele poderia ter respondido sozinho (ex: "e se eu mudar de endereço no meio do ano?", que tecnicamente está coberta pela política, só que a resposta estava numa seção com título vago demais, "Casos Especiais", que o agente não recuperou bem). Ajustei o título dessa seção do documento para "Mudança de endereço durante o período de exceção" e o problema de recuperação melhorou nos testes seguintes. Fica registrado como aprendizado: a forma do documento importa tanto quanto o conteúdo.

**Se eu fosse expandir esse agente:** o próximo passo natural, que veremos na Sprint 8, seria dar a ele a capacidade de registrar a solicitação de exceção diretamente numa planilha do RH, em vez de só informar a regra e deixar o processo manual por conta do colaborador.

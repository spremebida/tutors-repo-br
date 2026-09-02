# Etapa 1 — Redesenho do Fluxo com Ferramentas e Memória

**Ferramenta conectada:** Google Sheets via Make, ação "adicionar linha", para registrar solicitações de exceção diretamente na planilha compartilhada do RH (nome, data, justificativa).

**Teste real da integração:** rodei o cenário no Make três vezes com dados de exemplo diferentes e confirmei a linha aparecendo na planilha em tempo real, incluindo um teste de falha proposital (desconectando a credencial) para ver o comportamento de erro.

**Memória de longo prazo configurada:** o agente agora lembra se um colaborador já tem exceção registrada, consultando a mesma planilha antes de responder. Isso evita repetir a mesma pergunta em conversas futuras com o mesmo colaborador.

**O que decidi guardar:** nome do colaborador e status da exceção (tem/não tem).
**O que decidi não guardar:** qualquer comentário pessoal que o colaborador mencione durante a conversa, sem relação com a solicitação.
**Regra de expiração:** revisão trimestral da planilha para confirmar se as exceções continuam válidas (ex: colaborador pode ter mudado de endereço).

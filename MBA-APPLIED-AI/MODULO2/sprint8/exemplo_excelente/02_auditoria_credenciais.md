# Etapa 2 — Auditoria de Credenciais e Escopo Mínimo

**Credencial usada:** conexão Google Sheets configurada no Make, restrita à planilha específica de "Exceções Home Office", não à unidade de Drive inteira do RH.

**Justificativa do escopo:** a tarefa exige só ler e escrever nessa planilha específica. Testei a alternativa de dar acesso à pasta inteira do RH e decidi não usar, porque isso daria acesso a outras planilhas (folha de pagamento, avaliações) que esse agente nunca deveria tocar. Segue o princípio do menor privilégio de 8.2.2.

**O que perguntei ao time técnico:** confirmei que era possível restringir a permissão do Make a um arquivo específico do Drive, em vez do escopo padrão de "todos os arquivos", antes de configurar a conexão.

**Teste pós-configuração:** tentei (propositalmente) fazer o agente acessar outra planilha do mesmo Drive através de uma pergunta manipulada, e a tentativa falhou, confirmando que o escopo restrito está funcionando.

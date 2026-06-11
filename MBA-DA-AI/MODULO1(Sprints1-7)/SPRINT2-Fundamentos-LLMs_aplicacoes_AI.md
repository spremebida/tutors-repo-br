# O projeto e a avaliação

> Esse projeto será avaliado com base em uma rúbrica. As rúbricas ficam disponíveis nas lições dos projetos, onde cada pessoa estudante consegue entender como será avaliado. Você usará esse material para avaliar!

> A pessoa estudante vai entregar um link de apresentação que deve conter:

- [ ]  Breve explicação do cenário escolhido
- [ ]  Prints do processo de configuração (base de conhecimento e diretiva)
- [ ]  Prints de **pelo menos 5 conversas diferentes**
- [ ]  **Link público** do chatbot publicado

---

## Provejo - Criando um chatbot com o Zapier

Neste projeto, você irá **criar e publicar um chatbot funcional usando o Zapier**. O chatbot será projetado para ajudar usuários respondendo **perguntas frequentes (FAQs)** com base em uma **base de conhecimento fornecida**.

Você pode escolher **um dos dois cenários** abaixo:

1. **Assistente de hotel** — Um chatbot que ajuda hóspedes com perguntas comuns, como horário de check-in, comodidades e alterações de reserva.
2. **Chatbot de artigo acadêmico** — Um chatbot que responde perguntas com base no conteúdo de um artigo acadêmico escolhido por você.

> Para o cenário de hotel, fornecemos um arquivo PDF com perguntas frequentes:
>
> [Triple_Peaks_Hotel_FAQ.pdf](https://drive.google.com/file/d/1vpp49L-pjiTCxYOIl91cBSd6-mxS3sx3/view?usp=sharing)

Se você escolher o **artigo acadêmico**, será necessário fazer upload do PDF do artigo escolhido como fonte de conhecimento do chatbot. O bot deverá extrair informações relevantes e responder perguntas de forma útil e precisa.

## Requisitos do projeto

Seu chatbot deve:

- Ser criado usando **Zapier**
- Utilizar uma **fonte de conhecimento carregada** (PDF de FAQ do hotel ou PDF de artigo acadêmico)
- Fornecer respostas **claras, relevantes e corretas**, baseadas nos dados enviados
- Manter um **tom profissional e conversacional**
- Responder corretamente **pelo menos cinco perguntas diferentes**
- Incluir uma **mensagem de fallback** para perguntas fora do escopo da base de conhecimento

## Instruções do projeto

### 1. Criar uma conta no Zapier

Crie uma conta gratuita no [Zapier](https://zapier.com/) (se ainda não tiver) e acesse a seção **Chatbots** no painel principal.

### 2. Criar o chatbot

- Crie um chatbot do zero ou use um template disponível
- Dê um nome coerente com o cenário escolhido
    - Ex.: *“Assistente Hotel Bot”* ou *“Chatbot de Pesquisa Acadêmica”*
- Escreva uma **mensagem de boas-vindas profissional** para receber os usuários

### 3. Adicionar a base de conhecimento

No editor do chatbot, vá até **Knowledge Sources** e faça o upload do documento escolhido:

- Para o assistente de hotel: use o PDF de FAQ fornecido
- Para o chatbot acadêmico: envie o PDF do artigo selecionado

Confirme que o chatbot está configurado para **buscar respostas a partir desse conteúdo**.

### 4. Conectar a fonte de dados

- Clique em **Create Data Store**
- Selecione **Cloud Storage**
- Escolha o arquivo enviado
- Clique em **Create** e aguarde o processamento dos dados

### 5. Configurar o chatbot

- Use o **Directive Wizard** para definir o tom do bot
    
    *(útil, profissional e direto)*
    
- Configure uma **mensagem de fallback** para perguntas sem resposta
- Revise e refine as respostas para garantir alinhamento com o objetivo do chatbot

### 6. Publicar e documentar o chatbot

- Clique em **Share** para publicar o chatbot
- Copie o **link público** (ele será enviado junto com o projeto)
- Descreva o propósito do chatbot
- Tire **prints da configuração** e das **conversas de teste**


> ✅ O objetivo não é criar um chatbot perfeito, mas sim um **assistente prático, confiável e fácil de usar**, que responda claramente com base na sua base de conhecimento.


---

## Rubrica de avaliação

| **Critério** | **Excelente** 🟢 **9–10** | **Bom** 🟡 **7–8** | **Precisa Melhorar** 🟠 **5–6** | **Ausente** 🔴 **0–4** |
| --- | --- | --- | --- | --- |
| **Funcionalidade** | Responde corretamente com base no documento. As respostas refletem a intenção da pergunta. | Responde a maioria das perguntas corretamente, com pequenas imprecisões. | Respostas inconsistentes, vagas ou incompletas. | Chatbot não funciona ou respostas irrelevantes. |
| **Experiência do usuário** | Respostas claras, úteis, tom profissional e acolhedor. Boa mensagem inicial. | Tom geralmente adequado, mas com respostas genéricas ou estranhas. | Respostas confusas, robóticas ou tom inconsistente. | Sem tom definido ou mensagem inicial. |
| **Customização (diretiva + fallback)** | Diretiva clara e adequada ao cenário + fallback funcional e testado. | Diretiva e fallback presentes, mas genéricos. | Diretiva ou fallback incompletos. | Nenhuma diretiva ou fallback configurados. |
| **Testes e documentação** | 5 ou mais perguntas testadas com prints. Prints mostram upload, diretiva e configurações. | Maioria dos passos documentados, mas faltam 1–2 elementos. | Documentação incompleta ou poucos testes. | Sem prints, testes ou explicações. |
| **Publicação e envio** | Chatbot publicado, link funcional, nome correto e acesso configurado. | Publicado, mas com erro de nome ou acesso. | Link não funciona ou chatbot não publicado corretamente. | Nenhum chatbot enviado.
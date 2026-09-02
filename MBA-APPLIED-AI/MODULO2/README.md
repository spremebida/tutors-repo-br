# Repositório de Calibração — Projetos do Módulo 2

Este repositório existe para ajudar tutores a aplicar a rubrica de avaliação (`rubrica_avaliacao_projetos_modulo2.md`) de forma consistente entre si, usando exemplos completos e contrastantes em vez de só a descrição textual dos critérios.

## Estrutura

```
sprint7/
  exemplo_excelente/       — 96/100, aprovado
  exemplo_insuficiente/    — 42/100, reprovado (dado sensível exposto na base)
sprint8/
  exemplo_excelente/       — 97/100, aprovado
  exemplo_insuficiente/    — 38/100, reprovado (credencial com acesso total)
```

Cada pasta contém os arquivos que um aluno entregaria (numerados na ordem das etapas do projeto) e um `NOTA_TUTOR.md` com a pontuação critério por critério, explicando o raciocínio da nota.

## Como usar isso pra calibrar a equipe de tutores

1. Cada tutor novo lê os dois exemplos de uma sprint (excelente + insuficiente) **antes** de ver a nota do tutor, e tenta pontuar sozinho usando a rubrica.
2. Depois, compara a própria pontuação com o `NOTA_TUTOR.md` de referência.
3. Divergências maiores que 10 pontos num critério específico indicam que vale conversar sobre a interpretação daquele critério antes de começar a corrigir projetos de verdade.

## Continuidade entre os dois exemplos insuficientes

Os dois exemplos "insuficiente" (Sprint 7 e Sprint 8) foram desenhados como **o mesmo aluno hipotético**, mostrando como um padrão de negligência de segurança (dado sensível exposto na Sprint 7) se repete de forma diferente na Sprint 8 (credencial com acesso total). Isso é intencional: no NOTA_TUTOR.md da Sprint 8 há uma nota explícita sobre tratar isso como um padrão de comportamento na devolutiva, não como dois erros isolados. Serve de exemplo de como avaliar o projeto da Sprint 8 considerando o histórico do aluno na Sprint 7, não isoladamente.

## Observação sobre os exemplos "excelente"

Nenhum dos dois exemplos excelentes tira 100/100. Isso é proposital — mesmo bons projetos têm espaço de melhoria real, e a rubrica não deveria incentivar tutores a só darem nota máxima ou nota baixa. Os dois `NOTA_TUTOR.md` explicam exatamente o que faltou para a nota máxima, mesmo em projetos aprovados com folga.

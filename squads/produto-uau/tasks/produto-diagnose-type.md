# Produto Diagnose Type

```yaml
task:
  task_name: "Diagnosticar Tipo de Produto Ideal"
  status: pending
  responsible_executor: produto-chief
  execution_type: Agent
  estimated_time: "15-30 min"
  elicit: true

  input:
    - "Avatar (idealmente do avatar-ultra-profundo, Bloco 14 SCALE)"
    - "Mercado (L.U.C.R.O ou similar)"
    - "Expertise do aluno (em quê ele é referência ou tem resultado)"
    - "Recursos (tempo, dinheiro, time)"
    - "Canal principal (onde ele vai vender)"

  output:
    - "Tipo de produto recomendado (infoproduto, mentoria, SaaS, serviço, híbrido)"
    - "Rationale (por que esse tipo cabe)"
    - "Próximos passos (comandos sugeridos)"

  action_items:

    - step: 1
      name: "Coletar Contexto"
      description: |
        Perguntar ao aluno:
        1. Qual o avatar? (se saiu do avatar-ultra-profundo, carrega Bloco 14)
        2. Qual sua expertise / zona de gênio?
        3. Quanto tempo por semana você pode dedicar ao produto?
        4. Quanto investimento disponível? (pra entender se pode contratar time, pagar plataforma)
        5. Qual canal principal de venda? (Instagram orgânico, tráfego pago, lista de email)
        6. Quanto o avatar paga hoje por soluções parecidas? (referência de ticket)

    - step: 2
      name: "Mapear Restrições e Oportunidades"
      description: |
        Analisar:
        - **Tempo do criador**: pouco tempo → gravado ou SaaS. Muito tempo → mentoria.
        - **Escalabilidade necessária**: infoproduto / SaaS escala mais, serviço/mentoria menos
        - **Ticket desejado**: R$97-500 → infoproduto. R$500-2k → infoproduto+mentoria. R$2k-10k → mentoria. R$10k+ → mentoria high-ticket ou consultoria.
        - **Profundidade da dor**: dor superficial → infoproduto. Dor profunda → mentoria. Dor recorrente → SaaS.
        - **Expertise operacional**: se sabe fazer hands-on → serviço/done-with-you. Se só ensina → curso.

    - step: 3
      name: "Aplicar Matriz de Decisão"
      description: |
        Consultar `data/product-types-guide.md`. Matriz:

        | Tipo | Quando escolhe | Ticket típico | Tempo do criador | Escala |
        |------|----------------|---------------|------------------|--------|
        | Infoproduto | Dor superficial, ticket baixo-médio, conteúdo gravado | R$97-997 | Baixo (após criar) | Alta |
        | Mentoria | Dor profunda, ticket médio-alto, transformação | R$2k-20k | Alto | Baixa |
        | SaaS | Dor recorrente, problema de workflow, automação | R$47-997/mês | Médio (desenvolvimento) | Altíssima |
        | Serviço | Done-for-you, dor agora, cliente não quer aprender | R$5k-50k | Muito alto | Baixíssima |
        | Híbrido | Múltiplas dores, ticket alto, escala via alavancas | R$5k-50k | Médio-alto | Média |

    - step: 4
      name: "Recomendar Tipo + Rationale"
      description: |
        Escolher 1-2 tipos que cabem mais. Justificar em 1 parágrafo por quê.
        Apontar riscos da escolha.

    - step: 5
      name: "Sugerir Próximos Passos"
      description: |
        - Se tipo claro e aluno quer avançar, rodar `*create` (workflow 7 fases)
        - Se aluno tá na dúvida entre 2, fazer teste de viabilidade antes
        - Se avatar ou mercado ainda incompletos, mandar voltar pro avatar-ultra-profundo ou L.U.C.R.O

  output_example: |
    ## Diagnóstico, Tipo de Produto Ideal

    **Contexto coletado:**
    - Avatar, ex-funcionário 30-45 saturado, quer sair do emprego
    - Expertise, Meta Ads (10 anos de experiência hands-on)
    - Tempo, 15h/semana
    - Recursos, R$5k/mês pra contratar 1 pessoa
    - Canal, tráfego pago + Instagram autoridade
    - Ticket avatar paga hoje, R$500-2k pra outros cursos

    **Tipo recomendado, HÍBRIDO (Mentoria + Done-with-you)**

    **Rationale:**
    Avatar tem dor profunda (sair do emprego é transformação) mas também precisa de
    execução (não tem tempo de virar expert em tudo). Seu expertise é hands-on
    (Meta Ads), não só teórico. Com 15h/semana você consegue rodar mentoria em
    grupo + fazer campanhas junto. Ticket cabe entre R$3k-8k (entre mentoria pura
    e done-with-you puro). Categoria certa é "Aceleradora done-with-you" em vez
    de "curso" ou "mentoria só conversada".

    **Riscos:**
    - Não escala linear (teto ~30 alunos/trimestre)
    - Depende da sua presença (não pode ficar sem você operando)
    - Exige disciplina de processo (se não sistematiza, quebra)

    **Próximos passos:**
    1. Rodar `*create` (workflow 7 fases, Discovery → JTBD → ... → First Draft)
    2. Após First Draft, rodar `*feed-scale` pra exportar pacote pro S.C.A.L.E.
    3. S.C.A.L.E. transforma em oferta (preço, bônus, garantia)

  acceptance_criteria:
    - "Contexto completo coletado (6 perguntas)"
    - "Matriz de decisão aplicada"
    - "Tipo recomendado com rationale"
    - "Riscos apontados"
    - "Próximos passos claros"

  veto_conditions:
    - "Avatar não definido, VETO, mande pro avatar-ultra-profundo primeiro"
    - "Mercado não validado, VETO, mande pro L.U.C.R.O"
    - "Expertise genérica demais ('sou bom em marketing'), pedir especificação"

  handoff:
    on_complete: "Se tipo claro, rodar *create. Se dúvida, rodar teste de viabilidade"
    deliverable: "Recomendação de tipo de produto"
```

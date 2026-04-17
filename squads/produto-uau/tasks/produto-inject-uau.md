# Produto Inject UAU

```yaml
task:
  task_name: "Auditar 6 Injetores de UAU em Produto Existente"
  status: pending
  responsible_executor: produto-chief
  execution_type: Agent
  estimated_time: "30-60 min"
  elicit: true

  input:
    - "Nome do produto"
    - "Promessa principal"
    - "Módulos/entregáveis (lista completa)"
    - "Tempo de entrega"
    - "Formato (gravado, ao vivo, misto)"
    - "Concorrência direta (2-3 nomes)"
    - "Avatar-alvo (breve)"

  output:
    - "UAU Matrix preenchida (templates/uau-matrix-tmpl.md)"
    - "Para cada injetor, status (presente/ausente/fraco) + recomendação de injeção"
    - "Priorização de quais injetores adicionar primeiro"

  action_items:

    - step: 1
      name: "Coletar produto atual"
      description: |
        Perguntar ao aluno:
        1. Nome do produto
        2. Promessa (headline)
        3. Entregáveis (módulos, features, bônus)
        4. Tempo de entrega
        5. Formato
        6. Concorrência direta
        7. Avatar-alvo

    - step: 2
      name: "Auditar cada Injetor (6)"
      description: |
        Pra CADA injetor, avaliar presença (0-10) + apontar ausência.

        **Injetor 1, Mecanismo Único Oculto (Schwartz)**
        - Tem nome próprio? Tem ciência/lógica? Resolve dor oculta?
        - Se ausente, propor mecanismo com nome (rotear pra eugene-schwartz-produto se precisa)

        **Injetor 2, Entrega em Tempo 'Impossível' (Hormozi)**
        - Tempo de entrega é brutalmente menor que status quo?
        - Se não, propor quick win em 7 dias, modularização, done-for-you parcial

        **Injetor 3, Bônus Surpresa (Popeil/Hormozi)**
        - Tem algo que não foi prometido e vale mais que o core?
        - Nota, bônus pode ser feature do PRODUTO (ex, sessão extra), não só stacking de oferta
        - Se ausente, propor 1-2 bônus-produto

        **Injetor 4, Resultado Específico Garantido**
        - Cliente sai com COISA concreta pronta (primeira campanha, primeiro post, primeiro PDF)?
        - Se só "aprende", ausente. Propor entregável tangível.

        **Injetor 5, Formato Inesperado**
        - Produto é categorizado como 'curso' genérico?
        - Se sim, propor formato novo (aceleradora, fábrica, replicação assistida, imersão prática, etc)

        **Injetor 6, Anti-Método / Opportunity Switch (Brunson)**
        - Vende o contrário do senso comum?
        - Se não, propor inversão (rotear pra russell-brunson se precisa aprofundar)

    - step: 3
      name: "Priorizar injeções"
      description: |
        Rankear por IMPACTO × FACILIDADE:
        - Alto impacto + fácil, injetar agora
        - Alto impacto + difícil, injetar na próxima versão
        - Baixo impacto + fácil, inject se sobrar tempo
        - Baixo impacto + difícil, ignorar

    - step: 4
      name: "Gerar plano de injeção"
      description: |
        Pra cada injetor ausente/fraco:
        - O que injetar
        - Como injetar (mudança concreta no produto)
        - Quando (agora, v2, v3)

  output_example: |
    ## UAU Audit, Curso Tráfego Pago XYZ

    | Injetor | Presença (0-10) | Status | Ação |
    |---------|-----------------|--------|------|
    | 1. Mecanismo Oculto | 3 | Fraco | Batizar "Método Funil Invertido" |
    | 2. Tempo Impossível | 4 | Fraco | Quick win em 7 dias (1ª campanha) |
    | 3. Bônus Surpresa | 0 | Ausente | Adicionar "Auditoria 1:1 ao final" |
    | 4. Resultado Específico | 2 | Ausente | Sair com 3 campanhas RODANDO |
    | 5. Formato Inesperado | 5 | Médio | Rebatizar "Aceleradora" |
    | 6. Anti-Método | 1 | Ausente | "Pare de criar conteúdo" hook |

    **Score UAU total:** 15/60 (25%)

    **Priorização:**
    - **Injetar agora (alto impacto, fácil):** 1, 3, 5 (mecanismo + bônus + formato)
    - **V2 (alto impacto, difícil):** 2, 4, 6 (estrutura de tempo, entregáveis pro aluno, reposicionamento completo)

    **Plano concreto:**
    1. Semana 1, batizar mecanismo, rebatizar formato
    2. Semana 2, adicionar bônus-produto (auditoria 1:1 ao final)
    3. V2 (próxima turma), restruturar pra quick win em 7d + 3 campanhas rodando + hook anti-método

  acceptance_criteria:
    - "Todos os 6 injetores auditados com score"
    - "Injetores ausentes têm recomendação de injeção"
    - "Priorização (alto/baixo impacto × fácil/difícil)"
    - "Plano de injeção com prazo"

  veto_conditions:
    - "Score UAU total < 30% → vetar produto, reconstrução urgente"

  handoff:
    on_complete: "Se score >= 70%, libera pro feed-scale. Se < 70%, rodar injeções primeiro"
    deliverable: "UAU Audit Report"
```

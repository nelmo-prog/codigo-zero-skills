# Produto Review

```yaml
task:
  task_name: "Auditoria Cruzada de Produto Existente"
  status: pending
  responsible_executor: produto-chief
  execution_type: Agent
  estimated_time: "45-90 min"
  elicit: true

  input:
    - "Produto completo (spec, módulos, promessa, formato, preço atual)"
    - "Avatar-alvo (idealmente do avatar-ultra-profundo)"
    - "Concorrência direta (2-3 nomes)"
    - "Métricas atuais (conversão, churn, satisfação, se tiver)"

  output:
    - "Relatório de auditoria em 8 dimensões"
    - "Priorização de gaps"
    - "Plano de ação"

  action_items:

    - step: 1
      name: "Coletar contexto"
      description: |
        Perguntar ao aluno os 4 inputs.
        Se faltar avatar ou concorrência, apontar mas seguir com hipóteses.

    - step: 2
      name: "Rodar 8 dimensões em paralelo"
      description: |
        Coordenar os especialistas:

        **Dimensão 1, Job Fit** (@clayton-christensen)
        - Produto cumpre o job real do avatar?
        - Job é específico?

        **Dimensão 2, Value Equation** (@alex-hormozi-produto)
        - Sonho claro? Probabilidade alta? Tempo curto? Esforço baixo?

        **Dimensão 3, Unique Mechanism** (@eugene-schwartz-produto)
        - Tem nome proprietário? Tem passos? Resolve dor oculta?

        **Dimensão 4, Blue Ocean ERRC** (@kim-mauborgne)
        - Elimina algo? Categoria nova?

        **Dimensão 5, Simplicidade** (@steve-jobs)
        - Foca em 1 dor? Tem 1 The One Thing?

        **Dimensão 6, Opportunity Switch** (@russell-brunson)
        - Nova oportunidade ou melhoria? AC definido?

        **Dimensão 7, Positioning** (@april-dunford-produto)
        - Categoria onde vence? Atributos → valor → prova?

        **Dimensão 8, 6 Injetores UAU** (@produto-chief)
        - Quantos dos 6 injetores estão presentes?

    - step: 3
      name: "Comparar vs concorrência"
      description: |
        Pra cada dimensão, scorecard vs 2-3 concorrentes:
        - Quem vence nessa dimensão?
        - Onde o produto tá fraco e concorrência forte?
        - Onde é blue ocean?

    - step: 4
      name: "Comparar vs avatar"
      description: |
        Pegar o Resumo SCALE do avatar-ultra-profundo.
        Verificar alinhamento:
        - Dor principal do avatar × promessa do produto
        - Objeções do avatar × UAU matrix
        - Linguagem do avatar × one-liner

    - step: 5
      name: "Priorizar gaps"
      description: |
        Ranking IMPACTO × ESFORÇO:
        - Fix urgente (alto impacto, baixo esforço)
        - Fix médio prazo (alto impacto, alto esforço)
        - Nice-to-have (baixo impacto, baixo esforço)
        - Ignorar (baixo impacto, alto esforço)

    - step: 6
      name: "Plano de ação"
      description: |
        Pra cada gap priorizado:
        - O que fazer
        - Qual agente chamar
        - Prazo
        - Critério de conclusão

  output_example: |
    ## Relatório de Auditoria, Curso Tráfego Pago XYZ

    ### Score por Dimensão

    | Dimensão | Score | Achado |
    |----------|-------|--------|
    | 1. Job Fit | 6/10 | Job é genérico, falta emocional/social |
    | 2. Value Equation | 4/10 | Tempo 6 meses, esforço alto, poucas provas |
    | 3. Unique Mechanism | 2/10 | Sem nome proprietário, sem passos |
    | 4. Blue Ocean ERRC | 3/10 | Paralelo à concorrência, sem eliminar |
    | 5. Simplicidade | 5/10 | 50 aulas, 12 bônus (inflado) |
    | 6. Opportunity Switch | 4/10 | Improvement, AC fraco |
    | 7. Positioning | 6/10 | Categoria 'curso de tráfego', genérica |
    | 8. 6 Injetores UAU | 2/6 | Só tem formato (e duvidoso) + bônus |

    **Score total:** 32/80 (40%)
    **Diagnóstico:** Precisa de reconstrução parcial, não só ajuste

    ### vs Concorrência
    - **Vs Curso A:** perde em preço, empata em conteúdo
    - **Vs Mentoria B:** perde em ticket, ganha em formato gravado
    - **Blue Ocean potencial:** done-with-you não está no mercado

    ### vs Avatar
    - Dor do avatar é "ter negócio que rende sem virar creator"
    - Produto atual promete "aprender tráfego pago"
    - GAP, avatar quer RESULTADO, produto entrega CONHECIMENTO

    ### Priorização

    **Fix urgente (alto impacto, baixo esforço):**
    1. Batizar mecanismo (→ @eugene-schwartz-produto, 1-2h)
    2. Cortar 30% do conteúdo (→ @steve-jobs, 2-3h)
    3. Rebatizar categoria (aceleradora em vez de curso)

    **Fix médio prazo (alto impacto, alto esforço):**
    4. Adicionar done-with-you na semana 1 (→ novo delivery cube)
    5. Restruturar pra quick win em 7d
    6. Attractive Character completo (→ @russell-brunson)

    **Nice-to-have:**
    7. Detalhes invisíveis (email boas-vindas personalizado, certificado físico)

    **Ignorar:**
    - Reescrever aulas uma por uma (alto esforço, retorno marginal)

    ### Plano de Ação (4 semanas)

    Semana 1, mecanismo + cortes (@schwartz + @jobs)
    Semana 2, done-with-you + quick win estruturado (@hormozi)
    Semana 3, AC + positioning (@brunson + @dunford)
    Semana 4, compilação + feed-scale

  acceptance_criteria:
    - "8 dimensões auditadas com score"
    - "Comparação vs concorrência feita"
    - "Comparação vs avatar feita"
    - "Priorização com impacto × esforço"
    - "Plano de ação com prazo"

  veto_conditions:
    - "Score total < 30% → recomenda reconstrução total (rodar `*create`)"

  handoff:
    on_complete: "Baseado no score, roteia pra injeções (score 40-70%) ou reconstrução (score < 40%) ou feed-scale (score 70%+)"
    deliverable: "Relatório de auditoria + plano de ação"
```

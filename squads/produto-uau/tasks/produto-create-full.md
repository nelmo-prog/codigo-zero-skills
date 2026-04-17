# Produto Create Full

```yaml
task:
  task_name: "Criar Produto Completo do Zero (7 Fases)"
  status: pending
  responsible_executor: produto-chief (orquestrador)
  execution_type: Agent
  estimated_time: "2-4h"
  elicit: true

  input:
    - "Avatar (Bloco 14 Resumo SCALE do avatar-ultra-profundo)"
    - "Mercado (L.U.C.R.O)"
    - "Expertise do aluno"
    - "Tipo de produto diagnosticado"
    - "Concorrência principal (3-5 nomes)"

  output:
    - "Spec completa do produto (templates/produto-spec-tmpl.md)"
    - "UAU Matrix (templates/uau-matrix-tmpl.md, 6 injetores)"
    - "ERRC Grid (templates/errc-grid-tmpl.md)"
    - "Pacote SCALE (templates/pacote-scale-tmpl.md, input pro offer-creator)"
    - "First Draft (templates/first-draft-tmpl.md, MVP executável)"

  action_items:

    - step: 1
      name: "FASE 1, Discovery"
      agent: produto-chief
      description: |
        - Confirmar pré-requisitos (avatar, mercado, tipo)
        - Se algo faltando, roteia pra fonte correta (avatar-ultra-profundo, L.U.C.R.O, *diagnose)
        - Carregar contexto

      checkpoint:
        question: "Pré-requisitos completos?"
        veto_if_missing:
          - avatar (Bloco 14)
          - mercado validado
          - tipo de produto definido

    - step: 2
      name: "FASE 2, Job Discovery (JTBD)"
      agent: clayton-christensen
      description: |
        Rotear pra clayton-christensen com contexto.
        Output esperado, Job Statement canônico (funcional + emocional + social).

      checkpoint:
        question: "Job é específico, não genérico?"
        reject_if:
          - "Job = 'ganhar mais dinheiro'" (genérico)
          - "Job = 'ser feliz'" (genérico)

    - step: 3
      name: "FASE 3, Unique Mechanism"
      agent: eugene-schwartz-produto
      description: |
        Rotear pra eugene-schwartz-produto com Job Statement.
        Output, mecanismo único com NOME PRÓPRIO + 3-5 passos + por que funciona.

      checkpoint:
        question: "Mecanismo tem nome proprietário e 3-5 passos?"
        reject_if:
          - "Sem nome próprio"
          - "Menos de 3 ou mais de 5 passos"
          - "Sem explicação do porquê funciona"

    - step: 4
      name: "FASE 4, Value Equation + Delivery Cubes"
      agent: alex-hormozi-produto
      description: |
        Rotear pra alex-hormozi-produto com Job + Mecanismo.
        Output, Value Equation pontuada nos 4 eixos + Delivery Cubes (mínimo 8).

      checkpoint:
        question: "Equação fecha? Tempo e esforço cortados brutalmente?"
        reject_if:
          - "Dream Outcome não é mensurável"
          - "Zero provas de Probabilidade"
          - "Tempo igual ou maior que status quo"
          - "Menos de 8 delivery cubes"

    - step: 5
      name: "FASE 5, Blue Ocean ERRC"
      agent: kim-mauborgne
      description: |
        Rotear pra kim-mauborgne com stack + concorrência.
        Output, ERRC Grid + Strategy Canvas + categoria nova proposta.

      checkpoint:
        question: "Todos os 4 quadrantes preenchidos? Curva diverge 50%+?"
        reject_if:
          - "Algum quadrante vazio"
          - "Sem item corajoso em 'Eliminar'"
          - "Curva paralela à concorrência"

    - step: 6
      name: "FASE 6, UAU Injection"
      agents:
        - steve-jobs (simplicidade + detalhe invisível)
        - russell-brunson (opportunity switch + attractive character)
        - april-dunford-produto (positioning + one-liner)
      description: |
        Executar em sequência:
        1. @steve-jobs roda Subtraction Audit (corta 30-50%)
        2. @steve-jobs aplica os 6 injetores de UAU
        3. @russell-brunson faz Opportunity Switch + Attractive Character
        4. @april-dunford-produto faz Product Positioning + one-liner

      checkpoint:
        question: "6 injetores presentes? Opportunity switch rodado? Positioning claro?"
        reject_if:
          - "Menos de 6 injetores aplicados"
          - "Produto ainda é 'improvement' (não virou opportunity)"
          - "Sem Attractive Character definido"
          - "Sem one-liner"

    - step: 7
      name: "FASE 7, First Draft + Compilação"
      agent: produto-chief
      description: |
        Compilar TUDO nos templates:
        1. `produto-spec-tmpl.md` (arquitetura completa)
        2. `uau-matrix-tmpl.md` (6 injetores detalhados)
        3. `errc-grid-tmpl.md` (4 quadrantes + canvas)
        4. `pacote-scale-tmpl.md` (input pro offer-creator)
        5. `first-draft-tmpl.md` (MVP por tipo)

        Rodar checklists:
        - `uau-factor-checklist.md`
        - `produto-viability-checklist.md`
        - `produto-completeness-checklist.md`

      checkpoint:
        question: "Todos os 5 templates preenchidos? 3 checklists passaram?"
        reject_if:
          - "Algum template incompleto"
          - "Algum checklist com item não marcado"

  output_example: |
    ## Produto Criado, Aceleradora de Primeiro R$10k

    **FASE 1 - Discovery:** OK (avatar + mercado + tipo híbrido)
    **FASE 2 - JTBD:** OK ("Quando sou funcionário saturado, ajuda-me a ter negócio online que rende sem virar creator")
    **FASE 3 - Mecanismo:** OK (Método 80/20 Invertido, 4 passos nomeados)
    **FASE 4 - Value Equation:** OK (Dream R$10k/60d, Prob alta via done-with-you, Tempo 60d (vs 6m mercado), Esforço 10h/sem)
    **FASE 5 - ERRC:** OK (elimina acesso vitalício, reduz aulas, aumenta lives, cria done-with-you)
    **FASE 6 - UAU:** OK (6 injetores + AC + one-liner)
    **FASE 7 - First Draft:** OK (5 templates + 3 checklists)

    **Entregáveis finais:**
    - Spec → [link]
    - UAU Matrix → [link]
    - ERRC Grid → [link]
    - Pacote SCALE → [link]
    - First Draft → [link]

    **Próximo passo:** rodar `*feed-scale` pra exportar pacote pro S.C.A.L.E.

  acceptance_criteria:
    - "Todas as 7 fases completas com checkpoint passando"
    - "5 templates preenchidos"
    - "3 checklists passaram"
    - "Output pronto pra alimentar S.C.A.L.E."

  veto_conditions:
    - "Fase pulada (todos os checkpoints devem passar)"
    - "Algum injetor de UAU ausente"
    - "Mecanismo sem nome próprio"
    - "ERRC com quadrante vazio"

  handoff:
    on_complete: "Roda *feed-scale pra exportar pacote pro S.C.A.L.E."
    deliverable: "Produto completo, 5 templates + 3 checklists"
```

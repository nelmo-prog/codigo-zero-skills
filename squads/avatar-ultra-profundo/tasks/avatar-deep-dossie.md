# Avatar Deep Dossie

```yaml
task:
  task_name: "Construir dossiê completo dos 14 blocos"
  status: pending
  responsible_executor: avatar-chief (orquestrador)
  execution_type: Agent (rotação de 7 especialistas)
  estimated_time: "2-4 horas"
  elicit: true

  input:
    - "Briefing consolidado (output de avatar-diagnose-input.md)"
    - "Acesso ao template dossie-avatar-tmpl.md"
    - "Acesso à metodologia avatar-methodology.md"

  output:
    - "Dossiê completo em markdown com 14 blocos preenchidos"
    - "50 camadas do Bloco 12 marcadas como check"
    - "Marcações FATO/INFERÊNCIA/HIPÓTESE em cada insight chave"

  action_items:
    - step: 1
      name: "Fase 1, Input + Raio X (avatar-chief + robert-cialdini)"
      description: |
        Com base no briefing, rodar uma hipótese inicial do Bloco 1 (Raio X
        Executivo). Não é o Raio X final, é a hipótese que vai ser refinada
        no final do workflow. Saída: Bloco 1 versão 1.0 (hipótese marcada).

    - step: 2
      name: "Fase 2, Identidade + Contexto + Tentativas (clayton-christensen)"
      description: |
        Rotear para @clayton-christensen executar:
        - Bloco 2, Identidade e Contexto de Vida
        - Bloco 3, Identidade Psicológica
        - Bloco 9, Histórico de Tentativas

        Christensen usa JTBD pra garantir que contexto específico supere
        demografia genérica.

    - step: 3
      name: "Fase 3, Dores (brene-brown)"
      description: |
        Rotear para @brene-brown executar:
        - Bloco 4, 6 camadas de dor completas
        - Contribuição pros medos emocionais/identitários do Bloco 6

        Garantir que as camadas 4.5 (silenciosa) e 4.6 (inconfessável) sejam
        escavadas, não só declaradas.

    - step: 4
      name: "Fase 4, Desejos (jay-abraham)"
      description: |
        Rotear para @jay-abraham executar:
        - Bloco 5, 7 camadas de desejo completas

        Especial atenção à camada 5.4 (validação com destinatário nomeado) e
        5.7 (desejo oculto, vingança/superioridade/reconhecimento específico).

    - step: 5
      name: "Fase 5, Medos + Mecânica (daniel-kahneman)"
      description: |
        Rotear para @daniel-kahneman executar:
        - Bloco 6, Medos, Contradições, Ganhos Secundários
        - Bloco 11, Mecânica de Decisão (parte cognitiva)

        Enfatizar aversão à perda ESPECÍFICA (não genérica) e mapear ganhos
        secundários do problema.

    - step: 6
      name: "Fase 6, Autossabotagem + Objeções + Subcamadas (alex-hormozi-avatar)"
      description: |
        Rotear para @alex-hormozi-avatar executar:
        - Bloco 7, 3-5 padrões ativos dos 15
        - Bloco 8, crenças e objeções com tradução
        - Bloco 13, 10 subcamadas (com foco em 7 e 10)

        Regra: toda objeção declarada precisa ter tradução pra objeção real.

    - step: 7
      name: "Fase 7, Linguagem + Compilação (eugene-schwartz)"
      description: |
        Rotear para @eugene-schwartz executar:
        - Bloco 10, 25+ frases cruas em 5 categorias
        - Bloco 14, 18 campos destilados pro S.C.A.L.E.

        Regra: toda frase do Bloco 10 precisa passar no teste 'humano real
        diria?'. Nível de consciência (1-5) precisa estar identificado no
        topo do Bloco 14.

    - step: 8
      name: "Fase 8, Auditoria + Síntese (avatar-chief)"
      description: |
        Avatar Chief executa:
        - Checklist avatar-completeness-checklist.md (50 camadas, 10 subcamadas,
          25+ frases, 14 blocos)
        - Checklist avatar-depth-checklist.md (8 perguntas de autoauditoria)
        - Refinamento final do Bloco 1 (Raio X) consolidando tudo
        - Exportação do pacote S.C.A.L.E. (Bloco 14) em arquivo separado
          se solicitado

        Se alguma pergunta da autoauditoria falhar, rotear pro especialista
        dono do bloco e repetir.

  output_example: |
    ## Dossiê Avatar Ultra Profundo, [Nome do Avatar]
    **Data:** 2026-04-16
    **Versão:** 1.0
    **Produto:** [produto]
    **Nível de Consciência:** 3 (Consciente da Solução)

    ---

    ### Bloco 1, Raio X Executivo
    [preenchido pelo avatar-chief + Cialdini, refinado ao final]

    ### Bloco 2, Identidade e Contexto de Vida
    [preenchido pelo Christensen]

    ### Bloco 3, Identidade Psicológica
    [preenchido pelo Christensen]

    ### Bloco 4, Camadas de Dor
    [preenchido pela Brené Brown, 6 camadas]

    ### Bloco 5, Camadas de Desejo
    [preenchido pelo Jay Abraham, 7 camadas]

    ### Bloco 6, Medos, Contradições, Ganhos Secundários
    [preenchido pelo Kahneman + contribuições da Brown]

    ### Bloco 7, Padrões de Autossabotagem
    [preenchido pelo Hormozi, 3-5 padrões ativos]

    ### Bloco 8, Crenças e Objeções
    [preenchido pelo Hormozi, 6 subcategorias]

    ### Bloco 9, Histórico de Tentativas
    [preenchido pelo Christensen, 3-5 tentativas com JTBD real]

    ### Bloco 10, Linguagem Real do Avatar
    [preenchido pelo Schwartz, 25+ frases em 5 categorias]

    ### Bloco 11, Mecânica de Decisão
    [preenchido pelo Cialdini + Kahneman, 6 etapas compra + 4 etapas fuga]

    ### Bloco 12, Checklist das 50 Camadas Obrigatórias
    [preenchido pelo avatar-chief, verificação cruzada]

    ### Bloco 13, 10 Subcamadas de Autossabotagem
    [preenchido pelo Hormozi, 10 subcamadas com cena]

    ### Bloco 14, Resumo Estratégico pro S.C.A.L.E. (18 campos)
    [preenchido pelo Schwartz, pacote final]

    ---

    ### Autoauditoria (8 perguntas)
    1. ✅ Parece ser humano real?
    2. ✅ Não poderia ser 50 avatares?
    3. ✅ Motivo real diferente do declarado?
    4. ✅ Autossabotagem como força central?
    5. ✅ Linguagem crua (não de agência)?
    6. ✅ Dor inconfessável apareceu?
    7. ✅ Marcações FATO/INFERÊNCIA/HIPÓTESE presentes?
    8. ✅ Muda oferta, copy, ads?

    **Veredicto: APROVADO**

  acceptance_criteria:
    - "14 blocos preenchidos"
    - "50 camadas checadas no Bloco 12"
    - "10 subcamadas dissecadas no Bloco 13"
    - "25+ frases coletadas no Bloco 10"
    - "18 campos preenchidos no Bloco 14"
    - "Marcações FATO/INFERÊNCIA/HIPÓTESE em insights chave"
    - "Autoauditoria passou nas 8 perguntas (ou rebuild executado)"

  veto_conditions:
    - "Bloco faltando → VETO, rodar fase específica"
    - "Menos de 25 frases no Bloco 10 → VETO, voltar pro Schwartz"
    - "Motivo real (campo 16 do Bloco 14) igual ao desejo declarado (campo 3) → VETO"
    - "Nenhum padrão de autossabotagem no Bloco 7 → VETO"
    - "Camada 4.6 (dor inconfessável) vazia ou genérica → VETO"

  handoff:
    on_complete: "Dossiê vai pra avatar-review-audit.md ou direto pra avatar-feed-scale.md"
    deliverable: "Dossiê completo em markdown + pacote S.C.A.L.E. separado"
```

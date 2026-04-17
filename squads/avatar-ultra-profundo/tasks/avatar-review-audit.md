# Avatar Review Audit

```yaml
task:
  task_name: "Autoauditoria do dossiê, 8 perguntas de humanidade e profundidade"
  status: pending
  responsible_executor: avatar-chief
  execution_type: Agent
  estimated_time: "20-40 min"
  elicit: true

  input:
    - "Dossiê completo (versão final ou intermediária)"
    - "Checklists avatar-depth-checklist.md e avatar-completeness-checklist.md"

  output:
    - "Relatório de autoauditoria com 8 perguntas respondidas"
    - "Veredicto (APROVADO / REBUILD PARCIAL / REBUILD TOTAL)"
    - "Rotas pros especialistas donos dos blocos que falharam"

  action_items:
    - step: 1
      name: "Rodar as 8 perguntas de humanidade/profundidade"
      description: |
        Ler o dossiê de ponta a ponta. Pra cada pergunta, marcar PASSA, PARCIAL
        ou FALHA, com justificativa concreta (cite o bloco/camada).

        **As 8 perguntas:**

        1. **Isso parece um ser humano real que eu conheceria?**
           - Critério: tem nome, idade, cidade, cena concreta, frases literais
           - Falha se: "consumidor", "target", "pessoa que", sem cena

        2. **Poderia ser 50 avatares diferentes?**
           - Critério: cortar o briefing no topo, ler só o miolo, consigo
             distinguir de outro dossiê?
           - Falha se: frases genéricas de nicho, sem especificidade

        3. **O motivo REAL de compra está mapeado, diferente do declarado?**
           - Critério: campo 16 do Bloco 14 é diferente do campo 3
           - Falha se: campo 16 é versão polida do campo 3

        4. **Autossabotagem está como FORÇA CENTRAL, não detalhe?**
           - Critério: Blocos 7 e 13 têm destaque, com cenas, gatilhos,
             frases internas, subcamadas 7 e 10 detalhadas
           - Falha se: autossabotagem só no Bloco 7, sem subcamadas, sem gatilho
             que rompe

        5. **Linguagem crua é linguagem de bar ou de agência?**
           - Critério: Bloco 10 tem 25+ frases que soam humanas
           - Falha se: frases simétricas, polidas, "ele se questiona sobre"

        6. **Dor inconfessável apareceu (não só declarada)?**
           - Critério: Camada 4.6 do Bloco 4 tem vergonha/inveja/desejo
             sombrio específico
           - Falha se: 4.6 vazio ou "sente frustração profunda"

        7. **Cada insight chave tem marcação FATO/INFERÊNCIA/HIPÓTESE?**
           - Critério: varrer o dossiê, encontrar marcações em cenas,
             afirmações fortes, conclusões
           - Falha se: < 20 marcações ou marcações só em alguns blocos

        8. **O dossiê muda a oferta, a copy e o anúncio?**
           - Critério: pegar o Bloco 14 e simular 3 headlines de anúncio,
             3 bullets de LP, 1 lead de email. Soam diferente de qualquer
             outro dossiê?
           - Falha se: os testes saem genéricos

    - step: 2
      name: "Rodar checklists de completude"
      description: |
        Paralelamente às 8 perguntas, rodar:
        - avatar-completeness-checklist.md (14 blocos, 50 camadas, 10 subcamadas, 25+ frases)
        - Contar marcações FATO/INFERÊNCIA/HIPÓTESE
        - Verificar coerência cruzada (Bloco 4.6 deve ecoar no Bloco 5.7,
          Bloco 1 deve destilar Bloco 14)

    - step: 3
      name: "Emitir veredicto"
      description: |
        **APROVADO:** 8/8 perguntas passaram + completude 100%
        **REBUILD PARCIAL:** 1-2 perguntas falharam, rotas específicas
        **REBUILD TOTAL:** 3+ perguntas falharam ou pergunta 1 ou 2 falhou
          (fundação quebrada)

    - step: 4
      name: "Rotear falhas"
      description: |
        Se falhou:
        - Pergunta 1 ou 2 → @clayton-christensen (reconstruir Blocos 2, 3 com
          especificidade concreta)
        - Pergunta 3 → @clayton-christensen (JTBD real) + @eugene-schwartz
          (refinar campo 16)
        - Pergunta 4 → @alex-hormozi-avatar (rebuild Blocos 7 e 13)
        - Pergunta 5 → @eugene-schwartz (refazer Bloco 10)
        - Pergunta 6 → @brene-brown (escavar camada 4.6)
        - Pergunta 7 → @avatar-chief (passar por todos os blocos adicionando marcações)
        - Pergunta 8 → @eugene-schwartz (refinar Bloco 14) + @alex-hormozi
          (alinhar objeções e gatilhos)

  output_example: |
    # Autoauditoria do Dossiê, Carlos (Contador, 48, SP)

    **Data:** 2026-04-16
    **Dossiê auditado:** dossie-carlos-contador-v1.md

    ---

    ## As 8 Perguntas

    ### 1. Parece ser humano real? ✅ PASSA
    - Nome (Carlos Eduardo Marques), idade (48), cidade (Campinas SP), profissão
      (contador CRC 2001), família (casado, 2 filhos), cenas concretas (cliente
      R$ 280, almoço com marmita, churrasco família)
    - Evidência: Blocos 1, 2, 3 densos em especificidade

    ### 2. Poderia ser 50 avatares? ❌ PARCIAL
    - O miolo do dossiê é distintivo, mas a Categoria 10.2 (WhatsApp) poderia
      caber em qualquer contador 45+ frustrado
    - Rota: reforçar destinatário específico das mensagens (Pedro, colega
      de faculdade, escritório em Limeira)

    ### 3. Motivo real diferente do declarado? ✅ PASSA
    - Campo 3 (desejo central): "voltar a faturar R$ 40k como em 2015 sem
      virar influencer"
    - Campo 16 (motivo real): "provar em silêncio ao pai falecido e irmão
      vivo que contabilidade não foi erro em 98"
    - São claramente diferentes

    ### 4. Autossabotagem como força central? ✅ PASSA
    - Bloco 7 tem 4 padrões ativos
    - Bloco 13 tem 10 subcamadas detalhadas
    - Subcamada 7 (apego ao problema como identidade) tem análise profunda
    - Subcamada 10 (gatilho que rompe) tem cena concreta de sexta à noite

    ### 5. Linguagem crua ou de agência? ✅ PASSA
    - Bloco 10 tem 29 frases
    - Inclui palavrões em monólogo ("Puta que pariu")
    - Erros ortográficos em busca Google ("contabil" sem acento)
    - Abreviações em WhatsApp
    - Passa no teste 'humano real diria?'

    ### 6. Dor inconfessável apareceu? ✅ PASSA
    - Camada 4.6: inveja do irmão advogado + vergonha dessa inveja + desejo
      (uma vez, Natal) de que o irmão quebrasse "um pouquinho"
    - Marcada como INFERÊNCIA forte, com evidência cruzada nos Blocos 5.7 e 12.48

    ### 7. Marcações de confiança? ⚠️ PARCIAL
    - Contei 34 marcações no dossiê
    - Blocos 1, 4, 5, 7, 10, 13, 14 têm marcações densas
    - Blocos 2 e 3 têm poucas marcações, maior parte sem marcação explícita
    - Rota: passar pelos Blocos 2 e 3 adicionando marcações

    ### 8. Muda oferta, copy, ads? ✅ PASSA
    - Teste 1 (3 headlines de anúncio com base no Bloco 14):
      - "Contador 48+ que quer faturar R$ 2k por cliente sem virar influencer
        de LinkedIn"
      - "Seu filho adolescente já duvida que contabilidade tem futuro?"
      - "Escritório de 23 anos cobrando R$ 300: o método silencioso pra sair
        disso"
    - Soam distintos de qualquer outro avatar de contador

    ---

    ## Veredicto: **REBUILD PARCIAL**

    2 perguntas com falha parcial (2 e 7), resto aprovado.

    ### Rotas de Rebuild
    1. **@clayton-christensen:** Refinar Bloco 2 e 3 com mais especificidade
       + adicionar marcações FATO/INFERÊNCIA em cada afirmação forte
    2. **@eugene-schwartz:** Refinar Categoria 10.2 com destinatário explícito
       (Pedro, escritório Limeira) e cenas concretas de mensagens

    Tempo estimado de rebuild parcial: 40-60 min.

  acceptance_criteria:
    - "8 perguntas respondidas com evidência concreta (blocos/camadas citados)"
    - "Veredicto emitido (APROVADO / REBUILD PARCIAL / REBUILD TOTAL)"
    - "Se REBUILD, rotas pros especialistas específicos"
    - "Checklist de completude rodado em paralelo"

  veto_conditions:
    - "Pergunta 1 falha total → VETO (dossiê não é humano, reconstruir Blocos 2 e 3)"
    - "Pergunta 3 falha → VETO (sem motivo real, dossiê é superficial)"
    - "Pergunta 6 falha → VETO (sem dor inconfessável, falta profundidade)"

  handoff:
    on_complete_aprovado: "Dossiê pronto, rota pra avatar-feed-scale ou uso direto"
    on_complete_rebuild: "Rotas acionadas, re-auditoria após rebuild"
    deliverable: "Relatório de autoauditoria em markdown"
```

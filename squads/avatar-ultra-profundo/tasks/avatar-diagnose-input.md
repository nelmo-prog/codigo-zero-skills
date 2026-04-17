# Avatar Diagnose Input

```yaml
task:
  task_name: "Clarificar briefing antes de rodar dossiê completo"
  status: pending
  responsible_executor: avatar-chief
  execution_type: Agent
  estimated_time: "10-15 min"
  elicit: true

  input:
    - "Pedido inicial do usuário (pode ser vago, 'quero avatar do meu cliente')"

  output:
    - "Briefing estruturado em 10 campos prontos para rodar o workflow completo"
    - "Lista de hipóteses iniciais do avatar (para validar durante o dossiê)"

  action_items:
    - step: 1
      name: "Apresentar checklist dos 10 campos obrigatórios"
      description: |
        Explicar ao usuário que, antes de rodar os 14 blocos, precisamos destes
        inputs pra não construir em cima de suposição genérica. Apresentar em
        lista numerada. Se o usuário tiver resposta rápida, coletar. Se não,
        oferecer opções/hipóteses pra ele validar.

        **Campos obrigatórios:**
        1. **Nicho específico** (não "empresários", mas "dentistas clínica geral
           interior de SP faturando 30-80k/mês")
        2. **Produto/oferta que está sendo vendida** (ebook? curso? mentoria?
           serviço? SaaS? físico?)
        3. **Faixa de ticket** (R$ 47 / R$ 497 / R$ 1.997 / R$ 5.000+ / high-ticket
           R$ 10k+)
        4. **B2B, B2C ou B2B2C** (quem paga, quem usa)
        5. **Canal de aquisição principal** (Instagram orgânico? Meta Ads?
           Google Ads? YouTube? LinkedIn? indicação? email?)
        6. **Canal de venda** (LP + checkout? VSL? grupo WhatsApp? call 1:1?
           webinar? lançamento?)
        7. **Nível de consciência do público** (Schwartz 1-5, inconsciente a
           mais consciente)
        8. **Momento do mercado** (saturado? crescente? emergente? em crise?)
        9. **3 concorrentes diretos** (nomes reais, pra cruzar linguagem)
        10. **Objetivo do dossiê** (criar oferta nova? reescrever copy? rodar
            ads? lançamento?)

    - step: 2
      name: "Coletar respostas"
      description: |
        Fazer as 10 perguntas. Se usuário não souber alguma, oferecer 2-3
        hipóteses plausíveis e pedir escolha.

        Exemplo: "Não sei o nível de consciência" → "Pelos sinais do nicho,
        é provavelmente Nível 3 (consciente da solução, já viu cursos parecidos
        mas não comprou). Confirma ou corrige?"

    - step: 3
      name: "Consolidar briefing estruturado"
      description: |
        Gerar briefing em markdown seguindo template input-avatar-tmpl.md.
        Validar 1x com usuário antes de liberar pro workflow principal.

    - step: 4
      name: "Levantar hipóteses iniciais (opcional mas recomendado)"
      description: |
        Antes de rodar os 14 blocos, levantar 3-5 HIPÓTESES sobre o avatar
        baseado só no briefing. Marcar como HIPÓTESE. Durante o dossiê, essas
        hipóteses serão validadas, refinadas ou descartadas.

        Exemplos de hipóteses:
        - "Avatar provavelmente tem 40-55 anos (nicho + ticket sugerem)"
        - "Dor dominante deve ser comparação com pares que deram certo"
        - "Principal objeção provável é 'já tentei parecido, não funcionou'"

  output_example: |
    ## Briefing Consolidado, [Produto]

    **Nicho:** Contadores CRC, 40-55 anos, interior de SP/MG/RS, com escritório
    próprio de 1-2 pessoas, faturando R$ 8-18k/mês, principalmente atendendo
    MEI e ME.

    **Produto:** Mentoria coletiva online de 6 meses, foco em reposicionamento
    do escritório pra atender PME (R$ 300k+/mês)

    **Ticket:** R$ 3.997 à vista ou R$ 450 x 12

    **B2B ou B2C:** B2B (contador empresário)

    **Canal aquisição:** Meta Ads (Instagram feed) + YouTube orgânico

    **Canal venda:** LP com VSL + call 1:1 pra qualificados

    **Consciência:** Nível 3 (sabe que existem soluções, não convencido de qual)

    **Momento mercado:** Crescente, há ~5 players estabelecidos

    **Concorrentes:**
    - Contab Digital (Marcos Santos)
    - Escritório 5.0 (Carla Menezes)
    - CRC Pro (Paulo Bruno)

    **Objetivo do dossiê:** Reescrever LP + VSL + primeira sequência de email

    ---

    ### Hipóteses Iniciais (validar durante dossiê)
    1. **HIPÓTESE:** Avatar tem sensação de 'obsolescência profissional' e compara-se
       com irmão ou par que foi pra outra profissão de mais prestígio
    2. **HIPÓTESE:** Maior objeção será 'esses cursos são de quem não sabe
       contabilidade de verdade'
    3. **HIPÓTESE:** Autossabotagem dominante será perfeccionismo defensivo
       + consumo infinito de conteúdo
    4. **HIPÓTESE:** Gatilho de compra virá de evento familiar (filho, esposa,
       irmão) mais do que de evento profissional
    5. **HIPÓTESE:** Nível de consciência está no 3 estável, mas em crise
       pode migrar pro 4 (consciente do produto) em semanas

  acceptance_criteria:
    - "10 campos obrigatórios preenchidos (com hipótese explícita onde não houver dado)"
    - "Briefing em formato pronto pro workflow consumir"
    - "3-5 hipóteses iniciais levantadas e marcadas"
    - "Usuário validou o briefing antes de prosseguir"

  veto_conditions:
    - "Nicho genérico ('empresários', 'pessoas que querem crescer') → VETO, exigir especificidade"
    - "Ticket não definido → VETO, alinhar faixa antes de rodar"
    - "Objetivo do dossiê ausente → VETO, saber pra que o dossiê será usado muda a densidade"

  handoff:
    on_complete: "Briefing passa pro wf-avatar-from-zero.yaml, que rotaciona os 7 especialistas"
    deliverable: "Briefing estruturado em markdown"
```

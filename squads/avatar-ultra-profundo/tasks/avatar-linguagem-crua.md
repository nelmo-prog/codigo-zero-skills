# Avatar Linguagem Crua

```yaml
task:
  task_name: "Extrair Bloco 10, 25+ frases cruas do avatar"
  status: pending
  responsible_executor: eugene-schwartz
  execution_type: Agent
  estimated_time: "30-45 min"
  elicit: true

  input:
    - "Briefing do avatar (mínimo)"
    - "Ou dossiê completo (ideal)"
    - "Acesso a fontes externas (comentários IG, YouTube, grupos de WhatsApp, reviews) se disponível"

  output:
    - "25+ frases cruas em 5 categorias"
    - "Cada frase com marcação de origem (FATO de entrevista / HIPÓTESE plausível)"
    - "Observações de padrões linguísticos (erros ortográficos, gírias, níveis de formalidade)"

  action_items:
    - step: 1
      name: "Validar fontes disponíveis"
      description: |
        Perguntar ao usuário:
        - Você tem transcrições de entrevistas/calls com esse avatar?
        - Comentários de Instagram, YouTube, grupos públicos?
        - Reviews de produtos do nicho?
        - Conversas de WhatsApp (anonimizadas)?
        - Histórico de busca (se disponível)?

        Fontes REAIS são FATO. Sem fontes, só HIPÓTESE plausível baseada em padrão
        do nicho. Ambas são válidas, mas marcação obrigatória.

    - step: 2
      name: "Categoria 10.1, Conversa Consigo Mesmo (5+ frases)"
      description: |
        Monólogo interno. Chuveiro, trânsito, cama. Linguagem MUITO crua.

        Perguntas pro usuário (se não tiver dados reais):
        - O que ele pensa quando acorda de madrugada sem sono?
        - O que ele diz pra si no espelho antes de ir trabalhar?
        - Qual frase repete na cabeça quando algo dá errado?

        Cada frase: linguagem não polida, pode ter palavrão, pode ter frase
        incompleta. Se parece copy, NÃO É.

    - step: 3
      name: "Categoria 10.2, WhatsApp com Amigo Íntimo (5+ frases)"
      description: |
        Desabafo sem filtro pra UM amigo específico.

        Diferenças pra 10.1: aqui é verbalizado. Pode incluir:
        - Abreviações (pq, vc, mlk)
        - Áudios (marcar se é áudio)
        - Palavrões
        - Frases entrecortadas

        Perguntas:
        - Pra quem ele desabafa? (nome, contexto da amizade)
        - Qual foi a última mensagem REAL que ele mandou nessa linha?
        - O que ele manda em áudio vs texto?

    - step: 4
      name: "Categoria 10.3, Busca Google de Madrugada (5+ frases)"
      description: |
        O que ele digita no Google quando NINGUÉM TÁ VENDO. Geralmente:
        - Sem acento (digitando rápido)
        - Pergunta direta ou frase cortada
        - Mistura de técnico com emocional

        Exemplos de padrões:
        - "como parar de procrastinar de verdade"
        - "é normal sentir [emoção negativa] em [situação]"
        - "[nicho] aos [idade] ainda da tempo"
        - "[concorrente] funciona ou é golpe"

        IMPORTANTE: se possível, validar com Google Trends ou ferramenta de
        pesquisa de keyword (essas buscas têm volume, muitas vezes).

    - step: 5
      name: "Categoria 10.4, Objeções em Voz Alta (5+ frases)"
      description: |
        Como ele verbaliza objeção quando recebe uma oferta. Diferente de
        "razões pra não comprar" no Bloco 8. Aqui é a frase LITERAL.

        Padrões comuns:
        - "Parece bom, mas..."
        - "Isso funciona pros outros, mas pra mim..."
        - "Eu já tentei parecido em [ano], não rolou"
        - "Tô sem cabeça pra isso agora"
        - "Preciso conversar com a [esposa/sócio/contador]"

    - step: 6
      name: "Categoria 10.5, Fala Depois de Decidir (5+ frases)"
      description: |
        Como ele se justifica DEPOIS de comprar. Normalmente misto de:
        - Racionalização ("resolvi que era hora")
        - Urgência interna ("não dava mais pra continuar")
        - Aprovação social buscada ("meu amigo X falou que...")
        - Declaração de identidade ("desta vez é diferente")

        Isso importa porque vai informar a sequência de PÓS-COMPRA (onboarding,
        primeira aula, grupo de boas-vindas). A promessa implícita que ele fez
        a si mesmo é o que vai sustentar (ou quebrar) o engajamento.

    - step: 7
      name: "Observações de padrões linguísticos"
      description: |
        Depois de coletar 25+ frases, escrever 3-5 observações sobre padrões:
        - Erros ortográficos recorrentes
        - Gírias específicas do nicho
        - Nível de formalidade (voce/vc, você)
        - Uso de palavrões, "puta que pariu", "caralho"
        - Repetição de temas (família, dinheiro, comparação)

        Essas observações informam a VOZ da copy. A copy precisa soar como
        ele, não como o copywriter.

  output_example: |
    # Bloco 10, Linguagem Real do Avatar (Carlos, 48, contador)

    **Fontes consultadas:**
    - Briefing do usuário
    - 3 comentários extraídos de post Instagram @contabilidademaster (público)
    - 2 perguntas de grupo aberto "Contadores CRC Brasil" (LinkedIn)
    - Histórico de busca anonimizado de perfil similar (via Google Trends)

    ---

    ## 10.1 Conversa Consigo Mesmo (6 frases)

    1. "Puta que pariu, mais um mês igual." [HIPÓTESE plausível]
    2. "Será que eu fiz a escolha errada em 98?" [INFERÊNCIA, baseada em
       padrão de comparação com irmão]
    3. "O Ricardo (irmão) tá viajando pra Miami com a família. Eu tô aqui." [HIPÓTESE]
    4. "Pelo menos o Gabriel (filho) tá com saúde." [FATO, padrão de consolo]
    5. "Eu não aguento mais negociar R$ 20 com cliente." [FATO, relatado]
    6. "Se a Marina (esposa) soubesse como tá a conta..." [INFERÊNCIA]

    ## 10.2 WhatsApp para Amigo Íntimo (5 frases)
    **Destinatário:** Pedro, colega de faculdade, também contador, dono de
    escritório maior em Limeira.

    1. "Cara, tô precisando sair pra tomar cerveja, bora?" [FATO, padrão]
    2. "Pedro, te perguntar uma coisa, como tá o teu faturamento?" [HIPÓTESE]
    3. "Fechei o mês com 14k líquido, tô vendo se rebaixo alguma despesa" [FATO]
    4. "Será que eu tô muito pra trás do mercado? Sei lá, fiquei pensando." [FATO]
    5. "Mano, vou dormir. Abraço." [FATO]

    ## 10.3 Busca Google de Madrugada (8 frases)

    1. "contador 48 anos consegue mudar de ramo" [FATO, via Google Trends]
    2. "como cobrar mais por serviço contabil" [FATO]
    3. "por que escritorio contabilidade morreu" [FATO, com erro, padrão apressado]
    4. "contabilidade tradicional vs online qual ganha mais" [FATO]
    5. "é normal ter inveja do irmão que deu certo" [HIPÓTESE forte]
    6. "consultoria pra contador que ta perdendo cliente" [FATO]
    7. "contador que não quer usar instagram ainda ganha dinheiro" [HIPÓTESE]
    8. "como saber se minha profissão ta obsoleta" [INFERÊNCIA]

    ## 10.4 Objeções em Voz Alta (5 frases)

    1. "Parece bom, mas esses cursos nunca funcionam pra mim" [FATO]
    2. "Eu não vou virar influencer aos 48" [INFERÊNCIA, padrão declarado]
    3. "Já tentei consultoria em 23, R$ 3.600 no vento" [FATO]
    4. "Preciso pensar. Conversar com a Marina" [HIPÓTESE, padrão comum]
    5. "Essa galera que vende curso é cheia de lorota" [FATO]

    ## 10.5 Fala Depois de Decidir (5 frases)

    1. "Resolvi que chega. Não dá mais pra continuar igual" [HIPÓTESE]
    2. "Vi um cara de 51 anos que fez e deu certo, se ele fez, eu faço" [INFERÊNCIA]
    3. "Dessa vez eu vou aplicar, não é só estudar" [HIPÓTESE]
    4. "Investi 2k, mas o retorno vai ser rápido" [INFERÊNCIA]
    5. "Amor, comprei aquele curso, dessa vez é sério" [HIPÓTESE]

    ---

    ## Observações de Padrões Linguísticos

    1. **Erro ortográfico recorrente:** "contabil" sem acento em busca de madrugada.
       Indica pressa e estado emocional, não ignorância.

    2. **Padrão de consolo:** Ele balança pensamentos pesados com frases de
       alívio ("pelo menos X tá bem"). Isso é estratégia de auto-regulação
       emocional, não negação.

    3. **Comparação constante com irmão:** O nome "Ricardo" aparece 3x em
       24 horas de fala/busca. Validação implícita dos Blocos 4.6 e 5.7.

    4. **Formalidade baixa em WhatsApp, média na busca, alta em público:**
       Ele fala "mano" com Pedro, digita normal no Google, escreve "cordialmente"
       em email pro cliente. A copy precisa pegar o meio-termo, nem tudo "mano"
       nem tudo "cordialmente".

    5. **Evita palavrão em escrito, usa em monólogo interno:** Ele pensa "puta
       que pariu" mas escreve "Nossa, que situação". Copy não pode usar palavrão,
       mas pode usar intensidade emocional crua.

  acceptance_criteria:
    - "25+ frases coletadas (5 mínimo por categoria)"
    - "Cada frase com marcação FATO/INFERÊNCIA/HIPÓTESE e fonte"
    - "Observações de padrões linguísticos (3-5)"
    - "Todas as frases passam no teste 'humano real diria?'"

  veto_conditions:
    - "Menos de 25 frases → VETO, coletar mais"
    - "Frase polida/lapidada → VETO, reescrever ou descartar"
    - "Todas as frases marcadas como HIPÓTESE (sem FATO) → VETO, buscar fontes reais"
    - "Nenhuma observação de padrão linguístico → VETO"

  handoff:
    on_complete: "Bloco 10 pronto, pode ir direto pro copy-squad alimentar VSL/LP/ads"
    deliverable: "Arquivo bloco-10-linguagem.md ou seção do dossiê completo"
```

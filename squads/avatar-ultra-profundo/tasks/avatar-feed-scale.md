# Avatar Feed SCALE

```yaml
task:
  task_name: "Extrair Bloco 14 (18 campos) como pacote pronto pro S.C.A.L.E."
  status: pending
  responsible_executor: eugene-schwartz
  execution_type: Agent
  estimated_time: "20-30 min"
  elicit: false

  input:
    - "Dossiê completo (output de avatar-deep-dossie.md)"
    - "Template resumo-scale-tmpl.md"

  output:
    - "Arquivo resumo-scale.md com os 18 campos preenchidos"
    - "Nível de consciência identificado no topo"
    - "Formato pronto pra ser consumido pelo /offer-creator"

  action_items:
    - step: 1
      name: "Validar que dossiê completo existe"
      description: |
        Confirmar que os 13 blocos anteriores ao Bloco 14 foram preenchidos.
        Sem eles, o Bloco 14 será superficial. Se faltar algum bloco, rotear
        pro avatar-chief rodar o workflow completo primeiro.

    - step: 2
      name: "Identificar nível de consciência (1-5)"
      description: |
        Com base no Bloco 9 (tentativas), Bloco 10 (linguagem) e Bloco 8
        (objeções), classificar:
        - Nível 1: Inconsciente do problema
        - Nível 2: Consciente do problema, inconsciente de solução
        - Nível 3: Consciente de solução, inconsciente do produto específico
        - Nível 4: Consciente do produto, não convencido
        - Nível 5: Mais consciente, só precisa de razão final

        Nível determina estrutura de headline, comprimento de copy, ângulo
        de entrada e tipo de prova a usar. Essa informação é crítica pro
        S.C.A.L.E. construir a oferta certa.

    - step: 3
      name: "Preencher os 18 campos"
      description: |
        Usando template resumo-scale-tmpl.md, preencher:

        1. Dor central (destilada do Bloco 4.1-4.3)
        2. Dor oculta (destilada do Bloco 4.5 + 4.6)
        3. Desejo central (destilado do Bloco 5.1-5.3)
        4. Desejo oculto (destilado do Bloco 5.7)
        5. Urgência (o que torna agora diferente, normalmente do Bloco 6)
        6. Medos (3 bullets, top 3 do Bloco 6)
        7. Autossabotagem (padrão dominante do Bloco 7)
        8. Objeções (3 bullets, top 3 do Bloco 8)
        9. Frustrações (3 bullets, cenas concretas do Bloco 4.2)
        10. Linguagem que ressoa (5 frases do Bloco 10 que mais aparecem)
        11. Linguagem a evitar (3 termos do Bloco 8 que ele rejeita)
        12. Gatilhos de confiança (3 provas do Bloco 9)
        13. Gatilhos de decisão (3 catalisadores do Bloco 11)
        14. Inimigo (pessoa/sistema/ideia do Bloco 12.48)
        15. Cenário ideal (1 parágrafo do Bloco 12.50)
        16. Motivo real de compra (do Bloco 1 e Bloco 5.7)
        17. Janela emocional (do Bloco 11 e subcamada 10 do Bloco 13)
        18. Abordagem ideal (tom, estilo, canal, densidade, prova)

    - step: 4
      name: "Validação cruzada"
      description: |
        Confirmar que:
        - Campo 16 (motivo real) é DIFERENTE do campo 3 (desejo central declarado)
        - Campo 10 (linguagem que ressoa) vem do Bloco 10 LITERAL, não inventado
        - Campo 17 (janela emocional) tem cena concreta, não genérico
        - Campo 18 (abordagem ideal) alinha com nível de consciência identificado

    - step: 5
      name: "Exportar arquivo separado"
      description: |
        Salvar como resumo-scale.md (ou nome customizado do usuário) em formato
        pronto pra /offer-creator consumir. Incluir no topo:
        - Data
        - Produto
        - Nível de consciência
        - Link pro dossiê completo (se aplicável)

  output_example: |
    # Pacote S.C.A.L.E., [Nome do Avatar]

    **Data:** 2026-04-16
    **Produto:** Mentoria Escritório Contábil 2.0
    **Nível de Consciência:** 3 (Consciente da Solução)
    **Dossiê completo:** dossie-carlos-contador-v1.md

    ---

    ## 1. Dor Central
    Cobra R$ 300 por fechamento contábil aos 48 anos, com 23 anos de CRC,
    e vê clientes de 6 anos migrando pra contabilidade online por R$ 180.

    ## 2. Dor Oculta
    Sente inveja do irmão advogado que sempre foi "o que deu mais certo", e
    sente vergonha profunda dessa inveja.

    ## 3. Desejo Central
    Voltar a faturar R$ 40k/mês como em 2015, sem precisar virar influencer
    ou postar vídeos no Instagram.

    ## 4. Desejo Oculto
    Ver o irmão advogado, em conversa casual, reconhecer que "contabilidade
    também pode dar certo".

    ## 5. Urgência
    Filho de 16 anos está escolhendo curso nos próximos 12 meses. Se o pai não
    provar que contabilidade é profissão viva, o filho escolhe outra carreira
    por causa dele.

    ## 6. Medos
    - Ser visto como obsoleto pelos próprios filhos
    - Perder o último cliente grande (R$ 1.200/mês, 8 anos)
    - Ter que admitir pra esposa que o escritório está afundando

    ## 7. Autossabotagem
    Perfeccionismo defensivo: consome 10h/semana de conteúdo sobre precificação
    e marketing contábil mas nunca aplica, "porque ainda não tá totalmente certo".

    ## 8. Objeções
    - "Esses cursos de marketing pra contador são de quem não sabe contabilidade"
    - "Eu não vou virar influencer aos 48 anos"
    - "Já tentei consultoria em 2023, R$ 3.600 no vento"

    ## 9. Frustrações
    - Negociar R$ 20 de desconto no valor de R$ 280 com cliente de 6 anos
    - Ver contador do CRC regional postando resultado no Instagram semanalmente
    - Filho não perguntar mais sobre o trabalho do pai no jantar

    ## 10. Linguagem que Ressoa (frases literais do avatar)
    - "contador que ganha bem sem virar influencer"
    - "precificação que respeita o cliente antigo"
    - "método pra quem prefere ficar nos bastidores"
    - "passo a passo de verdade, não só teoria"
    - "contabilidade séria com faturamento sério"

    ## 11. Linguagem a Evitar
    - "transformação" (soa messiânico)
    - "liberdade financeira" (soa pirâmide)
    - "mude sua vida em 30 dias" (trava análise na hora)

    ## 12. Gatilhos de Confiança
    - Depoimento de outro contador 45+ que aplicou e manteve sobriedade
    - Autoridade com CRC ativo e registro (não só "empresário digital")
    - Método que permita não aparecer em rede social

    ## 13. Gatilhos de Decisão
    - Garantia de 15 dias (não 7, 7 parece "não dá tempo")
    - Primeira aula focada em precificação (dor imediata)
    - Link direto pra suporte humano, não chatbot

    ## 14. Inimigo
    Narrativa de que "contabilidade tradicional morreu". Culpa (silenciosamente)
    o irmão advogado pela comparação implícita que pesa desde os 19 anos.

    ## 15. Cenário Ideal (1 parágrafo)
    1 ano depois, Carlos reposicionou o escritório pra atender PMEs faturando
    R$ 300k+/mês, cobra R$ 1.500 a R$ 2.500 por cliente, tem 12 clientes ativos,
    faturamento líquido R$ 22k. Parou de aceitar MEI de R$ 300. Contratou auxiliar.
    No churrasco de dezembro, o sobrinho advogado de 19 anos perguntou a ele
    sobre "abrir escritório contábil depois da faculdade". O irmão ouviu. Ninguém
    comentou, mas Carlos viu.

    ## 16. Motivo Real de Compra
    Provar em silêncio, ao pai falecido e ao irmão vivo, que a escolha aos
    19 anos por contabilidade não foi erro.

    ## 17. Janela Emocional
    Sexta à noite, depois de fechar mais um cliente de R$ 280 com atraso
    de 40 dias. Abre o extrato, vê que vai precisar pedir adiantamento ao sócio
    de novo. Nessa janela, uma mensagem com "contador 48 anos que saiu do R$ 300
    pro R$ 2.000 sem virar influencer" converte.

    ## 18. Abordagem Ideal
    - **Tom:** Direto, sem hype, respeitoso com a profissão
    - **Estilo:** Linguagem contábil técnica misturada com narrativa de crise
      de meia-idade profissional
    - **Canal:** LinkedIn + YouTube + email longo. Evitar TikTok
    - **Densidade:** Média-alta. Aguenta texto longo se concreto. Não aguenta
      vídeo de 40 min "puro storytelling"
    - **Prova:** Par similar + autoridade técnica + método aplicável sem
      exposição pública

  acceptance_criteria:
    - "18 campos preenchidos"
    - "Nível de consciência identificado (1-5)"
    - "Campos 10, 15, 17 com linguagem/cena concreta"
    - "Campo 16 DIFERENTE do campo 3"
    - "Campo 18 alinhado com nível de consciência"
    - "Arquivo exportado com nome e metadados"

  veto_conditions:
    - "Nível de consciência ausente → VETO"
    - "Campo 16 igual ao campo 3 → VETO (motivo real tem que ser diferente do declarado)"
    - "Linguagem que ressoa inventada (não vem do Bloco 10) → VETO"
    - "Cenário ideal genérico (sem nome, sem cena) → VETO"

  handoff:
    on_complete: "Arquivo resumo-scale.md pronto pra alimentar /offer-creator (S.C.A.L.E.)"
    deliverable: "resumo-scale.md com 18 campos + metadados"
```

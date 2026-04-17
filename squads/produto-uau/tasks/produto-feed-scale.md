# Produto Feed SCALE

```yaml
task:
  task_name: "Exportar Pacote Pronto pro S.C.A.L.E."
  status: pending
  responsible_executor: produto-chief
  execution_type: Agent
  estimated_time: "15 min"
  elicit: false

  input:
    - "Spec completa do produto (produto-spec-tmpl.md preenchido)"
    - "UAU Matrix (uau-matrix-tmpl.md preenchido)"
    - "ERRC Grid (errc-grid-tmpl.md preenchido)"

  output:
    - "Pacote SCALE (templates/pacote-scale-tmpl.md preenchido)"
    - "Formato pronto pra input no offer-creator (S.C.A.L.E.)"

  action_items:

    - step: 1
      name: "Validar pré-requisitos"
      description: |
        Confirmar que as 3 coisas existem e estão preenchidas:
        1. Spec do produto
        2. UAU Matrix (score >= 70%)
        3. ERRC Grid completo

        Se não, VETO, voltar pra fase correta.

    - step: 2
      name: "Extrair Dream Outcome"
      description: |
        Do Spec + Value Equation:
        - Métrica específica com prazo
        - Dimensão emocional
        - Dimensão social

    - step: 3
      name: "Extrair Probabilidade"
      description: |
        Do UAU Matrix + Spec:
        - Lista de provas (cases, dados, demonstrações)
        - Mecanismo único (nome + passos)
        - Credenciais do criador

    - step: 4
      name: "Extrair Tempo"
      description: |
        Do Value Equation:
        - Tempo total de entrega
        - Quick win em X dias
        - Milestones intermediários

    - step: 5
      name: "Extrair Esforço"
      description: |
        Do Delivery Cubes:
        - Carga semanal esperada
        - O que é done-for-you
        - O que é done-with-you
        - O que é DIY (feito pelo aluno)

    - step: 6
      name: "Listar Delivery Cubes (Stack de Valor)"
      description: |
        Lista completa do que o cliente recebe.
        IMPORTANTE, aqui é só produto. S.C.A.L.E. vai empilhar bônus, precificar, garantir.

    - step: 7
      name: "Escrever Flags pro S.C.A.L.E."
      description: |
        Notas pro offer-creator:
        - Tipo de produto (infoproduto, mentoria, SaaS, serviço, híbrido)
        - Categoria proposta (do ERRC)
        - One-liner (do positioning)
        - Mecanismo (do Schwartz)
        - Attractive Character (do Brunson)

  output_example: |
    ## Pacote SCALE, Aceleradora de Primeiro R$10k

    ### Tipo de produto
    Híbrido (Mentoria em grupo + Done-with-you na semana 1)

    ### Categoria proposta
    Aceleradora done-with-you de Afiliado (nova categoria via ERRC)

    ### One-liner
    "Para ex-funcionários que já tentaram ser afiliados e desistiram,
    a Aceleradora de Primeiro R$10k é o programa done-with-you que faz
    sua primeira campanha lucrativa em 7 dias."

    ### Mecanismo Único
    **Nome:** Método 80/20 Invertido
    **Passos:** Diagnóstico de Alocação → Rotação → Aceleração → Consolidação

    ### Attractive Character
    - Backstory, [3-4 min]
    - Flaws, [lista]
    - Polarity, "Afiliado não é creator, é empresário de tráfego" / "Coach de coach é piada"
    - Character, The Reporter

    ---

    ### Value Equation Pronta pro SCALE

    **Dream Outcome:**
    - Métrica, primeiro R$10k em 60 dias
    - Emocional, segurança de dormir sabendo que conta bate
    - Social, "saiu do aluguel do chefe"

    **Probabilidade (provas):**
    - Case A, aluno X chegou em R$12k em 45 dias (prova por case)
    - Case B, Y alunos da turma piloto, N% atingiram (prova por dado)
    - Campanha feita ao vivo na semana 1 (prova por demonstração)
    - Mecanismo único (Método 80/20 Invertido)

    **Tempo:**
    - Total, 60 dias
    - Quick win, 7 dias (1ª campanha rodando)
    - Milestone 14d, primeira venda
    - Milestone 30d, R$3k
    - Milestone 60d, R$10k

    **Esforço:**
    - Carga semanal, 10h/semana
    - Done-for-you, configuração de conta, revisão de copy, setup inicial
    - Done-with-you, criação de campanhas (semana 1, juntos)
    - DIY, rotina de acompanhamento diário de métricas (15min/dia)

    ---

    ### Stack de Valor (Delivery Cubes)
    1. 4 módulos semanais com 3 aulas cada (12 aulas)
    2. Semana 1 done-with-you (campanha criada junto)
    3. 8 lives semanais (2 por semana)
    4. Revisão 1:1 semanal (nicho + copy + campanha)
    5. Dashboard com alertas automáticos
    6. Planilha Única do Afiliado (template)
    7. Grupo de 10 alunos/turma (intimidade)
    8. Certificado FÍSICO de Primeiro R$10k

    ---

    ### Flags pro S.C.A.L.E.

    **Itens pra SCALE decidir (não é produto, é oferta):**
    - Preço
    - Stack de bônus adicional (pode adicionar bônus externos, SCALE que decide)
    - Garantia (se aplicável, dinheiro de volta / continua até atingir / etc)
    - Escassez (10 vagas, janela de 7 dias, etc)
    - Parcelamento
    - Order bump / upsell

    **Recomendações do produto-uau pro SCALE:**
    - Ticket sugerido (baseado em categoria e delivery), R$3k-8k
    - Garantia natural, "continuamos juntos até você atingir R$10k (extensão gratuita)"
    - Urgência natural, 10 vagas (limite real de turma)

  acceptance_criteria:
    - "Pacote SCALE preenchido com todas as seções"
    - "Value Equation completa nos 4 eixos"
    - "Stack de valor listado (delivery cubes)"
    - "Flags pro S.C.A.L.E. escritas"
    - "One-liner e Attractive Character exportados"

  veto_conditions:
    - "Algum pré-requisito (spec, UAU matrix, ERRC) ausente, VETO"
    - "UAU score < 70%, VETO, voltar pro inject-uau"

  handoff:
    on_complete: "Envia pro offer-creator (S.C.A.L.E.) via comando `/offer-creator *create` com o pacote anexo"
    deliverable: "Pacote SCALE pronto pra virar oferta"
```

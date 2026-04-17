# Produto First Draft

```yaml
task:
  task_name: "Gerar Primeiro Rascunho Executável (MVP / Esqueleto)"
  status: pending
  responsible_executor: produto-chief
  execution_type: Agent
  estimated_time: "30-60 min"
  elicit: false

  input:
    - "Spec do produto (produto-spec-tmpl.md)"
    - "UAU Matrix (uau-matrix-tmpl.md)"
    - "ERRC Grid (errc-grid-tmpl.md)"
    - "Tipo de produto (infoproduto, mentoria, SaaS, serviço, híbrido)"

  output:
    - "First Draft preenchido (templates/first-draft-tmpl.md)"
    - "MVP testável em 7 dias com 1 cliente real"

  action_items:

    - step: 1
      name: "Identificar tipo de produto"
      description: |
        Baseado no tipo, carregar a seção correta do first-draft-tmpl.md.

    - step: 2
      name: "Por tipo, gerar rascunho"
      description: |
        **INFOPRODUTO:**
        - Lista de módulos (4-6, máximo)
        - Lista de aulas por módulo (3-4, máximo)
        - Título de cada aula
        - Objetivo de aprendizado por aula
        - Entregável por aula (o que o aluno TEM ao final)
        - Formato (vídeo, PDF, template, live)

        **MENTORIA:**
        - Framework central (já vem do Schwartz como mecanismo único)
        - Agenda semanal (quantas chamadas, duração, conteúdo)
        - Tópicos por semana
        - Rituais do programa (início, meio, fim)
        - Entregável por semana

        **SAAS:**
        - Lista de features (MVP, máximo 5 features core)
        - User stories por feature ("Como [persona], eu quero [ação] pra [outcome]")
        - Fluxo principal do usuário (onboarding → job primário → retenção)
        - Métricas de sucesso
        - Stack tecnológica sugerida (opcional)

        **SERVIÇO:**
        - Entregáveis (lista concreta do que o cliente recebe)
        - SLA (prazo, revisões, canais)
        - Processo (onboarding, execução, entrega, pós)
        - Time necessário (quem faz o quê)
        - Ferramentas usadas

        **HÍBRIDO:**
        - Combina acima (ex, infoproduto + mentoria ou SaaS + serviço)
        - Clarifica o que é cada parte
        - Como as partes se conversam

    - step: 3
      name: "Adicionar camada UAU"
      description: |
        Pra cada elemento do rascunho, aplicar os 6 injetores da UAU Matrix:
        - Onde injetar o mecanismo único?
        - Onde injetar quick win (tempo impossível)?
        - Onde injetar bônus surpresa?
        - Onde garantir resultado específico?
        - Onde aplicar formato inesperado?
        - Onde aparece o anti-método?

    - step: 4
      name: "Teste de 7 dias"
      description: |
        Definir, qual a versão MÍNIMA testável com 1 cliente real em 7 dias?
        - Não é o produto final, é o MVP
        - Foco em validar a promessa central
        - Ex, se o produto é Aceleradora, em 7 dias roda 1 done-with-you com 1 cliente

    - step: 5
      name: "Lista de próximos passos"
      description: |
        - O que precisa criar antes de abrir venda
        - O que pode ser criado depois (conforme turma entra)
        - Dependências externas (plataforma, gravação, time)

  output_example: |
    ## First Draft, Aceleradora de Primeiro R$10k (Tipo Híbrido)

    ### Estrutura Geral
    - 60 dias
    - 10 alunos/turma
    - Modalidade, mentoria em grupo + done-with-you semana 1

    ### Componente 1, Módulos (infoproduto leve)

    | Módulo | Semana | Aulas | Entregável |
    |--------|--------|-------|------------|
    | 1. Diagnóstico | 1 | 3 aulas | Campanha rodando (done-with-you) |
    | 2. Rotação | 2 | 3 aulas | Automação de conteúdo |
    | 3. Aceleração | 3-4 | 4 aulas | Campanha escalada |
    | 4. Consolidação | 5-8 | 2 aulas | Processo auto-sustentável |

    ### Componente 2, Mentoria (ao vivo)

    Agenda semanal:
    - Terça 19h, Live de ensino (1h)
    - Quinta 19h, Live de revisão 1:1 (2 alunos por live, rotativa)
    - Sábado 10h, Accountability circle (30min, grupo todo)

    ### Componente 3, Done-With-You (semana 1)

    - Dia 1, Onboarding (nicho, posicionamento, conta configurada)
    - Dias 2-4, Criação de campanha JUNTO (você + aluno, live shared screen)
    - Dia 5, Lançamento da campanha
    - Dias 6-7, Otimização inicial

    ### Entregáveis concretos (Delivery Cubes)
    1. Campanha rodando na semana 1
    2. Planilha Única do Afiliado
    3. Dashboard com alertas
    4. Acesso ao fórum privado (resposta em 2h)
    5. Certificado FÍSICO de Primeiro R$10k
    6. 50 templates de copy testadas
    7. Checklist de nicho validado
    8. Revisão 1:1 semanal

    ### Camada UAU Injetada

    - **Mecanismo oculto:** Método 80/20 Invertido (batiza tudo)
    - **Tempo impossível:** 1ª campanha em 7 dias (quick win)
    - **Bônus surpresa:** certificado FÍSICO no R$10k
    - **Resultado específico:** sai com campanha rodando, não "aprendendo"
    - **Formato inesperado:** Aceleradora, não curso nem mentoria
    - **Anti-método:** "Pare de criar conteúdo"

    ### MVP Testável (7 dias)
    - Escolher 1 aluno piloto
    - Rodar dia 1 ao 7 (onboarding + done-with-you)
    - Meta, aluno sai do dia 7 com campanha rodando
    - Se falhar, ajusta antes de abrir turma

    ### Próximos Passos
    **Antes de abrir venda:**
    - Criar Planilha Única do Afiliado
    - Gravar 12 aulas (4 módulos × 3 aulas)
    - Criar fórum privado (Discord ou Circle)
    - Desenhar dashboard com alertas

    **Pode criar em andamento:**
    - 50 templates de copy (cria conforme turma pede)
    - Certificado físico (cria quando aluno atinge)

    **Dependências:**
    - Plataforma de vídeo (Kiwify, Hotmart, Klickart)
    - Plataforma de comunidade (Discord grátis ou Circle pago)
    - Gestor de suporte (se turma > 10, precisa)

  acceptance_criteria:
    - "First Draft por tipo preenchido"
    - "6 injetores de UAU injetados no rascunho"
    - "MVP testável em 7 dias definido"
    - "Lista de próximos passos com dependências"

  veto_conditions:
    - "MVP não é testável em 7 dias, é escopo grande demais"
    - "Rascunho sem camada UAU, volta pra UAU injection"

  handoff:
    on_complete: "Produto pronto pra rodar `*feed-scale` ou testar MVP"
    deliverable: "First Draft executável"
```

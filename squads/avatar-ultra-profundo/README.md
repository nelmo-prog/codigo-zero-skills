# Avatar Ultra Profundo Squad

## Visão Geral

Squad de elite para construção de dossiês psicológicos ultra profundos de avatares (clientes ideais). Cada agente é clonado de uma mente real com metodologia documentada, vocabulário próprio e resultados comprovados em pesquisa de audiência, copy e oferta.

O output NÃO é um "persona de marketing genérico". É um dossiê psicológico profundo que revela o motivo REAL de compra, autossabotagem, linguagem crua, medos silenciosos e desejos ocultos, tudo pronto para alimentar a criação de oferta via S.C.A.L.E./Hormozi.

## Propósito

Construir avatares com profundidade emocional de entrevista terapêutica, crueza de conversa de bar, rigor de pesquisa qualitativa e utilidade comercial de copywriter de resposta direta. O resultado é um mapa completo de 14 blocos, 50 camadas e 10 subcamadas de autossabotagem que servem como insumo direto para oferta, copy, anúncios, funil e vendas.

## Quando Usar Este Squad

- Construir avatar de cliente antes de criar oferta
- Diagnosticar por que a oferta atual não converte
- Encontrar a linguagem real que o cliente usa (conversa consigo, WhatsApp, Google)
- Identificar o motivo real de compra (não o declarado)
- Mapear objeções, autossabotagem e ganhos secundários
- Alimentar o squad S.C.A.L.E. (criador de ofertas) com dossiê completo
- Reescrever copy e VSL usando a voz do próprio avatar

## Agentes

| Agente | Mente | Tier | Domínio |
|-------|------|------|--------|
| **avatar-chief** | *(orquestrador)* | 0 | Sintetiza 14 blocos, compila dossiê, exporta pacote S.C.A.L.E. |
| **robert-cialdini** | Robert Cialdini | 0 | Blocos 1 e 11, Raio X executivo, Mecânica de decisão |
| **daniel-kahneman** | Daniel Kahneman | 0 | Blocos 6 e 11, Medos/contradições, Sistema 1 vs 2 |
| **brene-brown** | Brené Brown | 1 | Blocos 4 e 6, Camadas de dor, vergonha, vulnerabilidade |
| **jay-abraham** | Jay Abraham | 1 | Bloco 5, Camadas de desejo, valor percebido |
| **clayton-christensen** | Clayton Christensen | 1 | Blocos 2, 3 e 9, Identidade, contexto, JTBD, tentativas |
| **eugene-schwartz** | Eugene Schwartz | 1 | Blocos 10 e 14, Linguagem real, níveis de consciência, resumo S.C.A.L.E. |
| **alex-hormozi** | Alex Hormozi | 2 | Blocos 7, 8 e 13, Autossabotagem, crenças, objeções, subcamadas |

## Workflows

| Workflow | Descrição | Fases |
|----------|-------------|--------|
| `wf-avatar-from-zero` | Dossiê completo dos 14 blocos | 5 fases: Diagnose, Create, Review, Feed S.C.A.L.E., Handoff |

## Tasks

| Task | Agente | Propósito |
|------|-------|---------|
| `avatar-diagnose-input` | avatar-chief | Clarifica briefing antes de rodar (nicho, produto, público, canal, ticket) |
| `avatar-deep-dossie` | avatar-chief | Executa os 14 blocos completos com rotação de agentes |
| `avatar-feed-scale` | eugene-schwartz | Extrai Bloco 14 (18 campos) pro S.C.A.L.E. |
| `avatar-linguagem-crua` | eugene-schwartz | Extrai Bloco 10, as 25+ frases categorizadas |
| `avatar-review-audit` | avatar-chief | Autoauditoria de profundidade, humanidade, motivo real |

## Templates

| Template | Propósito |
|----------|---------|
| `input-avatar-tmpl.md` | Briefing inicial (nicho, produto, público, canal, ticket, concorrência) |
| `dossie-avatar-tmpl.md` | Dossiê completo dos 14 blocos |
| `linguagem-crua-tmpl.md` | 25+ frases categorizadas (conversa consigo, WhatsApp, Google, objeções) |
| `resumo-scale-tmpl.md` | 18 campos do Bloco 14 pronto pro S.C.A.L.E. |

## Checklists

- `avatar-depth-checklist.md`, 8 perguntas de autoauditoria (humanidade, profundidade, motivo real)
- `avatar-completeness-checklist.md`, verifica 14 blocos, 50 camadas, 10 subcamadas, 25+ frases

## Data

- `avatar-methodology.md`, metodologia completa (14 blocos, 50 camadas, 10 subcamadas, marcação de confiança fato/inferência/hipótese)
- `elite-minds-reference.md`, referências bibliográficas de cada mente (livros, papers, frameworks)

## Como Usar

### Dossiê Completo do Zero
```
/avatar-ultra-profundo:create
```

### Clarificar Briefing Primeiro
```
/avatar-ultra-profundo:diagnose
```

### Extrair Apenas o Pacote S.C.A.L.E.
```
/avatar-ultra-profundo:feed-scale
```

### Extrair Apenas a Linguagem Crua
```
/avatar-ultra-profundo:linguagem
```

### Auditar um Dossiê Existente
```
/avatar-ultra-profundo:review
```

## Sequência Lógica

```
Diagnose Input  ->  Deep Dossie (14 blocos)  ->  Review Audit  ->  Feed S.C.A.L.E.
     (1)                    (2)                       (3)              (4)
  avatar-chief      rotação 7 agentes           avatar-chief     eugene-schwartz
                    + avatar-chief sintetiza
```

## Regras Globais

- Português brasileiro com ortografia correta (acentos, cedilhas obrigatórios)
- NUNCA usar travessão/dash (—), sempre vírgula no meio de frases
- Nada genérico, nada de "cliente busca resultados", só linguagem crua humana
- Autossabotagem é força central da decisão, não detalhe periférico
- Marcar confiança em cada insight: FATO, INFERÊNCIA ou HIPÓTESE
- Dossiê precisa passar no teste "isso parece um ser humano real?"

## Integração

O output deste squad alimenta diretamente:
- `/offer-creator` (S.C.A.L.E.), via Bloco 14
- `/copy-squad` (VSL, LP, ads), via Bloco 10
- `/squad-ads` (Meta e Google), via Blocos 4, 5, 7, 10
- `/squad-launch` (lançamento), via Blocos 6, 9, 11

## Estrutura do Pack

```
squads/avatar-ultra-profundo/
├── agents/
│   ├── avatar-chief.md
│   ├── robert-cialdini.md
│   ├── daniel-kahneman.md
│   ├── brene-brown.md
│   ├── jay-abraham.md
│   ├── clayton-christensen.md
│   ├── eugene-schwartz.md
│   └── alex-hormozi-avatar.md
├── checklists/
│   ├── avatar-depth-checklist.md
│   └── avatar-completeness-checklist.md
├── config.yaml
├── data/
│   ├── avatar-methodology.md
│   └── elite-minds-reference.md
├── README.md
├── squad.yaml
├── tasks/
│   ├── avatar-diagnose-input.md
│   ├── avatar-deep-dossie.md
│   ├── avatar-feed-scale.md
│   ├── avatar-linguagem-crua.md
│   └── avatar-review-audit.md
├── templates/
│   ├── input-avatar-tmpl.md
│   ├── dossie-avatar-tmpl.md
│   ├── linguagem-crua-tmpl.md
│   └── resumo-scale-tmpl.md
└── workflows/
    └── wf-avatar-from-zero.yaml
```

---

**Construído com profundidade emocional, crueza e utilidade comercial. O dossiê é insumo de oferta, não peça de portfólio.**

_Versão: 1.0.0_
_Compatível com: AIOS v4+_
_Imersão Código ZERO, 16-17/05/2026_

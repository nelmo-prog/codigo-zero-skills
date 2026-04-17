# Produto UAU Squad

## Visão Geral

Fábrica de produtos com metodologia híbrida que gera o fator UAU no aluno. Preenche o buraco entre Avatar (quem) e Oferta S.C.A.L.E. (como vender), criando o que o cliente de fato recebe.

Usa 5 frameworks comprovados, JTBD (Christensen), Value Equation (Hormozi), Unique Mechanism (Schwartz), Blue Ocean ERRC (Kim e Mauborgne) e Simplicity Principle (Jobs), costurados por 6 Injetores de UAU obrigatórios.

## Distinção crítica: PRODUTO vs OFERTA

- **PRODUTO** = o que o cliente recebe (módulos, features, deliverables, formato, stack de valor)
- **OFERTA** = como é vendido (preço, bônus, garantia, escassez, empilhamento visual, copy, stack visual)

`produto-uau` cuida só da parte PRODUTO. O squad `offer-creator` (S.C.A.L.E.) cuida da parte OFERTA. Este squad entrega o pacote pronto pro S.C.A.L.E. transformar em oferta irresistível.

## Quando usar este squad

- Aluno tem avatar definido mas não sabe qual produto construir
- Aluno tem ideia de produto mas falta mecanismo único, falta UAU
- Aluno quer auditar produto existente (injetores de UAU, ERRC, fit com avatar)
- Aluno precisa decidir formato (infoproduto, mentoria, SaaS, serviço, híbrido)
- Aluno quer primeiro rascunho executável (MVP, esqueleto) antes de vender

## Fluxo no Código ZERO

```
Fase 1. Mercado (L.U.C.R.O)
     ↓
Fase 2. Avatar (avatar-ultra-profundo) [Bloco 14 Resumo SCALE]
     ↓
Fase 3. PRODUTO (produto-uau) ← VOCÊ ESTÁ AQUI
     ↓
Fase 4. Oferta (offer-creator / S.C.A.L.E.)
     ↓
Fase 5. Copy e funil
```

## Agentes

| Agente | Mente | Tier | Domínio |
|--------|-------|------|---------|
| **produto-chief** | *(orquestrador)* | 0 | Rota, coordena, audita os 6 injetores de UAU, compila spec |
| **clayton-christensen** | Clayton Christensen | 1 | Jobs-to-be-Done, descobre o "job" real que o avatar contrata |
| **alex-hormozi-produto** | Alex Hormozi | 1 | Value Equation, Delivery Cubes, stack de entregáveis |
| **eugene-schwartz-produto** | Eugene Schwartz | 1 | Unique Mechanism com nome próprio |
| **kim-mauborgne** | W. Chan Kim e Renée Mauborgne | 1 | Blue Ocean ERRC Grid, cria categoria nova |
| **steve-jobs** | Steve Jobs | 1 | Simplicity, UAU, remoção brutal |
| **russell-brunson** | Russell Brunson | 2 | Opportunity Switch, produto como nova oportunidade |
| **april-dunford-produto** | April Dunford | 2 | Positioning do produto, categoria onde vence |

## 5 Frameworks (nada inventado)

| Framework | Autor | Para que serve |
|-----------|-------|----------------|
| Jobs-to-be-Done | Clayton Christensen | Descobre o "job" real que o cliente contrata o produto pra fazer |
| Value Equation | Alex Hormozi, $100M Offers | Valor = (Sonho × Probabilidade) ÷ (Tempo × Esforço) |
| Unique Mechanism | Eugene Schwartz, Breakthrough Advertising | O "como" único, mecanismo batiza o produto |
| Blue Ocean ERRC | Kim e Mauborgne | Eliminar, Reduzir, Aumentar, Criar, cria categoria nova |
| Simplicity Principle | Steve Jobs / Ken Segall, Insanely Simple | UAU nasce da remoção, foco brutal |

## 6 Injetores de UAU (obrigatórios)

1. **Mecanismo único oculto** que resolve dor que o avatar nem sabia que tinha (Schwartz)
2. **Entrega em tempo impossível**, redução brutal de Tempo na Value Equation (Hormozi)
3. **Bônus surpresa** que vale mais que o core (stacking, Popeil / Hormozi)
4. **Resultado específico garantido**, boost de Probabilidade (sai com Y pronto, não aprende X)
5. **Formato inesperado** (não é curso, é fábrica / não é mentoria, é replicação assistida)
6. **Anti-método / Opportunity Switch** (Brunson), vende o contrário do senso comum

## Workflows

| Workflow | Descrição | Fases |
|----------|-----------|-------|
| `wf-produto-from-zero` | Criação completa de produto do zero | 7 fases: Discovery → JTBD → Mecanismo → Value Equation → ERRC → UAU → First Draft |
| `wf-produto-audit` | Auditoria de produto existente | 3 fases: Coletar → Auditar (6 injetores + ERRC + avatar) → Sintetizar |

## Tasks

| Task | Agente | Propósito |
|------|--------|-----------|
| `produto-diagnose-type.md` | produto-chief | Diagnostica tipo ideal (infoproduto, mentoria, SaaS, serviço, híbrido) |
| `produto-create-full.md` | produto-chief | Roda as 7 fases completas |
| `produto-inject-uau.md` | produto-chief | Auditoria dos 6 injetores em produto existente |
| `produto-feed-scale.md` | produto-chief | Exporta pacote pro S.C.A.L.E. |
| `produto-review.md` | produto-chief | Auditoria cruzada (vs concorrência, vs avatar, vs mercado) |
| `produto-first-draft.md` | produto-chief | Gera MVP / esqueleto executável |

## Templates

- `produto-spec-tmpl.md`, arquitetura completa do produto
- `uau-matrix-tmpl.md`, 6 injetores de UAU detalhados
- `errc-grid-tmpl.md`, 4 quadrantes Blue Ocean vs concorrência
- `pacote-scale-tmpl.md`, input direto pro S.C.A.L.E.
- `first-draft-tmpl.md`, template flexível por tipo de produto

## Checklists

- `uau-factor-checklist.md`, os 6 injetores de UAU estão presentes?
- `produto-viability-checklist.md`, escopo viável, avatar alinhado, mercado valida?
- `produto-completeness-checklist.md`, spec, UAU matrix, ERRC, pacote SCALE, first draft

## Data / Base de conhecimento

- `produto-methodology.md`, os 5 frameworks e os 6 injetores detalhados
- `product-types-guide.md`, guia de cada tipo de produto
- `elite-minds-reference.md`, bibliografia de cada mente

## Como usar

### Criar produto do zero (7 fases)
```
/produto-uau:produto-chief
*create
```

### Diagnosticar tipo ideal
```
/produto-uau:diagnose
```

### Auditar produto existente (injetores de UAU)
```
/produto-uau:inject-uau
```

### Alimentar o S.C.A.L.E.
```
/produto-uau:feed-scale
```

### Revisar produto (auditoria completa)
```
/produto-uau:review
```

### Ativar agente específico
```
/produto-uau:clayton-christensen   → Descobrir o job
/produto-uau:alex-hormozi-produto  → Value equation, cubos
/produto-uau:eugene-schwartz-produto → Mecanismo único
/produto-uau:kim-mauborgne         → Blue Ocean ERRC
/produto-uau:steve-jobs            → Simplicidade, UAU
/produto-uau:russell-brunson       → Opportunity Switch
/produto-uau:april-dunford-produto → Positioning do produto
```

## Sequência de criação

```
Discovery → JTBD → Mecanismo → Value Equation → ERRC → UAU Injection → First Draft
    (1)      (2)       (3)          (4)         (5)        (6)           (7)

          @clayton-  @eugene-    @alex-        @kim-      @steve-jobs   @produto-
          christensen schwartz   hormozi       mauborgne  +@russell-    chief
                                                          brunson       (compila)
                                                          +@april-
                                                          dunford
```

## Referências

- Christensen, Clayton, Competing Against Luck (2016), JTBD
- Hormozi, Alex, $100M Offers (2021), Value Equation e Delivery Cubes
- Schwartz, Eugene, Breakthrough Advertising (1966), Unique Mechanism
- Kim, W. Chan e Mauborgne, Renée, Blue Ocean Strategy (2005), ERRC Grid
- Segall, Ken, Insanely Simple (2012), Jobs e o princípio da simplicidade
- Brunson, Russell, Expert Secrets (2017), Opportunity Switch

---

_Version: 1.0.0_
_Compatible with: AIOS v4+_
_Criado para imersão Código ZERO (16-17/05/2026)_

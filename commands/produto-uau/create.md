---
description: Cria produto completo com 5 frameworks (JTBD, Value Equation, Unique Mechanism, Blue Ocean ERRC, Simplicity) + 6 injetores de UAU obrigatórios. Entrega spec + first draft + pacote SCALE.
---

# Produto UAU, Create

Roda o workflow `wf-produto-from-zero.yaml` do squad. 7 fases.

## Pré-requisitos (bloqueantes)
- `RESUMO-SCALE.md` do avatar (18 campos)
- `PRODUTO-TIPO.md` do diagnose (qual tipo)

Se falta algum, rode `/produto-uau:diagnose` primeiro.

## 7 Fases do Workflow

1. **Discovery**: inventário de expertise/recursos/avatar/mercado (chief)
2. **Job Discovery**: JTBD, por que avatar "contrata" o produto (Christensen)
3. **Unique Mechanism**: mecanismo proprietário com nome próprio (Schwartz)
4. **Value Equation**: maximizar Dream Outcome + Probabilidade, minimizar Tempo + Esforço (Hormozi)
5. **ERRC Grid**: Eliminar/Reduzir/Aumentar/Criar vs concorrência (Kim & Mauborgne)
6. **UAU Injection**: audita 6 injetores obrigatórios (Jobs/Brunson)
7. **First Draft**: gera primeiro rascunho executável do tipo escolhido

## 6 Injetores de UAU (auditados na Fase 6, todos obrigatórios)

1. Mecanismo único oculto (resolve dor que avatar nem sabia)
2. Entrega em tempo "impossível"
3. Bônus surpresa que vale mais que o core
4. Resultado específico garantido
5. Formato inesperado
6. Anti-método / Opportunity Switch

## Saídas (em `03-produto/`)

1. `PRODUTO-SPEC.md` — arquitetura completa (tipo, avatar, job, mecanismo, módulos, formato, prazo)
2. `UAU-MATRIX.md` — 6 injetores aplicados neste produto
3. `ERRC-GRID.md` — diferenciação vs concorrência
4. `PRIMEIRO-RASCUNHO.md` — MVP/esqueleto executável (infoproduto: módulos+aulas; SaaS: features+stories; mentoria: framework+agenda; serviço: entregáveis+SLA)
5. `PACOTE-SCALE.md` — input pronto pro S.C.A.L.E. virar oferta

## Próximo passo
Rode `/offer-creator` (S.C.A.L.E.) consumindo o `PACOTE-SCALE.md`.

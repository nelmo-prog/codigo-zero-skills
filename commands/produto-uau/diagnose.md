---
description: Diagnostica qual TIPO de produto cabe no contexto do aluno (infoproduto, mentoria, SaaS, serviço, híbrido) com base em expertise, recursos, avatar, mercado.
---

# Produto UAU, Diagnose Type

Roda a task `produto-diagnose-type.md` do squad. Antes de criar o produto, decide qual TIPO faz sentido.

## Pré-requisito (forte, não pular)
- `RESUMO-SCALE.md` do avatar (Fase 2 completa)
- `LUCRO-DIAGNOSTICO.md` do mercado (Fase 1 completa)

Se falta avatar, rode `/avatar-ultra-profundo:create` primeiro.

## 5 Tipos Possíveis

| Tipo | Quando Escolher |
|------|-----------------|
| **Infoproduto** (curso/e-book) | Conhecimento transferível, avatar prefere aprender sozinho, ticket R$47-R$1.997 |
| **Mentoria** (alta | grupo) | Transformação profunda, avatar precisa ser puxado, ticket R$2k-R$50k |
| **SaaS / App** | Problema recorrente, dor contínua, avatar pagaria mensalidade pra não pensar |
| **Serviço** (DFY) | Avatar não quer aprender, quer o resultado entregue |
| **Híbrido** | Combo de 2+ acima (ex: SaaS + mentoria, curso + serviço) |

## Perguntas Obrigatórias
1. Qual sua expertise/recursos disponíveis?
2. Seu avatar quer aprender, ser puxado, ou terceirizar?
3. Ticket médio que o mercado paga?
4. Você tem tempo pra entregar ao vivo ou precisa escalar?
5. Tem equipe ou solo?

## Saída: `PRODUTO-TIPO.md`
Tipo recomendado + justificativa + alternativas viáveis + próximos passos.

Alimenta input do `/produto-uau:create`.

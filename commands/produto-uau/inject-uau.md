---
description: Audita os 6 injetores de UAU num produto existente. Aponta quais estão ausentes ou fracos e propõe injeção específica.
---

# Produto UAU, Inject UAU

Roda a task `produto-inject-uau.md` do squad. Pra produto que JÁ EXISTE mas está morno (sem UAU).

## Pré-requisito
`PRODUTO-SPEC.md` existente (seja do `:create` ou produto legado importado).

## Fluxo
Cada um dos 6 injetores é auditado pelo agente responsável:

| Injetor | Auditor | Pergunta-chave |
|---------|---------|----------------|
| Mecanismo único oculto | Schwartz | Você tem um "como" proprietário com nome? |
| Tempo "impossível" | Hormozi | Em quanto tempo o cliente vê o primeiro resultado? Pode ser menor? |
| Bônus surpresa | Brunson | Tem algo que vale mais que o produto principal e o cliente recebe grátis? |
| Resultado garantido | Hormozi | A garantia é específica (métrica) ou genérica ("satisfação")? |
| Formato inesperado | Jobs | O formato é óbvio (curso, mentoria) ou tem um twist? |
| Opportunity Switch | Brunson | Vende o oposto do senso comum do mercado? |

## Saída: `UAU-AUDIT.md`
Nota 0-10 por injetor + sugestão específica de reforço/adição.

Se score total < 40/60, produto é "comoditizado" e precisa reinjeção completa (vira `:create` de novo).

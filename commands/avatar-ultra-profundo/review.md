---
description: Autoauditoria do dossiê do avatar. Valida profundidade, humanidade, revelação do motivo real de compra, autossabotagem mapeada. Retorna veredito PASS/REWORK por bloco.
---

# Avatar, Review (Autoauditoria)

Roda a task `avatar-review-audit.md` do squad. Aplica as 8 perguntas da autoauditoria do prompt mestre.

## Pré-requisito
`DOSSIE-COMPLETO.md` em `02-avatar/`.

## 8 Perguntas da Autoauditoria

1. Isso parece um ser humano real?
2. Isso está profundo ou ainda superficial?
3. Isso ajuda a vender melhor?
4. Isso ajuda a criar oferta depois?
5. Isso revela o motivo real de compra?
6. Isso trouxe tensões, vergonhas, desejos ocultos e objeções reais?
7. Isso mostrou como o avatar se sabota?
8. Isso mostrou como quebrar essa autossabotagem?

## Saída: `AVATAR-AUDIT.md`
Por bloco (1-14), nota PASS (profundo o suficiente) ou REWORK (voltar pro agente dono).

Se alguma resposta for "não", retorna o bloco pro agente específico aprofundar.

## Regras
Sem cortesia, sem "parabéns". Auditoria cruel. Melhor um REWORK agora que um avatar raso virando oferta rasa virando copy rasa virando campanha zero conversão.

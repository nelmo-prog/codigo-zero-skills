---
name: codigo-zero-flow
description: Orquestrador master da Imersão Código ZERO. Guia o aluno pelas 9 fases canônicas (Mercado→Avatar→Produto→Oferta→Copy→LP→Criativos→Campanhas→Lançamento), detecta fase atual, valida pré-requisitos, bloqueia pulos, chama skill canônica correta. Use quando o aluno perguntar "por onde começo?" ou quer orquestrar lançamento completo.
---

# Código ZERO Flow

Master orchestrator das 9 fases de criação de produto/lançamento.

## Quando Usar
- "Por onde começo meu lançamento?"
- "Quero criar meu primeiro produto na Imersão"
- "Estou perdido entre tantas skills, qual uso primeiro?"
- "Valida se posso pular pra fase X"

## Ordem Canônica (imutável)

| # | Fase | Skill canônica |
|---|------|----------------|
| 1 | Mercado | `/lucro:diagnose` |
| 2 | Avatar | `/avatar-ultra-profundo:create` |
| 3 | Produto | `/produto-uau:create` |
| 4 | Oferta | `/offer-creator` (S.C.A.L.E.) |
| 5 | Copy | `/copy-squad:*` |
| 6 | LP | `/design-squad:*` + `/tracking-conversion-pipeline` |
| 7 | Criativos | `/creative-squad` |
| 8 | Campanhas | `/squad-ads` + `/squad-google-ads` |
| 9 | Lançamento | `/squad-launch` |

## Regra Mestra
Multidão faminta antes do produto (Hormozi). Nunca avatar sem mercado. Nunca produto sem avatar. Nunca oferta sem produto.

## Distinção Crítica
- **PRODUTO** = o que o cliente recebe
- **OFERTA** = como é vendido

## Pasta Padrão de Projeto
`C:\Users\Ryzen 7\lancamentos\{projeto}\01-mercado\` ... `09-lancamento\`

## Comando
Implementação em `C:\Users\Ryzen 7\.claude\commands\codigo-zero-flow.md`

## Memória
Fluxo canônico salvo em `memory/project_codigo_zero_fluxo_canonico.md`

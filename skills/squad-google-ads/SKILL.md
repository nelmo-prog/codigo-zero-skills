---
name: squad-google-ads
description: "Orquestrador de campanhas Google Ads. Cria, analisa e otimiza campanhas Search, Shopping e PMax com um único comando. Pipeline: análise de negócio, keywords, RSA ads, targeting, negativas, performance. Tudo via API direta (google-ads-api Opteo), sem dashboard, sem CSV. Actions: criar campanha, analisar search terms, adicionar negativas, gerar RSA ads, pausar, ativar, ajustar budget, relatório Thomas. Topics: Google Ads, campanha, Search, PMax, Shopping, keywords, negativas, search terms, RSA, headline, description, Quality Score, ROAS, CPA, budget, bid strategy."
---

# Squad Google Ads - Orquestrador de Campanhas

Cria, analisa e otimiza campanhas Google Ads com um único comando. Tudo via API direta, sem interface gráfica, sem CSV, sem dashboard.

---

## Quando Ativar

- "Cria campanha no Google Ads para X"
- "Analisa os search terms da campanha Y"
- "Adiciona negativas na campanha Z"
- "Gera novos anúncios RSA para a campanha W"
- "Analisa a performance no Google Ads"
- "Pausa a campanha X no Google"
- "Relatório Thomas completo"
- Qualquer pedido envolvendo criação, gestão ou otimização de campanhas Google Ads

---

## Configuração (Credenciais)

### Conta Nelmo Ricalde (padrão)
- **Customer ID:** 997-159-9900
- **Developer Token:** GOOGLE_ADS_DEVELOPER_TOKEN no .env.local do Zuvora
- **Client ID/Secret:** GOOGLE_ADS_CLIENT_ID / GOOGLE_ADS_CLIENT_SECRET no .env.local
- **Refresh Token:** GOOGLE_ADS_REFRESH_TOKEN no .env.local
- **Login Customer ID:** GOOGLE_ADS_LOGIN_CUSTOMER_ID no .env.local

### Para outra conta (mentorado)
Perguntar: Customer ID, Developer Token, Client ID, Client Secret, Refresh Token.

---

## Acesso à API (Como Executar)

Todas as operações usam as funções TypeScript do Zuvora. Para executar via Claude Code:

```typescript
// Importar funções do Zuvora
import { createGoogleCampaignOnApi, createRsaAd, addNegativeKeywordsToCampaign, listAdGroups, listAdsInAdGroup } from "C:/Users/Ryzen 7/zuvora/src/lib/services/google-campaign-creator"
import { getGoogleCampaignMetrics, getGoogleKeywords, getGoogleSearchTerms, validateGoogleCredentials } from "C:/Users/Ryzen 7/zuvora/src/lib/services/google-ads-api"
```

Ou via GAQL direto com curl (para consultas rápidas, usar as funções TS é preferível).

As credenciais estão em `C:\Users\Ryzen 7\zuvora\.env.local`.

---

## Pipeline de Criação (4 Fases)

### FASE 1 — CONTEXTO (perguntas obrigatórias)

**REGRA DE CADEIA ALIMENTAR (verificar ANTES de perguntar):**
Se o projeto tem pasta `lancamentos/{projeto}/`, consumir outputs existentes:
- `02-avatar/RESUMO-SCALE.md` → substitui pergunta 5 (avatar já existe com 50 camadas)
- `02-avatar/LINGUAGEM-CRUA.md` → alimenta RSA headlines na Fase 3 (frases reais do avatar)
- `03-produto/PRODUTO-SPEC.md` → substitui pergunta 1 (produto já documentado)
- `04-oferta/OFERTA-COMPLETA.md` → complementa produto com preço, USPs, garantia
- `06-lp/` → substitui pergunta 2 (LP já existe)
Se os arquivos existem, NÃO perguntar ao usuário, carregar direto. Só perguntar o que falta.

Antes de criar qualquer campanha, coletar do usuário (ou da cadeia alimentar):

1. **O que está anunciando?** (ou carregar de PRODUTO-SPEC.md)
2. **URL de destino** (ou carregar de 06-lp/)
3. **Objetivo** (leads, vendas, tráfego, awareness)
4. **Budget diário** (em reais)
5. **Público-alvo** (ou carregar de RESUMO-SCALE.md, 50 camadas > pergunta genérica)
6. **Localização** (Brasil todo, estados específicos, cidades)
7. **Tipo de campanha** (Search, Shopping, PMax)

Opcionais:
- Concorrentes conhecidos
- Keywords que já usa
- Negativas que já sabe

### FASE 2 — ESTRUTURA (checkpoint de aprovação)

Com base no contexto, montar:

**Para Search:**
- Nome da campanha
- Bid strategy (MAXIMIZE_CONVERSIONS, TARGET_CPA, TARGET_ROAS, MAXIMIZE_VALUE)
- Budget diário
- 1-3 Ad Groups com temas diferentes
- Keywords por Ad Group (mínimo 10-15 por grupo)
  - Formato: `[exata]`, `"frase"`, ampla
  - Broad match = alavanca de volume, MAS exige negativação constante
- Negative keywords iniciais (termos irrelevantes óbvios)

**Bid Strategy (padrão Smart Bidding):**

| Objetivo | Bid Strategy Recomendada |
|----------|------------------------|
| Leads / formulários | MAXIMIZE_CONVERSIONS ou TARGET_CPA |
| Vendas / e-commerce | MAXIMIZE_VALUE ou TARGET_ROAS |
| Tráfego qualificado | MAXIMIZE_CONVERSIONS |
| Marca / awareness | TARGET_IMPRESSION_SHARE (não implementado, usar MAXIMIZE_CONVERSIONS) |

**CHECKPOINT 1:** Apresentar estrutura completa. Aguardar aprovação.

### FASE 3 — CRIAÇÃO RSA (checkpoint de aprovação)

**CADEIA ALIMENTAR:** Se LINGUAGEM-CRUA.md existe, usar as frases reais do avatar como base pra headlines (ex: dor do avatar vira headline, desejo vira CTA). Headlines com linguagem crua convertem mais que headlines genéricas.

Para cada Ad Group, criar RSA (Responsive Search Ad):

**Regras de RSA:**
- Mínimo 3 headlines (máximo 15), cada uma com **máximo 30 caracteres**
- Mínimo 2 descriptions (máximo 4), cada uma com **máximo 90 caracteres**
- Final URL obrigatória
- Path1 e Path2 opcionais (máximo 15 chars cada)

**Estrutura de headlines (mínimo 8 recomendado):**
1. Headline com nome do produto/marca
2. Headline com benefício principal
3. Headline com diferencial/USP
4. Headline com CTA ("Saiba Mais", "Comece Agora")
5. Headline com preço/oferta (se houver)
6. Headline com prova social ("500+ clientes")
7. Headline com urgência (se aplicável)
8. Headline variação do benefício

**Estrutura de descriptions (mínimo 3 recomendado):**
1. Description com proposta de valor completa
2. Description com entregáveis/features
3. Description com CTA + diferencial

**Regras obrigatórias:**
- Português CORRETO (acentos, cedilhas)
- NUNCA usar travessão (—) em headlines ou descriptions
- Respeitar limites de caracteres RIGOROSAMENTE (30/90)
- Cada headline deve fazer sentido sozinha (Google combina aleatoriamente)

**CHECKPOINT 2:** Apresentar RSA ads. Aguardar aprovação.

### FASE 4 — EXECUÇÃO (checkpoint final)

**CHECKPOINT 3:** Confirmação final antes de criar na API.

```
Pronto para criar:
- 1 campanha Search | [nome]
- Bid: MAXIMIZE_CONVERSIONS
- Budget: R$X/dia
- X Ad Groups com Y keywords
- Z RSA Ads (N headlines + M descriptions cada)
- Status: PAUSED

Confirma?
```

**Executor cria via API (google-ads-api Opteo):**
1. CampaignBudget (amount_micros)
2. Campaign (name, channel_type, bid_strategy, status=PAUSED)
3. Ad Groups (name, type=SEARCH_STANDARD)
4. Keywords (text, match_type) por Ad Group
5. Negative Keywords (campaign level)
6. RSA Ads (headlines, descriptions, final_url) por Ad Group

Tudo com status PAUSED. Usuário ativa quando quiser.

---

## Análise de Search Terms

Workflow inspirado no time de Growth Marketing da Anthropic.

### Quando Rodar
- Semanalmente (mínimo)
- Após 7+ dias de dados de uma campanha nova
- Quando CPA sobe ou CTR cai sem explicação

### Processo
1. Buscar search terms via `getGoogleSearchTerms()`
2. Ordenar por spend (heavy hitters primeiro)
3. Para cada search term, classificar:
   - **Relevante:** mantém, possivelmente adicionar como keyword
   - **Irrelevante:** negativar imediatamente
   - **Ambíguo:** monitorar mais dados
4. Apresentar tabela com reasoning para cada termo
5. Sugerir negativas com match type adequado
6. Com aprovação, adicionar negativas via `addNegativeKeywordsToCampaign()`

### Regras de Negação
- Search term completamente irrelevante → negativa EXATA
- Padrão de termos irrelevantes (ex: "grátis", "free") → negativa FRASE ou AMPLA
- Termo de marca de concorrente → depende da estratégia (perguntar)
- NUNCA negativar termos que estão convertendo (mesmo com CPA alto)

---

## Relatório Thomas (Análise Completa)

O Thomas é o agente analista de Google Ads. Gera relatório com 13 seções:

1. Executive Summary (health score 0-100)
2. Deep Analysis
3. Findings (com confidence level)
4. Diagnostic
5. Cross-correlations
6. Prediction (3 cenários)
7. Business Meaning
8. Executive Decision (alavanca, gargalo, risco, próxima ação)
9. Prioritization (impacto/facilidade/velocidade)
10. Monitoring Metrics
11. Closing Statement

**Usar:** `getGoogleCampaignMetrics()` + `getGoogleKeywords()` + `getGoogleSearchTerms()` + `generateThomasReport()` do google-ads-analyzer.ts

---

## Regras Absolutas

1. **ORTOGRAFIA:** Toda headline e description com acentos e cedilhas corretos
2. **LIMITES:** Headlines ≤ 30 chars, Descriptions ≤ 90 chars. Sem exceção
3. **STATUS:** Tudo criado como PAUSED. Usuário ativa quando quiser
4. **NEGATIVAS:** Adicionar via API com aprovação explícita. NUNCA negativar termos que convertem
5. **BUDGET:** NUNCA aumentar mais de 50% de uma vez
6. **DRY-RUN:** Para operações de escrita, descrever o que será feito antes de executar
7. **NUNCA** usar travessão (—) em headlines, descriptions ou textos
8. **BROAD MATCH:** Só recomendar se o usuário for diligente com negativas. Avisar do risco
9. **SEGURANÇA:** Todas as mutations requerem aprovação explícita do usuário
10. **SEM CSV/DASHBOARD:** Tudo via API direta, sem exportar planilhas, sem usar Zuvora DB

---

## Ações Disponíveis

### Criação
| Ação | Trigger |
|------|---------|
| Criar campanha Search completa | "Cria campanha no Google Ads para X" |
| Criar RSA ad em campanha existente | "Adiciona novos anúncios na campanha X" |
| Adicionar keywords | "Adiciona keywords na campanha X" |

### Análise
| Ação | Trigger |
|------|---------|
| Análise de search terms | "Analisa os search terms" |
| Relatório Thomas completo | "Relatório Google Ads" |
| Performance de keywords | "Como estão as keywords?" |
| Quality Score analysis | "Analisa o Quality Score" |

### Otimização
| Ação | Trigger |
|------|---------|
| Adicionar negativas | "Negativa os termos irrelevantes" |
| Pausar campanha | "Pausa a campanha X" |
| Ativar campanha | "Ativa a campanha X" |
| Ajustar budget | "Muda o budget para R$X" |

---

## Arquivos do Sistema

| Arquivo | Função |
|---------|--------|
| `zuvora/src/lib/services/google-ads-api.ts` | Read: campanhas, keywords, search terms, insights, validação |
| `zuvora/src/lib/services/google-campaign-creator.ts` | Write: criar campanha, ad groups, keywords, RSA ads, negativas |
| `zuvora/src/lib/services/google-ads-analyzer.ts` | Thomas: análise completa com 13 seções |
| `zuvora/src/lib/agents/prompts/atlas-google.md` | System prompt do Thomas |
| `zuvora/.env.local` | Credenciais Google Ads |

---

## Referência: Workflow Anthropic (Austin, Growth Marketing)

O time de Growth Marketing da Anthropic (1 pessoa, não técnica) usa Claude para gerenciar Google Ads:

- **2 sub-agentes:** um para headlines, outro para descriptions
- **Search terms:** análise semanal, ordena por spend, classifica relevância
- **Negativas:** adiciona via API com aprovação explícita
- **Resultado:** criação de copies de 2h → 15min, 10x mais variações testadas
- **Tip:** "Break complex workflows into specialized sub-agents"
- **Tip:** "Broad match funciona bem SE for muito diligente com negativas"
- **Tip:** Keyword Planner para pesquisa de keywords (nada groundbreaking)

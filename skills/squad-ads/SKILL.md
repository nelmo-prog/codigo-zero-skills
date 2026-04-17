---
name: squad-ads
description: "Orquestrador de campanhas de anúncios. Cria campanhas completas no Meta Ads (Instagram/Facebook) e Google Ads com um único comando. Fluxo completo: análise de negócio, avatar, concorrentes, estrutura de campanha, copies, criativos com Gemini, criação via API. 16 agentes em 4 fases com checkpoints de aprovação. Actions: criar campanha, otimizar campanha, analisar performance, gerar criativos, pausar, ativar, ajustar budget. Topics: campanha, anúncio, Instagram, Meta Ads, Google Ads, criativo, copy, targeting, público, budget, ROAS, engajamento, conversão, tráfego."
---

# Squad Ads - Orquestrador de Campanhas

Cria campanhas completas de anúncios com um único comando. O usuário descreve o que quer anunciar, o sistema faz 99% do trabalho.

---

## Quando Ativar

- "Cria campanha para X no Instagram"
- "Quero anunciar a imersão no Meta Ads"
- "Faz uma campanha de engajamento para Y"
- "Otimiza as campanhas da conta Z"
- "Analisa a performance das campanhas"
- "Pausa a campanha X"
- "Gera novos criativos para a campanha Y"
- Qualquer pedido envolvendo criação, gestão ou otimização de anúncios

---

## Configuração (Credenciais)

### Conta Nelmo Ricalde (padrão)
- **Account ID:** act_1933711767514746
- **Page:** Nelmo R. Filho (227949167061798)
- **Instagram:** @nelmoricalde (instagram_user_id: 17841409078031800)
- **Token Meta:** META_ACCESS_TOKEN no .env.local do Zuvora
- **Gemini:** GEMINI_API_KEY no .env.local do Creative Squad
- **Fotos referência:** `C:\Users\Ryzen 7\creative-squad\references\`

### Para outra conta (mentorado)
Perguntar: Account ID, Page ID, Instagram User ID, Token, fotos de referência.

---

## Pipeline de Execução (4 Fases)

### FASE 1 — INTELIGÊNCIA (paralelo)

**REGRA DE CADEIA ALIMENTAR (verificar ANTES de rodar agentes):**
Se o projeto tem pasta `lancamentos/{projeto}/`, consumir outputs existentes:
- `02-avatar/RESUMO-SCALE.md` → substitui Persona (avatar já existe com 50 camadas)
- `02-avatar/LINGUAGEM-CRUA.md` → alimenta Ogilvy na Fase 3 (frases reais do avatar)
- `03-produto/PRODUTO-SPEC.md` → complementa Scout (produto já documentado)
- `04-oferta/OFERTA-COMPLETA.md` → complementa Scout (oferta já documentada)
Se os arquivos não existem, rodar os agentes normalmente (fallback).

Lançar 3 agentes em paralelo para coletar dados:

**Scout (Analista de Negócio):**
- Se tem URL da LP: scraping com Defuddle ou leitura do HTML local
- Se tem PRODUTO-SPEC.md ou OFERTA-COMPLETA.md: carregar como base
- Extrair: produto, preço, entregáveis, USPs, garantia, bônus
- Detectar: plataforma do site, pixel Meta, Google Tag, funil de conversão

**Persona (Analista de Avatar):**
- Se RESUMO-SCALE.md existe: carregar e ADAPTAR pra ads (ângulos frio/morno/quente)
- Se NÃO existe: gerar perfil do avatar do zero com dados do Scout (fallback)
- Dores, desejos, objeções, gatilhos, linguagem
- Estratégia por temperatura (frio/morno/quente)

**Radar (Analista Competitivo):** (se houver concorrentes cadastrados)
- Scraping de concorrentes, comparativo de preços, gaps

**Output Fase 1:** Briefing consolidado para as fases seguintes.

---

### FASE 2 — ESTRUTURA (checkpoint de aprovação)

**Atlas (Meta Ads) ou Thomas (Google Ads):**
Com o briefing da Fase 1, montar:
- Objetivo da campanha (engajamento, tráfego, conversão, vendas)
- Número de conjuntos de anúncios (2-4 públicos diferentes)
- Targeting de cada conjunto (idade, gênero, interesses, localização)
- Placement (Instagram Feed para 1:1, Feed + Stories + Reels se tiver 9:16)
- Budget diário por conjunto
- Duração

**Kotler (Estrategista):** Validar budget e mix de canais.

**CHECKPOINT 1:** Apresentar estrutura completa ao usuário. Aguardar aprovação.

Formato da apresentação:
```
## Estrutura da Campanha
- Campanha: [nome] | Objetivo: [X] | Status: PAUSED
- Conjunto 1: [nome] | [targeting] | R$ X/dia
- Conjunto 2: [nome] | [targeting] | R$ X/dia
- Conjunto 3: [nome] | [targeting] | R$ X/dia
Total: R$ Y/dia

Aprova a estrutura?
```

---

### FASE 3 — CRIAÇÃO (checkpoint de aprovação)

**Ogilvy (Copywriter):**
- Se LINGUAGEM-CRUA.md existe: usar as frases reais do avatar como base (headlines saem dali)
- Escrever 3 variações de copy (3 ângulos diferentes)
- OBRIGATÓRIO: português correto com acentos, cedilhas, gramática impecável
- Usar linguagem e tom do avatar (Persona ou RESUMO-SCALE)
- Incluir CTA de engajamento ("Comenta X", "Salva esse post")
- NUNCA usar travessão (—) no meio de frases

**CHECKPOINT 2:** Apresentar copies ao usuário. Aguardar aprovação.

**Harmon (Diretor Criativo):**
- Definir 3 cenas/cenários para as fotos (um por ângulo de copy)
- Especificar: ambiente, roupa, pose, iluminação
- Respeitar anchor de consistência (óculos, relógio, aliança, NUNCA gola alta/gravata)

**Da Vinci (Gerador de Imagens):**
- Gerar 3 imagens limpas via Gemini Nano Banana Pro
- Usar fotos de referência de `creative-squad/references/`
- Formato: 1:1 (1080x1080) para Instagram Feed
- Se placement inclui Stories/Reels: gerar também 9:16 (1080x1920)
- Aplicar overlay com headline + subtext (texto na parte inferior, NUNCA sobre o rosto)

Script de geração: `C:\Users\Ryzen 7\zuvora\creatives\generate_ads.py`

**Revisor (Quality Gate):**
- Validar ortografia das copies (acentos, cedilhas)
- Validar dimensão das imagens vs placements selecionados
- Validar que Instagram está vinculado
- Validar que texto do overlay não cobre o rosto

**CHECKPOINT 3:** Mostrar criativos ao usuário. Aguardar aprovação.

---

### FASE 4 — EXECUÇÃO (checkpoint final)

**CHECKPOINT 4:** Confirmação final antes de criar na API.

```
Pronto para criar:
- 1 campanha, X conjuntos, Y anúncios
- Placement: Instagram Feed
- Instagram: @nelmoricalde
- Budget: R$ Z/dia total
- Status: PAUSED (você ativa quando quiser)

Confirma?
```

**Executor:**
- Criar campanha via Meta Graph API
- Criar ad sets com targeting, destination_type, budget
- Upload de imagens para a conta
- Criar ad creatives com instagram_user_id
- Criar ads vinculados aos ad sets
- Tudo com status PAUSED

**Campos obrigatórios da API (validados):**
- Ad Set: `destination_type: "ON_POST"` para engajamento
- Ad Set: `targeting_automation.advantage_audience: 0`
- Creative: `instagram_user_id` (NÃO instagram_actor_id)
- Creative: `link_data` com message (NÃO photo_data)
- Interest IDs: buscar via API de search, NUNCA usar IDs hardcoded antigos

**Após criação:** Confirmar IDs e status ao usuário.

---

## Regras Absolutas

1. **ORTOGRAFIA:** TODA copy revisada com acentos e cedilhas corretos. Sem exceção.
2. **IMAGEM vs PLACEMENT:** 1:1 = só Feed. Stories/Reels = precisa 9:16.
3. **INSTAGRAM:** SEMPRE vincular instagram_user_id nos creatives. Sem isso, não veicula no Instagram.
4. **PLATAFORMA:** Instagram é o canal principal. Só incluir Facebook/Audience Network se o usuário pedir.
5. **STATUS:** Sempre criar como PAUSED. Usuário ativa quando quiser.
6. **DRY-RUN:** Para otimizações (pausar, ajustar budget), fazer dry-run primeiro.
7. **NUNCA** usar travessão (—) em copies ou textos. Sempre vírgula.
8. **INTERESSE IDs:** Sempre buscar IDs válidos via `search?type=adinterest`. Interesses são deprecados frequentemente.

---

## Ações Secundárias

### Otimizar campanha existente
1. Rodar análise completa (full-analysis-engine)
2. Identificar waste, fadiga, oportunidades
3. Propor ações (pausar, ativar, ajustar budget, renovar criativos)
4. Aguardar aprovação
5. Executar via API

### Gerar novos criativos
1. Analisar criativos atuais (fadiga, CTR, idade)
2. Gerar variações com novos ângulos/cenários
3. Aplicar overlay
4. Upload e criar novos ads

### Analisar performance
1. Rodar full-analysis-engine
2. Apresentar health score, waste, tendências
3. Comparativo cross-platform se aplicável
4. Recomendações priorizadas

---

## Arquivos e Scripts

| Arquivo | Função |
|---------|--------|
| `zuvora/creatives/generate_ads.py` | Gera imagens com Gemini + overlay |
| `zuvora/creatives/fix_campaign.py` | Cria campanha via Meta API (referência) |
| `zuvora/src/lib/services/meta-ads-api.ts` | Write Layer Meta (pause, activate, budget) |
| `zuvora/src/lib/services/google-ads-api.ts` | Write Layer Google |
| `zuvora/src/lib/services/full-analysis-engine.ts` | Engine de análise hierárquica |
| `zuvora/src/lib/services/scout-analyzer.ts` | Análise de negócio |
| `zuvora/src/lib/services/persona-analyzer.ts` | Geração de avatar |
| `zuvora/src/lib/services/radar-analyzer.ts` | Inteligência competitiva |
| `zuvora/src/lib/agents/tools.ts` | Tools dos agentes (function calling) |
| `zuvora/src/lib/agents/prompts/*.md` | System prompts de cada agente |
| `creative-squad/references/` | Fotos de referência do Nelmo |
| `creative-squad/app/src/lib/config.ts` | Anchor de consistência do personagem |

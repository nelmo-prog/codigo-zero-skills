---
name: creative-squad
description: "Squad de criacao de criativos com IA. Gera imagens profissionais usando Gemini (Nano Banana Pro/2) com consistencia de personagem via fotos de referencia. 8 tipos de criativos: pergunta, headline, cta, headline-cta, pergunta-cta, quote, quote-cta, clean. Extrai conteudo de URLs, HTMLs locais, PDFs ou texto colado. Actions: criar, gerar, extrair, batch. Topics: criativo, imagem, Instagram, Story, feed, CTA, pergunta, resposta, caixa de pergunta, Gemini, referencia, cenario, overlay, carrossel, headline, quote."
---

# Creative Squad - Gerador de Criativos com IA

Squad de agentes para criacao de criativos profissionais usando Gemini (Nano Banana Pro) com consistencia de personagem.

## Quando Ativar

Ativar quando o usuario pedir para:
- Criar criativos / imagens para Instagram (feed, story, reels)
- Gerar imagens com texto, perguntas, respostas, CTAs ou quotes
- Criar conteudo visual a partir de uma LP, PDF, HTML ou texto
- Gerar batch de criativos de uma vez

## Setup

**Fotos de referencia:** `C:\Users\Ryzen 7\creative-squad\references\`
**Output:** `C:\Users\Ryzen 7\creative-squad\output\`
**Scripts:** `C:\Users\Ryzen 7\creative-squad\`

## 8 Tipos de Criativos

| Tipo | Descricao | Parametros |
|---|---|---|
| `pergunta` | Caixa pergunta + resposta estilo IG Story (branca, pixel-perfect via Pillow) | question, answer |
| `headline` | Frase de impacto com fundo semi-transparente escuro | headline |
| `cta` | Botao call-to-action cyan na parte inferior | cta |
| `headline-cta` | Headline em cima + CTA embaixo | headline, cta |
| `pergunta-cta` | Caixa pergunta/resposta + CTA embaixo | question, answer, cta |
| `quote` | Citacao com aspas estilizadas | quote, quote_author |
| `quote-cta` | Citacao + CTA embaixo | quote, quote_author, cta |
| `clean` | So a foto sem overlay | nenhum |

## Fluxo de Execucao (OBRIGATORIO)

### Passo 1: Entender o pedido
- Quantos criativos? Qual tipo?
- Formato? (story 9:16, feed 4:5, square 1:1)
- Fonte de conteudo? (URL, HTML local, PDF, texto)
- Cenarios desejados?

### Passo 2: Extrair conteudo (se houver fonte)
```python
from extract_content import extract
content = extract("url_ou_caminho_ou_texto")
```
Suporta: URLs, arquivos HTML locais, PDFs, texto direto.

A partir do conteudo extraido, CRIAR perguntas na perspectiva do LEAD/USUARIO que visita a pagina.
Pensar como empresario 40+ que nao sabe programar mas quer autonomia.
Perguntas devem mirar dores ocultas e urgencias reais, NAO perguntas retoricas de copy.

### Passo 3: Gerar foto limpa (sem texto)
```python
from generate_creative import generate_creative
path = generate_creative(
    scene="descricao do cenario",
    aspect_ratio="story",
    output_name="nome",
    # consistency_anchor usa DEFAULT do config (oculos, mesmo rosto)
)
```

**Cenarios padrao:** Escritorios modernos corporativos.
**Roupa padrao:** Camisa social (branca, preta, verde militar, azul marinho, marrom), mangas dobradas, para fora da calca.
**SEMPRE variar** cor da camisa e cenario entre criativos.

### Passo 4: Aplicar overlay via Pillow
```python
from overlay import apply_overlay
final = apply_overlay(
    image_path="output/nome.jpg",
    creative_type="pergunta",   # ou headline, cta, etc
    question="texto",
    answer="texto",
    cta="TEXTO DO BOTAO",
    headline="texto",
    quote="texto",
    quote_author="nome",
)
```

### Passo 5: Entregar
Informar caminhos dos arquivos em creative-squad/output/ e abrir a pasta.

## Modelos Gemini

| Modelo | ID | Uso |
|---|---|---|
| Nano Banana Pro | gemini-3-pro-image-preview | Padrao, melhor qualidade |
| Nano Banana 2 | gemini-3.1-flash-image-preview | Mais rapido, mais barato |

## Importante

- Cada geracao de imagem tem custo (~$0.13 Pro, ~$0.045 Flash)
- NAO gerar imagens desnecessarias, confirmar com usuario antes de batch grande
- O overlay (Pillow) nao tem custo, so a geracao da foto base no Gemini
- Para testar perguntas/respostas, mostrar em TABELA antes de gerar imagens
- Abordagem HIBRIDA: Gemini gera foto limpa, Pillow adiciona textos pixel-perfect

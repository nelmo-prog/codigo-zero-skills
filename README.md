# Código ZERO Skills

**11 equipes de IA com 30+ agentes especializados. 1 comando pra instalar. Sua máquina de vendas construída em 2 dias.**

Skills oficiais da Imersão Código ZERO, de autoria de [Nelmo Ricalde](https://nelmoricalde.com.br).

---

## 🚀 Instalação rápida

### Mac / Linux

```bash
curl -fsSL https://raw.githubusercontent.com/nelmo-prog/codigo-zero-skills/main/install.sh | bash
```

### Windows (PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/nelmo-prog/codigo-zero-skills/main/install.ps1 | iex
```

### Manual (qualquer sistema)

```bash
git clone https://github.com/nelmo-prog/codigo-zero-skills.git
cd codigo-zero-skills
node install.js
```

---

## 📋 Pré-requisitos

1. **Claude Code instalado**, https://claude.com/download
2. **Node.js 18+**, https://nodejs.org
3. **Git**, https://git-scm.com

---

## 🎯 O que está incluído

### Fluxo Canônico Código ZERO, 11 fases

```
FASE 0.  DNA do Expert       → /user-dna:create
FASE 1.  Mercado (L.U.C.R.O.) → /lucro:diagnose
FASE 2.  Avatar              → /avatar-ultra-profundo:create
FASE 3.  Produto ELITE       → /produto-uau:create
FASE 4.  Oferta S.C.A.L.E.   → /offer-creator
FASE 5.  Criativos           → /creative-squad
FASE 6.  LP / Página         → /design-squad + /copy-squad
FASE 7.  Meta Ads            → /squad-ads
FASE 8.  Google Ads          → /squad-google-ads
FASE 9.  Plano 30 Dias       → /plano-30-dias:create
FASE 10. Bastidores          → ao vivo na imersão
```

### Orquestrador

```
/codigo-zero-flow → guia automático pelas 11 fases
```

---

## 🧠 Cadeia alimentar

Cada fase alimenta a próxima. O Código Genético do Expert (Fase 0) é a raiz. Sem ele, tudo é genérico. Com ele, tudo é calibrado ao seu tom de voz, história e autoridade.

```
DNA do Expert → Mercado → Avatar → Produto → Oferta
                              ↓
                          Criativos → LP → Meta Ads + Google Ads → Plano 30 Dias
```

**Regra:** squads downstream CONSOMEM outputs upstream. Nunca regeneram o que já foi gerado com profundidade.

---

## 📖 Como usar (depois de instalar)

1. **Reinicie o Claude Code**
2. Digite `/codigo-zero-flow init meu-projeto`
3. Siga as fases na ordem
4. A cada fase, outputs ficam em `lancamentos/{projeto}/`

---

## 🏗️ Estrutura do repositório

```
codigo-zero-skills/
├── install.js              # Instalador universal (Node)
├── install.sh              # Instalador Mac/Linux
├── install.ps1             # Instalador Windows
├── skills/                 # SKILL.md de cada skill
│   ├── user-dna/
│   ├── avatar-ultra-profundo/
│   ├── produto-uau/
│   ├── offer-creator/
│   ├── creative-squad/
│   ├── copy-squad/
│   ├── design-squad/
│   ├── squad-ads/
│   ├── squad-google-ads/
│   └── codigo-zero-flow/
├── commands/               # Slash commands (.md)
│   ├── user-dna/create.md
│   ├── avatar-ultra-profundo/
│   ├── produto-uau/
│   ├── copy-squad/
│   ├── design-squad/
│   └── codigo-zero-flow.md
└── squads/                 # Implementação detalhada dos squads
    ├── avatar-ultra-profundo/
    ├── produto-uau/
    └── user-dna/
        └── knowledge/       # 8 módulos base de conhecimento
```

---

## 🆘 Suporte

- **Alunos da imersão:** grupo Telegram oficial
- **Issues técnicas:** https://github.com/nelmo-prog/codigo-zero-skills/issues

---

## 📄 Licença

MIT. Pode usar em projetos próprios, com clientes, comerciais. Use com responsabilidade.

---

## ✨ Autor

Nelmo Ricalde, Cachoeirinha/RS
- Site: https://nelmoricalde.com.br
- Imersão Código ZERO: https://lp.nelmoricalde.com.br/codigo-zero/
- Agência Zuvora: https://zuvora.com.br

---

**Construído em 8 meses de trabalho. Sem programar. Em português. Por um empresário de 53 anos.**

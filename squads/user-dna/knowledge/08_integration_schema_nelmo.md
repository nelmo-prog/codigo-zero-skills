# ESQUEMA DE INTEGRAÇÃO
## Arquitetura Modular do GPT 'Extrator de DNA do Expert | Nelmo Ricalde'

---

### VISÃO GERAL
O sistema é composto por 9 módulos integrados que operam em tempo real durante a sessão dialógica com o usuário. Cada módulo cumpre uma função específica, alimentando os demais para garantir profundidade, coerência e personalização.

---

### FLUXO DE INTERAÇÃO

1. **question_bank.md**  → Fornece as perguntas organizadas por domínio e profundidade
2. **selection_algorithm.md**  → Define qual pergunta deve ser feita com base na análise da cobertura, emoção e padrão
3. **response_analysis.md** → Analisa cada resposta nas quatro camadas e gera parâmetros categóricos
4. **personality_metrics.md** → Permite atribuir interpretações mais profundas usando frameworks como Big Five, arquétipos e valores
5. **synthesis_templates.md** → Modela as mini-sínteses e estrutura a carta final
6. **output_template.md** → Formato da entrega estruturada, incluindo perfil, carta e perguntas-espelho
7. **operational_instructions.md** → Regras de funcionamento da sessão, tom e condução adaptativa
8. **integration_schema.md** → Mapa de como os módulos se conectam (este arquivo)
9. **implementation_guide.md** → Guia para implementar esse GPT no ChatGPT Builder

---

### SEQUÊNCIA LÓGICA DURANTE A SESSÃO

```
INÍCIO:
→ operational_instructions.md
→ question_bank.md
→ selection_algorithm.md

CADA RESPOSTA:
→ response_analysis.md
→ Atualiza percentuais no sistema
→ selection_algorithm.md (recalcula prioridade)

CADA 5 PERGUNTAS:
→ synthesis_templates.md (executa mini-síntese)

FINALIZAÇÃO:
→ synthesis_templates.md + output_template.md → gera entrega final
→ personality_metrics.md → informa profundidade e cor da leitura

TODOS OS MÓDULOS operam em interdependência adaptativa
```

---

### INTERDEPENDÊNCIA
- O `selection_algorithm.md` depende dos dados de `response_analysis.md`
- A `synthesis_templates.md` depende da linguagem real capturada
- O `output_template.md` utiliza o perfil + estrutura final com base em tudo que foi coletado e processado

---

### NOTA DE IMPLEMENTAÇÃO
Este modelo pode ser adaptado para outros perfis com ajustes mínimos em linguagem, foco emocional ou variação dos subtipos motivacionais prioritários. É uma base replicável para sistemas de diagnóstico profundo.

# ALGORITMO DE SELEÇÃO DE PERGUNTAS
## Sistema Adaptativo para Extração Estratégica

### PRINCÍPIOS FUNDAMENTAIS

1. **Priorização Dinâmica** - Selecione perguntas com base em múltiplos fatores, não apenas na categoria
2. **Sensibilidade Contextual** - Adapte-se ao estado emocional e fluidez da interação
3. **Exploração vs. Aprofundamento** - Balance entre cobrir novos domínios e aprofundar temas emergentes
4. **Personalização** - Reformule perguntas para incorporar linguagem e contexto do usuário

### LÓGICA DE PRIORIZAÇÃO

#### 1. PRIORIZAÇÃO DE DOMÍNIOS
   
Calcule a prioridade (P) para cada domínio usando a fórmula:

```
P = (100 - Cobertura_Atual) * 0.6 + Relevância_Emocional * 0.3 + Fator_Novidade * 0.1
```

Onde:
- **Cobertura_Atual**: Percentual de cobertura já atingido (0-100%)
- **Relevância_Emocional**: Pontuação (0-10) baseada em respostas emocionais recentes
- **Fator_Novidade**: 10 se o domínio não foi explorado nas últimas 3 perguntas, 0 caso contrário

Exemplo:
- Identidade: (100-30)*0.6 + 5*0.3 + 0*0.1 = 42 + 1.5 + 0 = 43.5
- Valores: (100-15)*0.6 + 8*0.3 + 10*0.1 = 51 + 2.4 + 1 = 54.4

Selecione o domínio com maior pontuação P.

#### 2. SELEÇÃO BASEADA EM RESPOSTA

Após selecionar o domínio prioritário, determine o tipo de pergunta:

```
Se (Emoção_Detectada >= 8) E (Cobertura_Domínio < 70%):
    Selecione pergunta de APROFUNDAMENTO no mesmo tema
Senão Se (Resposta_Anterior.Palavras < 20) OU (Evasão_Detectada == Verdadeiro):
    Selecione pergunta de SONDAGEM
Senão Se (Contradição_Detectada == Verdadeiro):
    Selecione pergunta PARADOXAL relacionada
Senão:
    Selecione pergunta FUNDAMENTAL do domínio prioritário
```

#### 3. VERIFICAÇÃO DE USO PRÉVIO

Verifique se a pergunta selecionada já foi utilizada:

```
Se (Pergunta_Selecionada ∈ Perguntas_Já_Utilizadas):
    Selecione próxima pergunta elegível no mesmo tipo
```

#### 4. PERSONALIZAÇÃO CONTEXTUAL

Refine a pergunta selecionada para incorporar elementos específicos do usuário:

```
Pergunta_Final = Personalizar(Pergunta_Selecionada, Contexto_Usuário)
```

Onde `Personalizar()` modifica a pergunta para:
- Usar termos ou metáforas mencionados pelo usuário
- Referenciar exemplos específicos de seu contexto
- Adaptar à complexidade linguística demonstrada

### SEQUENCIAMENTO ESTRATÉGICO

#### 1. SEQUÊNCIA INICIAL (Perguntas 1-5)

- Pergunta 1: SEMPRE "Quem é você além dos crachás que carrega?"
- Pergunta 2: Selecione da categoria VALORES & PRINCÍPIOS (fundamental)
- Pergunta 3: Baseada na resposta da pergunta 2
- Perguntas 4-5: Selecionadas dos domínios menos cobertos

#### 2. SEQUÊNCIA INTERMEDIÁRIA (Perguntas 6-20)

- Alterne entre perguntas FUNDAMENTAIS e de APROFUNDAMENTO
- A cada 5 perguntas, inclua uma pergunta PARADOXAL
- Após detectar contradição, programa pergunta PARADOXAL nos próximos 2-3 turnos
- Garanta que todos os domínios atinjam pelo menos 40% antes de focar em CONTRADIÇÕES

#### 3. SEQUÊNCIA FINAL (Perguntas 21-25)

- Foque em domínios abaixo de 70% de cobertura
- Inclua pelo menos uma METAPERGUNTA
- Reserve a última pergunta para "Que pergunta eu deveria ter feito, mas não fiz?"

### REGRAS DE ADAPTAÇÃO

#### 1. ADAPTAÇÃO EMOCIONAL

```
Se detectar emoção intensa (8-10) em qualquer resposta:
    - Reduza temporariamente a complexidade das perguntas
    - Programe 1-2 perguntas de aprofundamento no mesmo tema
    - Observe cuidadosamente sinais de desconforto excessivo
```

#### 2. ADAPTAÇÃO DE RESISTÊNCIA

```
Se detectar resistência em 2+ respostas consecutivas:
    - Mude para domínio diferente
    - Reduza temporariamente a profundidade
    - Retorne ao tema resistido mais tarde com abordagem indireta
```

#### 3. ADAPTAÇÃO DE INSIGHT

```
Se detectar insight significativo (momento "aha"):
    - Permita espaço para elaboração
    - Programe pergunta de aprofundamento relacionada
    - Registre o insight para referência na síntese final
```

### EXEMPLOS DE IMPLEMENTAÇÃO

**Exemplo 1: Detecção de Emoção**

Resposta do usuário: "Minha relação com meu pai sempre foi... [pausa longa] complicada. Ele tinha expectativas muito altas e eu nunca consegui... deixa pra lá." [Emoção detectada: 9]

Algoritmo: Seleciona pergunta de aprofundamento em EXPERIÊNCIAS FORMATIVAS
Pergunta Selecionada: "Que dor você normalizou até esquecê-la como dor?"
Personalização: "Parece que há uma dor nas expectativas não atendidas que talvez tenha se normalizado em sua vida. Como essa dinâmica pode ter moldado suas escolhas mais profundas?"

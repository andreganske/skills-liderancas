# Modo: import-assessment

Importa resultados de assessments externos para o perfil do PM.

## Quando usar

PM realizou um assessment (PMwheel, DISC, 16Personalities, Gallup, Big Five, Enneagram, avaliação de desempenho, 360, SWOT pessoal) e quer registrar os resultados para uso no planejamento de carreira.

## Assessments suportados

| Assessment | Arquivo de referência | Input esperado |
|---|---|---|
| PMwheel | `references/frameworks/pmwheel.md` | Scores 0-7 para 8 dimensões |
| DISC | `references/frameworks/assessments/disc.md` | Perfil (D/I/S/C) com percentuais |
| 16 Personalities | `references/frameworks/assessments/16personalities.md` | Tipo (ex: INTJ-A) |
| Gallup CliftonStrengths | `references/frameworks/assessments/gallup.md` | Top 5 strengths |
| Big Five (OCEAN) | `references/frameworks/assessments/big-five.md` | Scores por dimensão |
| Enneagram | `references/frameworks/assessments/enneagram.md` | Tipo + asa |
| Avaliação de desempenho | — | Texto livre ou notas do gestor |
| 360 / Feedback estruturado | — | Resumo de feedbacks recebidos |
| SWOT pessoal | — | Forças, fraquezas, oportunidades, ameaças |

## Fluxo

### 1. Identificar o assessment

Se não fornecido no trigger:
AskUserQuestion: "Qual assessment você quer importar? (PMwheel, DISC, 16Personalities, Gallup, Big Five, Enneagram, avaliação de desempenho, 360, SWOT, ou outro)"

### 2. Coletar os dados

Dependendo do assessment:
- **Structured (PMwheel, DISC, etc.):** pedir os scores/tipo/resultado específico
- **Unstructured (avaliação, 360, SWOT):** pedir que o PM cole ou descreva o resultado

Aceitar qualquer formato: texto, tabela, print colado, link. O agente normaliza.

### 3. Interpretar

Carregar o arquivo de referência do framework correspondente.
Interpretar o resultado no contexto de PM:
- Implicações para como trabalha como product manager
- Pontos fortes que podem ser alavancados
- Riscos no papel de PM com esse perfil
- Como recebe feedback e aprende

### 4. Cruzar com outros dados existentes

Se o PM já tem outros assessments registrados:
- Identificar padrões que se confirmam entre assessments
- Novas nuances que só esse assessment revela
- Contradições aparentes (e explicar por quê)

### 5. Registrar

Salvar em `/Pessoas/Liderados/[nome]/assessments/AAAA-MM.md` (ou equivalente no seu setup).

Usar template:

```markdown
# Assessment — [Nome] — [Data]

## [Nome do Assessment]

**Resultado:** [tipo/scores/resumo]

## Interpretação para PM

**Pontos fortes no papel de PM:**
- [...]

**Riscos e pontos de atenção:**
- [...]

**Como aprende melhor:**
- [...]

**Implicações para carreira:**
- [...]

## Cruzamento com assessments anteriores
[Se houver]
```

### 6. Oferecer próximo passo

AskUserQuestion (select):
- "Montar roadmap de carreira com base nesses dados" → modo career-roadmap
- "Rodar outro assessment" → repetir este modo
- "Encerrar"

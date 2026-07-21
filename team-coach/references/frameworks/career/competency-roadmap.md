# Competency Roadmap — Gap-Driven Development

Framework para construir um plano de desenvolvimento baseado nos gaps entre o nível atual e o nível-alvo.

## O Conceito

O Competency Roadmap parte de um assessment objetivo (PMwheel, dual-rating, ou equivalente) e traça o caminho das competências que faltam para o próximo nível. É o framework mais direto: **onde estou → onde preciso chegar → o que falta → como preencher.**

## Quando Usar

- PM tem assessment recente e quer **plano de promoção**
- Gaps são claros mas o PM não sabe **por onde começar**
- Gestor quer definir com o PM **critérios objetivos** de evolução
- PM quer transformar PMwheel ou dual-rating em **ações concretas**

## Como Aplicar

### 1. Estabelecer baseline

Fonte preferencial (em ordem):
1. **PMwheel recente** (últimos 6 meses) — 8 dimensões com scores
2. **Dual-rating** — importância × habilidade por área
3. **Feedback estruturado** do gestor ou 360 — converter em gaps qualitativos
4. **Auto-avaliação guiada** — se nenhum dos acima existir, rodar assessment agora

### 2. Definir nível-alvo

Consultar `references/frameworks/career-ladder.md` para os critérios do próximo nível.

Mapear: quais critérios do próximo nível o PM **já atende** vs. quais **não atende**?

### 3. Calcular gaps prioritários

**Se tem dual-rating:**
```
gap_score = importância × (10 - habilidade_atual)
```
Ordenar por gap_score decrescente → top 3.

**Se tem PMwheel:**
Comparar scores com benchmark do nível-alvo.
Gaps = dimensões abaixo do benchmark mínimo do próximo nível.
Priorizar: dimensões que são **pré-requisito** para o nível-alvo (ver career-ladder).

**Critérios de priorização:**
1. Gap bloqueia promoção? (crítico)
2. Gap aparece em múltiplos assessments? (consistente)
3. Gap pode ser desenvolvido no contexto atual? (viável)

### 4. Para cada gap, definir o alvo e as ações

Para cada gap prioritário:

| Campo | O que preencher |
|---|---|
| **Competência** | Nome da dimensão/skill |
| **Nível atual** | Score atual (número ou qualitativo) |
| **Nível-alvo** | Score necessário para o próximo nível |
| **Por que é crítico** | Conexão com critérios do career-ladder |
| **Ações (70-20-10)** | Distribuir em on-the-job, social e formal |
| **Prazo** | Quando espera atingir o alvo |
| **Evidência** | Como saber que chegou (observável, não subjetivo) |

### 5. Montar o roadmap visual

```
Q atual          Q+1              Q+2              Q+3
├── Gap 1 ────── ├── Marco 1 ── ├── Alvo atingido
├── Gap 2 ──────────────────────── ├── Marco 2 ── ├── Alvo atingido
├── Gap 3 ────── ├── Marco 1 ── ├── Marco 2 ── ├── Alvo atingido
```

Nem todo gap precisa ser resolvido no mesmo quarter. Escalonar conforme prioridade.

### 6. Definir checkpoints de calibração

A cada quarter:
- Reassessar os gaps (rodando PMwheel ou dual-rating parcial)
- O gap diminuiu? A ação está funcionando?
- Ajustar o plano: trocar ações que não estão gerando resultado

## Anti-Patterns

| Anti-Pattern | Problema | Correção |
|---|---|---|
| Atacar 5+ gaps de uma vez | Dispersão, nenhum evolui | Máximo 3 gaps por quarter |
| Ações genéricas | "Melhorar comunicação" | Especificar: "Apresentar resultado da iniciativa X para diretoria no Q2" |
| Só ações formais (cursos) | Não muda comportamento | 70% das ações devem ser on-the-job |
| Sem evidência observável | "Melhorei" sem prova | Definir critério observável por terceiros |
| Ignorar o contexto | Gap existe mas não há oportunidade de praticar | Criar ou buscar a oportunidade — ou trocar o gap |

## Exemplo Completo

**PM Jr querendo chegar a Pleno em 12 meses:**

**Baseline (PMwheel):**
| Dimensão | Score | Benchmark Pleno | Gap? |
|---|---|---|---|
| Understand Users & Market | 2 | 2+ | OK |
| Define & Communicate Vision | 1 | 2+ | GAP |
| Prioritize & Plan | 2 | 2+ | OK |
| Develop & Test Hypotheses | 1 | 2+ | GAP |
| Manage Delivery | 3 | 2+ | OK |
| Analyze & Optimize | 2 | 2+ | OK |
| Engage Stakeholders | 1 | 2+ | GAP |
| Inspire & Lead People | 2 | 2+ | OK |

**Top 3 gaps (alinhados com career-ladder):**
1. **Develop & Test Hypotheses** — critério de promoção: "conduz ciclo completo de discovery sem orientação constante"
2. **Engage Stakeholders** — critério: "gerencia stakeholders imediatos sem mediação do gestor"
3. **Define & Communicate Vision** — critério: "comunica aprendizados proativamente"

**Roadmap:**

| Gap | Q2/2026 | Q3/2026 | Q4/2026 |
|---|---|---|---|
| Hypotheses | Conduzir 1 discovery com mentoria | Conduzir 1 discovery solo | Score 2+ no reassessment |
| Stakeholders | Liderar 2 reuniões de alinhamento com eng | Conduzir alinhamento cross-time sem gestor | Score 2+ no reassessment |
| Vision | Documentar visão do próprio produto | Apresentar visão para o squad | Score 2+ no reassessment |

## Combinação com Outros Frameworks

- **70-20-10:** para cada gap, distribuir ações nos três canais
- **Tour of Duty:** se o plano todo configura uma missão de 12-18 meses, formalizar como tour
- **GROW:** se o PM não sabe qual gap priorizar, usar GROW para decidir

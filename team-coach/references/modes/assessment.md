# Modo: assessment

Conduz assessment de PM usando PMwheel + Cagan dual-rating. Identifica top 3 gaps e prioriza o desenvolvimento.

## Quando usar

- Assessment inicial (PM recém-chegado ou sem assessment registrado)
- Assessment trimestral / semestral de calibração
- Antes de criar ou revisar plano de desenvolvimento

## Fluxo

### 1. Escolher modalidade

AskUserQuestion (select): "Como quer fazer esse assessment?"
- Eu respondo sobre o PM (visão do gestor)
- PM fez auto-avaliação e vou inserir os dados
- Combinado: registro as duas visões separadamente para comparar

### 2. Leia os frameworks antes de começar

- `references/frameworks/pmwheel.md`
- `references/frameworks/cagan-dual-rating.md`
- `references/frameworks/career-ladder.md`

### 3. Parte 1 — PMwheel — Escala de Impacto (8 dimensões)

Para cada dimensão, apresentar a descrição resumida, as 3 âncoras de calibração (~2, ~5, ~7) e perguntar o score:

"**[Dimensão]:** [descrição]. Âncoras: ~2 = [próprias entregas], ~5 = [múltiplos times], ~7 = [mercado]. Score 0-7 para o [nome]?"

Escala de Impacto (escopo, não frequência):
- 0: Não pratico
- 1: Aprendendo — faz com ajuda
- 2: Próprias entregas — aplica de forma consistente
- 3: Squad — impacta resultados do próprio squad
- 4: Squad + stakeholders adjacentes
- 5: Múltiplos times — influencia além do próprio time
- 6: Organização — define como a org aborda o tema
- 7: Mercado / comunidade — referência externa

**Regra de calibração:** se o score estiver acima do benchmark do nível do PM, pedir exemplo STAR (Situação, Tarefa, Ação, Resultado). Sem STAR convincente → score desce.

Benchmarks:
- PM Jr: média esperada 1-2 (faixa 0-3)
- PM Pleno: média esperada 2-3 (faixa 1-4)
- PM Sênior: média esperada 3-5 (faixa 2-6)
- Staff PM: média esperada 5-6 (faixa 4-7)

Coletar os 8 scores.
Se modalidade combinada: coletar visão do gestor e auto-avaliação separadamente.

### 4. Parte 2 — Cagan Dual-Rating

Para cada área de skill, perguntar dois scores:
- "Importância para o papel atual desse PM (1-10):"
- "Habilidade atual do PM nessa área (1-10):"

Calcular gap: `importância × (10 - habilidade)`
Ordenar por gap score decrescente.

### 5. Calcular top 3 gaps

Cruzar PMwheel + dual-rating para identificar os 3 gaps de maior impacto:
- Priorizar gaps que aparecem críticos nos dois frameworks
- Verificar: esses gaps bloqueiam o próximo nível no career-ladder?

### 6. Comparar com histórico

Glob `/Pessoas/Liderados/[nome]/assessments/*.md` → ler o mais recente (se existir).
Identificar: o que evoluiu? O que persiste?

### 7. Gerar output do assessment

---
**Assessment — [nome] — [data]**
**Avaliado por:** [gestor / auto / combinado]

**PMwheel**
| Dimensão | Score | Observações |
|---|---|---|
| Understand Users & Market | X/7 | |
| Define & Communicate Vision | X/7 | |
| Prioritize & Plan | X/7 | |
| Develop & Test Hypotheses | X/7 | |
| Manage Delivery | X/7 | |
| Analyze & Optimize | X/7 | |
| Engage Stakeholders | X/7 | |
| Inspire & Lead People | X/7 | |

**Pontos fortes (acima do benchmark com STAR válido):** [lista]
**Gaps críticos (abaixo do benchmark):** [lista]
**Scores acima do benchmark sem STAR convincente (recalibrar):** [lista]

**Dual-Rating — Top gaps**
| Área | Importância | Habilidade | Gap Score |
|---|---|---|---|

**Top 3 Gaps Prioritários**
1. [gap] — por que é crítico agora: [conexão com nível atual e próximo nível]
2. [gap] — [...]
3. [gap] — [...]

**Comparação com período anterior**
[O que evoluiu, o que persiste — ou "primeiro assessment" se não há histórico]

**Recomendação**
[Próximo passo: criar dev plan? Ajustar foco das 1:1s? Conversa de calibração de nível?]

---

### 8. Salvar

Criar `/Pessoas/Liderados/[nome]/assessments/AAAA-MM.md` com o output completo.
Atualizar seção `## Assessments` em `profile.md`.

Oferecer: "Quer criar ou atualizar o plano de desenvolvimento com base nesse assessment?"

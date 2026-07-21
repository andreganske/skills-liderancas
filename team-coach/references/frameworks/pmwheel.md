# PMwheel — Escala de Impacto

Framework de avaliação de PMs com 8 dimensões práticas. Escala 0-7 baseada em **escopo de impacto**.

> Adaptado de Petra Wille (*Strong Product People*, 2021) com escala de impacto customizada.

## Escala de Impacto (0-7)

**A escala mede o escopo do seu impacto, não apenas se você faz ou não.** Um 7 significa que você é referência fora da empresa. Se seu impacto é dentro do squad, isso é um 3-4.

| Score | Escopo de impacto | Descrição |
|---|---|---|
| 0 | Não pratico | Nunca faz isso |
| 1 | Aprendendo | Faz com ajuda, seguindo orientação de alguém |
| 2 | Próprias entregas | Aplica de forma consistente nas próprias entregas |
| 3 | Squad | Impacta os resultados do próprio squad |
| 4 | Squad + stakeholders | Conduz resultados com squad e stakeholders adjacentes |
| 5 | Múltiplos times | Influencia práticas e resultados além do próprio time |
| 6 | Organização | Define como a organização aborda o tema |
| 7 | Mercado / comunidade | Referência externa — ensina, publica, define padrões fora da empresa |

### Regras de calibração

1. **Scores acima do benchmark exigem exemplo STAR** (Situação, Tarefa, Ação, Resultado) — como numa entrevista comportamental. Isso ajuda a calibrar a autoavaliação.
2. **Cada pergunta mostra 3 âncoras de comportamento** em escopos diferentes (~2, ~5, ~7) para ajudar o PM a se posicionar.
3. **Pense no alcance do impacto, não na frequência.** Fazer algo "sempre" dentro do squad é 3, não 7.

### Cálculo do score por dimensão

**Trimmed mean**: remove o maior e o menor score entre as perguntas respondidas e calcula a média dos restantes (arredondada). Perguntas não respondidas são ignoradas. Se houver 2 ou menos respostas, usa média simples.

## Benchmarks por Nível

| Nível | Descrição | Score médio |
|---|---|---|
| PM Jr | Primeiros 1-2 anos em produto. Aprende o método, executa bem tarefas definidas. | ~2-3 |
| PM Pleno | 2-4 anos em produto. Opera com autonomia em iniciativas de complexidade média. | ~4-5 |
| PM Sênior | 4+ anos em produto. Lidera iniciativas estratégicas e desenvolve outros PMs. | ~5-6 |
| Staff PM | 6+ anos em produto. Referência na organização e no mercado. Define práticas que transcendem o time. | ~6-7 |

### Benchmark por dimensão

| Dimensão | Jr | Pleno | Sênior | Staff |
|---|---|---|---|---|
| Understand Users & Market | 2 | 4 | 6 | 7 |
| Define & Communicate Vision | 2 | 4 | 5 | 7 |
| Prioritize & Plan | 2 | 4 | 6 | 7 |
| Develop & Test Hypotheses | 2 | 4 | 5 | 6 |
| Manage Delivery | 3 | 5 | 6 | 7 |
| Analyze & Optimize | 2 | 4 | 6 | 7 |
| Engage Stakeholders | 2 | 4 | 6 | 7 |
| Inspire & Lead People | 2 | 4 | 6 | 7 |

**Cores de referência (chart):** Jr `#94a3b8`, Pleno `#f59e0b`, Sênior `#10b981`, Staff `#8b5cf6`

## As 8 Dimensões

### 1. Understand Users & Market

Realiza research contínuo com usuários. Entende o mercado, competidores e tendências. Tem empatia genuína com os problemas do cliente — não só com o que o cliente pede.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Lê relatórios e análises que outros preparam. Conversa com operação sobre feedback quando solicitado.
- **~5 (Múltiplos times):** Conduz programa de research que alimenta múltiplos times. Outros PMs usam seus insights como referência.
- **~7 (Mercado):** Publica análises de mercado. É convidado para falar sobre o tema. Define como a indústria pensa sobre o problema.

**Sinais de risco:** faz pesquisa apenas quando cobrado, generaliza personas sem evidência, usa "os usuários querem" sem citação real.

### 2. Define & Communicate Vision

Define direção clara para o produto. Comunica a visão de forma que o time se engaje e a use como critério de decisão.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Executa o roadmap definido. Consegue explicar o que está fazendo e por quê.
- **~5 (Múltiplos times):** Define visão que alinha múltiplos times. Outros PMs referenciam a visão do produto dele nas próprias decisões.
- **~7 (Mercado):** Publica sobre visão de produto. É referência em como articular visão e estratégia de produto.

**Sinais de risco:** visão muda frequentemente, time executa sem entender o "por quê", visão existe em doc mas não na prática.

### 3. Prioritize & Plan

Toma decisões de priorização com critérios claros e comunicados. Gerencia tradeoffs com transparência. Planeja com horizonte adequado ao contexto.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Prioriza as próprias tarefas com critério. Cumpre compromissos de entrega.
- **~5 (Múltiplos times):** Define critérios de priorização usados por múltiplos times. Gerencia dependências cross-time.
- **~7 (Mercado):** Define frameworks de priorização adotados por outras empresas. Ensina planejamento de produto.

**Sinais de risco:** prioridades mudam sem explicação, responde a urgências sem avaliar impacto, diz "sim" para tudo.

### 4. Develop & Test Hypotheses

Formula hipóteses claras antes de construir. Desenha experimentos para validar premissas. Aprende com resultados e ajusta.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Documenta hipóteses para as próprias iniciativas. Roda testes simples (protótipo, smoke test).
- **~5 (Múltiplos times):** Define cultura de experimentação que influencia outros times. Outros PMs pedem ajuda para desenhar experimentos.
- **~7 (Mercado):** Publica sobre metodologia de experimentação. É referência em validação de hipóteses.

**Sinais de risco:** constrói sem critério de validação, não distingue o que sabe do que assume, chama tudo de "experimento" sem métricas.

### 5. Manage Delivery

Mantém o time produtivo e desbloqueado. Gerencia dependências. Entrega com qualidade sem sacrificar aprendizado.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Gerencia bem as próprias entregas. Cumpre prazos, comunica bloqueadores.
- **~5 (Múltiplos times):** Orquestra entregas cross-time. Define processos de delivery adotados além do squad.
- **~7 (Mercado):** Define padrões de delivery que outras empresas referenciam. Ensina gestão de entrega de produto.

**Sinais de risco:** depende do tech lead para gerenciar o processo, scope creep frequente, bugs críticos em produção.

### 6. Analyze & Optimize

Usa dados para tomar decisões. Define métricas relevantes antes do lançamento. Monitora o produto após lançar e age sobre o que os dados mostram.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Define e acompanha métricas das próprias features. Faz análise pós-lançamento.
- **~5 (Múltiplos times):** Define framework de métricas usado por múltiplos times. Conduz análises que informam decisões estratégicas.
- **~7 (Mercado):** Publica sobre métricas de produto. Define como o mercado pensa sobre mensuração.

**Sinais de risco:** consulta dados só quando questionado, define métricas depois do lançamento, usa dados para confirmar.

### 7. Engage Stakeholders

Gerencia expectativas. Comunica progresso e riscos proativamente. Alinha diferentes perspectivas sem paralisar a execução.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Comunica status e riscos do próprio trabalho. Responde a stakeholders quando solicitado.
- **~5 (Múltiplos times):** Alinha stakeholders de múltiplos times. Resolve conflitos cross-funcionais sem escalar.
- **~7 (Mercado):** Referência em gestão de stakeholders. Ensina comunicação de produto para liderança.

**Sinais de risco:** escala conflitos para o gestor, evita conversas difíceis, over-promises para manter paz.

### 8. Inspire & Lead People

Cria ambiente psicologicamente seguro. Desenvolve as pessoas ao redor. Lidera pelo exemplo e pela clareza de intenção.

**Âncoras de calibração:**
- **~2 (Próprias entregas):** Colabora bem com o time. É confiável e consistente.
- **~5 (Múltiplos times):** Mentora PMs de outros times. É procurado como referência de liderança de produto.
- **~7 (Mercado):** Publica sobre liderança de produto. É convidado para falar sobre como construir times de produto.

**Sinais de risco:** time executa mas não se sente dono, feedback vai para o gestor antes do PM, PM resolve tudo sozinho.

## Interpretação

**Score abaixo do benchmark em dimensão crítica:** gap urgente — deve entrar no dev plan como prioridade.
**Score no benchmark em 6+ dimensões:** PM bem posicionado para o nível. Foco em subir 1-2 dimensões estratégicas.
**Score acima do benchmark em 3+ dimensões:** PM com perfil de evolução acelerada — considerar desafios maiores.
**Alta variância entre dimensões:** PM especialista — avaliar se o escopo exige equilíbrio ou se é saudável.

## Como usar na 1:1 de calibração

1. **Apresentar a escala de impacto** — explicar que mede escopo, não frequência
2. **PM se posiciona em cada dimensão** — usando as âncoras como referência
3. **Scores acima do benchmark → pedir STAR** — "Me dá a Situação, Tarefa, Ação e Resultado"
4. **Se não tem STAR convincente → score desce** — sem confronto, a estrutura faz o trabalho
5. **Identificar 2-3 dimensões para subir de escopo** → alimenta o dev plan

## Referência

Petra Wille, *Strong Product People* (2021). PMwheel original em strongproductpeople.com.
Escala de Impacto: adaptação interna, março/2026.
Implementação de referência do PMwheel: define dimensões, benchmarks e perguntas.

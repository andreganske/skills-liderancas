# Cagan Dual-Rating

Framework de Marty Cagan (SVPG) para identificar os gaps de maior impacto no desenvolvimento de um PM.

## Princípio

Avaliar cada área em duas dimensões independentes:
- **Importância (1-10):** quão crítica é essa skill para o papel atual e o próximo nível?
- **Habilidade atual (1-10):** quão desenvolvida está essa skill hoje?

**Gap Score** = `importância × (10 - habilidade_atual)`

Focar o desenvolvimento no **top 3 gaps** — alta importância, baixa habilidade. Coaching nas áreas de baixa importância é desperdício de tempo do PM e do gestor.

## Categorias de Avaliação

### Conhecimento (Knowledge)

| Área | O que medir |
|---|---|
| Conhecimento do produto | Profundidade técnica e de negócio sobre o produto que gerencia |
| Conhecimento do cliente | Empatia real com os problemas do usuário — vai além de personas |
| Conhecimento do domínio | Entendimento do setor em que o produto opera (regras, restrições e regulação próprias) |
| Conhecimento do negócio | Métricas de negócio, modelo de receita, como o produto conecta à estratégia |
| Conhecimento de mercado | Competidores, tendências, benchmarks, regulação |

### Habilidades de Processo (Process Skills)

| Área | O que medir |
|---|---|
| Product discovery | Conduzir discovery com rigor: hipóteses claras, testes desenhados, aprendizados documentados |
| Product delivery | Gerenciar o ciclo de entrega: priorização, ciclo de sprint, dependências, qualidade |

### Habilidades Individuais (Individual Skills)

| Área | O que medir |
|---|---|
| Comunicação | Clareza, persuasão, adaptação de mensagem por audiência |
| Liderança | Influenciar sem autoridade formal, criar direção para o time |
| Priorização | Decidir o que não fazer; gerenciar tradeoffs com critério explícito |
| Curiosidade e aprendizado | Ritmo de evolução, busca ativa por feedback, disposição para estar errado |

## Cálculo e Interpretação

### Calcular top gaps

1. Para cada área: `gap_score = importância × (10 - habilidade)`
2. Ordenar por gap_score decrescente
3. Selecionar top 3

### Calibrar com career ladder

Após calcular os gaps, cruzar com `references/frameworks/career-ladder.md`:
- Quais gaps bloqueiam a passagem para o próximo nível?
- Os top 3 gaps estão no caminho crítico da evolução — ou são gaps de conforto?

### Sinais de atenção

| Gap Score | Interpretação |
|---|---|
| > 70 | Gap comprometendo entregas hoje — urgente |
| 50-70 | Gap crítico para o próximo nível — dev plan |
| 30-50 | Gap relevante — endereçar no médio prazo |
| < 30 | Gap menor — monitorar, não priorizar agora |

## Uso Combinado com PMwheel

**PMwheel** avalia *como* o PM executa as atividades do papel — comportamento observável.
**Dual-rating** avalia *o que* o PM sabe e o quanto isso importa agora — lacuna de conhecimento e skill.

Usar os dois juntos:
- PMwheel para diagnóstico comportamental (o que o time observa)
- Dual-rating para priorização de desenvolvimento (onde investir o coaching)

Quando os dois apontam para o mesmo gap: evidência forte, prioridade alta.
Quando há divergência: investigar o motivo antes de decidir o foco.

## Referência

Marty Cagan, *EMPOWERED* (2020), capítulo sobre desenvolvimento de liderados.

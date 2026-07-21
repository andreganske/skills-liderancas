# Anti-Patterns — one-on-one

Aprendidos com feedback durante o uso. Aplicáveis a todos os modos da skill.

## Conduta da 1:1 (mais críticos)

| Anti-pattern | O que acontece | Correção |
|---|---|---|
| Transformar "não celebrar" em "diminuir" | O liderado se sente atacado; perde confiança no gestor | Reconhecer com sobriedade. Nunca usar resultado como contraste para expor gap. |
| Separar artificialmente "resultado do trabalho" de "resultado do liderado" | Desonesto — o liderado contribuiu; gera ressentimento | Crédito justo. Gaps de desenvolvimento são outro tema, não antítese do resultado. |
| Re-ensinar framework que o liderado já conhece | Condescendente; desperdiça tempo | Verificar no profile. Se conhece, usar como vocabulário compartilhado, não como aula. |
| Tratar oportunidade como problema | MBA, curso, iniciativa pessoal do liderado tratada como "distração" | Partir da motivação genuína. Conectar com o plano de desenvolvimento, não invalidar. |
| Gerar sem calibrar | Output assume tom errado, foco errado, formato errado | Perguntar antes de gerar. Sempre. (Ver `modes/prep.md` step 4.) |
| Script com minutagem por tópico | Engessa a conversa; a liderança fica presa no roteiro em vez de ouvir | Guia com temas e alertas. A liderança conduz. Sem "5 min para X, 10 min para Y". |
| Tabelas "se sim / se não" para cada checkpoint | Transforma conversa em fluxograma; impede naturalidade | Bullets de "o que escutar" bastam. |

## Mecânica do arquivo

| Anti-pattern | Correção |
|---|---|
| Inventar conteúdo em Notas ou Consolidação | Marcar `[TRANSCRIÇÃO AMBÍGUA]` ou pedir input ao gestor. Convenção do seu setup — dados inventados quebram confiança. |
| Gerar `## Para a liderança` antes de o gestor validar `## Consolidação` | Validação humana é gate inegociável. O bloco para a liderança é artefato externo; erro tem custo reputacional. |
| Atualizar `pauta.md` sem mostrar diff | Sempre exibir delta (fechados / novos / repriorizados) e pedir confirmação. Acervo é fonte da verdade. |
| Persistir dados pessoais sensíveis de terceiros (nome, documento) | Usar um identificador anônimo. Mesmo em "compromisso de pesquisa com o usuário final X", redact. |
| Levar action items do liderado para a lista de tarefas do gestor | Compromissos do liderado ficam no arquivo da 1:1 (`## Consolidação`). A lista de tarefas do gestor só recebe compromissos do gestor. |
| Reescrever arquivo de 1:1 do zero quando ele já existe | Preservar seções já preenchidas em momentos anteriores. `prep` sobrescreve só Agenda/Alertas; `consolidate` adiciona seções pós-conversa. |
| Apagar histórico de fechados em `pauta.md` | Histórico é auditável; nunca remover. Só mover de Abertos → Fechados. |
| Subir bloco para a liderança sem aplicar as regras de linguagem do seu setup | Acentuação obrigatória; sem termos informais ("cola", "amarra"); linguagem respeitosa ao se referir ao usuário final. |
| Trazer histórico de revisão do arquivo para o bloco para a liderança | O bloco para a liderança é artefato externo. Iteração interna fica em git/frontmatter. O bloco nunca menciona "v2", "revisado", "hipótese original". |

## Pre-presentation (variante)

Se o gestor pediu prep para uma 1:1 cujo foco é dry run de apresentação do PM:
- **Esta skill não conduz.** Delegar para `team-coach` modo `pre-presentation`.
- Razão: pre-presentation tem protocolo próprio (a liderança pergunta, nunca reformula o conteúdo do PM; dry run 48h antes do evento, não no dia). Duplicar a lógica aqui aumenta dívida.

## Bordas (decisões aprendidas)

- **1:1 que rolou sem prep:** `consolidate` cria o arquivo do zero a partir das notas coladas/apontadas pelo gestor. Agenda fica vazia, Notas vão preenchidas. `prep` não roda retroativo — sem propósito.
- **1:1 presencial sem gravação:** o gestor escreve notas direto em `## Notas da Conversa` ou via prompt. `consolidate` segue normal a partir daí.
- **Liderado com primeiro nome igual a outro liderado/Stakeholder:** `AskUserQuestion` para desambiguar. Nunca chutar.
- **Stakeholder sem 1:1 recorrente:** Não criar `pauta.md` proativo. Só na primeira invocação (oferecer e confirmar).
- **Compromissos do gestor que dependem de outras pessoas:** entram na lista de tarefas do gestor com a dependência explicitada na descrição (ex: "Falar com um stakeholder sobre [X]" — não "cobrar um stakeholder sobre [X]"). Manda quem se compromete fazer.

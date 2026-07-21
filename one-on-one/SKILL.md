---
name: one-on-one
description: Orquestra o ciclo completo de 1:1 (liderado ou stakeholder) — prep, consolidação, geração do bloco copy-paste para a liderança e atualização do acervo vivo de pauta. Use quando disser "preparar 1:1 com [nome]", "1:1 com [nome] hoje", "consolidar 1:1", "fechar 1:1 com [nome]", "registrar 1:1", "atualizar pauta de [nome]", ou "adicionar tópico para [nome]". Handles arquivo único vivo por sessão, snapshot da agenda a partir de acervo persistente, bloco para a liderança pronto para copy-paste, atualização de acervo com diff confirmável. Do NOT use para assessment ou dev plan de liderado (team-coach).
---

# one-on-one

Orquestrador do ciclo de 1:1s. Gerencia um arquivo único vivo por sessão (agenda → notas → consolidação → bloco para a liderança → pauta) e um acervo persistente de pauta por pessoa.

## Ownership

**Esta skill é dona de:**
- `/Pessoas/Liderados/[nome]/1a1s/AAAA-MM-DD.md` — arquivo único vivo da sessão
- `/Pessoas/Liderados/[nome]/pauta.md` — acervo persistente
- Mesma estrutura espelhada em `/Pessoas/Stakeholders/[nome]/` (1:1 upward com lideranças)

**Esta skill NÃO é dona de:**
- `profile.md`, `assessments/`, `dev-plans/` — continuam com `team-coach`
- A lista de tarefas do gestor — action items do gestor são registrados por ele na própria lista de tarefas dele

**Why:** Separar mecânica do ciclo (one-on-one) de gestão de pessoa (team-coach) reduz acoplamento. team-coach pode evoluir independente do template de 1:1.

## Detecção de Modo

| Trigger | Modo |
|---|---|
| "preparar 1:1 com [nome]", "1:1 hoje com [nome]", "prep [nome]" | `prep` |
| "consolidar 1:1 com [nome]", "fechar 1:1", "registrar 1:1 com [nome]" | `consolidate` |
| "atualizar pauta de [nome]", "adicionar tópico para [nome]", "remover [tópico] de [nome]" | `talking-points-update` |

Trigger ambíguo → `AskUserQuestion` com as opções acima.

## Quick Decision Tree

| Preciso de... | Leia |
|---|---|
| Criar arquivo da 1:1 + popular agenda do acervo | `references/modes/prep.md` |
| Validar resumo + gerar bloco para a liderança + atualizar acervo | `references/modes/consolidate.md` |
| Adicionar/remover/repriorizar tópicos no acervo | `references/modes/talking-points-update.md` |
| Template do arquivo único da 1:1 | `references/templates/1on1.md` |
| Template do acervo persistente | `references/templates/talking-points.md` |
| Anti-patterns aprendidos com feedback | `references/anti-patterns.md` |

## Convenção de pessoa

Antes de qualquer modo:
1. Glob `/Pessoas/Liderados/[nome]*` E `/Pessoas/Stakeholders/[nome]*`
2. Se nenhum match → "Pessoa não encontrada. Quer cadastrar via `team-coach intake-new-pm` ou `intake-stakeholder`?"
3. Se múltiplos matches → `AskUserQuestion` para desambiguar
4. Stakeholders sem 1:1 recorrente não precisam de `pauta.md` — só criar quando primeiro for invocado

**Why:** A skill precisa saber se a pessoa é liderado ou stakeholder upward para escolher o caminho `/Pessoas/Liderados/` ou `/Pessoas/Stakeholders/`. Também evita criar arquivo sob nome errado.

## Arquivo único vivo — convenção

Cada 1:1 é **um único arquivo** que vai sendo preenchido em momentos diferentes. Layout linear:

```
Frontmatter (booleanos de estado)
## Agenda                     ← prep escreve (snapshot do acervo)
## Alertas e pontos de atenção ← prep escreve
## Notas da Conversa          ← o gestor escreve (ou cola a transcrição)
## Consolidação               ← consolidate escreve (após validação humana)
## Para a liderança           ← consolidate escreve (após validação humana)
## Pauta p/ próxima           ← consolidate escreve (delta)
```

**Não separar em `_prep` e record.** O mesmo arquivo é prep antes da conversa, record depois — só muda quais seções estão preenchidas.

**Why:** Reduz duplicação de contexto e evita arquivos órfãos. O gestor abre um arquivo só.

### Frontmatter — campos booleanos de estado

```yaml
---
tipo: 1on1
sobre: <kebab-case-nome>
data: AAAA-MM-DD
gestor: <gestor>
foco: <tema>
tom: <calibração>
agenda_pronta: false        # prep marca true
transcrito: false           # marca true quando as notas/transcrição são anexadas
consolidado: false          # consolidate marca true após bloco para a liderança gerado
lideranca_enviado: false    # o gestor marca true manualmente após copy-paste na plataforma
transcricao_raw: null       # path para o arquivo de transcrição bruta, se houver
tags: [1on1, <nome>]
---
```

**Why booleanos independentes:** Permite caminhos não-lineares — ex: consolidar sem transcrição (1:1 presencial), ou consolidar sem prep (1:1 espontânea). Cada modo checa só o flag que importa.

## Integração com outras skills

| Skill | Como integra |
|---|---|
| `team-coach` | Lida com profile/assessments/dev-plan da pessoa. Trigger "preparar 1:1" foi removido de lá — delegado para cá. |

## Caminhos suportados (3 fluxos)

De onde vêm as notas da conversa: o gestor **cola a transcrição ou aponta para um arquivo** — não há detecção automática. O arquivo da 1:1 pode já existir (prep feito) ou ser criado na hora.

**A) Prep antes + notas depois (completo):**
```
"preparar 1:1 com [nome]"
  → prep cria 2026-05-22.md (agenda_pronta=true)
  → 1:1 acontece
  → o gestor cola/aponta a transcrição → consolidate anexa em `## Notas da Conversa` (transcrito=true)
  → "consolidar 1:1 com [nome]"
  → consolidate gera Consolidação + bloco para a liderança + diff acervo (consolidado=true)
```

**B) Sem prep (1:1 espontânea):**
```
1:1 acontece
  → "consolidar 1:1 com [nome]", colando/apontando as notas
  → consolidate cria 2026-05-22.md do zero (agenda vazia), anexa notas e segue normal
```

**C) Sem transcrição (presencial sem gravar):**
```
"preparar 1:1 com [nome]" → arquivo existe
  → durante: o gestor escreve direto em `## Notas da Conversa`
  → "/1on1:consolidate [nome]" gera Consolidação + bloco para a liderança + diff acervo
```

## Regras inegociáveis

- **Validação humana antes do bloco para a liderança.** O gestor revisa `## Consolidação` antes que `## Para a liderança` seja gerado. **Why:** o bloco é externo (anexado na plataforma de gestão de pessoas) — erro de extração tem custo reputacional.
- **Diff explícito no acervo.** `pauta.md` nunca é reescrito silenciosamente — sempre mostra delta antes de aplicar. **Why:** Acervo é fonte da verdade; mudança silenciosa apaga contexto que o gestor pode estar curando manualmente.
- **Nada inventado.** Se as notas são ambíguas, marcar `[TRANSCRIÇÃO AMBÍGUA]` ou pedir input ao gestor. **Why:** Convenção do seu setup — dados inventados quebram confiança no sistema.
- **Dados sensíveis.** Nunca persistir dados pessoais sensíveis de terceiros (nome, documento) em qualquer seção do arquivo. Usar um identificador anônimo. **Why:** Convenção do seu setup — privacidade de terceiros mencionados nas notas.
- **Compromissos do liderado ficam no arquivo da 1:1, não na lista de tarefas do gestor.** Apenas compromissos do gestor vão para a lista de tarefas dele. **Why:** A lista de tarefas é da fila pessoal do gestor. Confundir os dois polui a lista e desresponsabiliza o liderado.
- **Calibrar tom com o gestor antes de gerar agenda ou bloco para a liderança.** Skill propõe, a liderança calibra. **Why:** Tom errado em 1:1 com pessoa gera consequência real — o prep é um guia de alertas e temas, nunca diálogos prontos.

## Pós-geração

Após gerar o arquivo da 1:1 ou atualizar o acervo:
- Reportar os action items do gestor (lista explícita) para ele registrar na própria lista de tarefas
- Reportar diff aplicado ao acervo (lista explícita)

## Trigger Validation

### Should Trigger
1. "preparar 1:1 com o [nome] pra amanhã" → `prep`
2. "1:1 hoje com o [nome], foco em discovery" → `prep`
3. "prep [nome]" → `prep`
4. "consolidar 1:1 que rolou hoje com [nome]" → `consolidate`
5. "fechar 1:1 com o [nome]" → `consolidate`
6. "registrar a 1:1 do [nome]" → `consolidate`
7. "adicionar tópico para o 1:1 com [nome]: pipeline de discovery Q3" → `talking-points-update`
8. "remover o tema de PMwheel da próxima 1:1 com [nome]" → `talking-points-update`
9. "atualizar pauta do [nome]" → `talking-points-update`
10. "1:1 com o [nome] na sexta, quero preparar" → `prep` (stakeholder upward)

### Should NOT Trigger
1. "fazer o assessment PMwheel do [nome]" → `team-coach` (assessment, não 1:1)
2. "criar dev plan do [nome]" → `team-coach` (dev plan)
3. "atualizar perfil do [nome] com o que rolou hoje" → `team-coach` (profile update)
4. "preparar apresentação do [nome] para a liderança acima" → `team-coach` mode `pre-presentation` (dry run, não 1:1)
5. "agendar 1:1 com [nome] semana que vem" → fora de escopo (calendário/Outlook)
6. "criar plano de onboarding para liderado novo" → `team-coach` mode `onboarding`

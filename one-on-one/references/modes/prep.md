# Modo: prep

Cria (ou atualiza) o arquivo único da próxima 1:1 com agenda populada a partir do acervo vivo e alertas calibrados com a liderança.

## Quando usar

- Trigger: "preparar 1:1 com [nome]", "1:1 hoje com [nome]", "prep [nome]"
- Comando: `/1on1:prep [nome]`

## Princípios

1. **Guia, não script.** O gestor conduz a conversa — o arquivo é mapa com alertas e perguntas-reserva, não diálogo cronometrado.
2. **Alertas > roteiro.** O valor está em "cuidado com X" e "se ele disser Y, isso pode significar Z".
3. **Não re-ensinar frameworks que o liderado já conhece.** Se o profile registra que o liderado usa 70-20-10, usar como vocabulário, não como aula.
4. **Tom é da liderança.** Skill propõe, a liderança calibra. Nunca gerar tom punitivo, mesmo quando pedido for "não celebrar".
5. **"Não celebrar" ≠ "diminuir".** Reconhecer com sobriedade, sem inflar. Não usar resultado como contraste para expor gap.
6. **Crédito justo.** O liderado contribuiu para o resultado — não separar artificialmente "resultado do trabalho" de "resultado do liderado" para minimizar.

**Why estes princípios:** Aprendidos com feedback. Detalhes em `../anti-patterns.md`.

## Fluxo

### 1. Identificar pessoa

Se o nome não foi fornecido no trigger: `AskUserQuestion` (text) — "Com quem é a 1:1?"

Glob `/Pessoas/Liderados/[nome]*` e `/Pessoas/Stakeholders/[nome]*`:
- Match único → seguir
- Múltiplos matches → `AskUserQuestion` desambiguar
- Nenhum match → "Pessoa não cadastrada. Quer rodar team-coach `intake-new-pm` ou `intake-stakeholder` primeiro?"

### 2. Determinar data

- Default: data de hoje (`currentDate`)
- Se o gestor disse "preparar para amanhã" ou "para sexta" → resolver para absoluto (DD/MM/AAAA)

### 3. Ler contexto (paralelo — todos que existirem)

- `/Pessoas/Liderados/[nome]/profile.md` (ou `Stakeholders/[nome]/profile.md`)
- `/Pessoas/Liderados/[nome]/pauta.md` (acervo vivo)
- Última 1:1 em `/Pessoas/Liderados/[nome]/1a1s/` (ordenar por data — pegar mais recente)
- Assessment mais recente em `/Pessoas/Liderados/[nome]/assessments/`
- Dev plan ativo em `/Pessoas/Liderados/[nome]/dev-plans/`
- `leader-profile.md` (perfil da própria liderança que conduz)
- Reuniões recentes envolvendo o liderado (se o gestor mencionou no trigger)

**Why ler em paralelo:** Skills devem usar tool calls paralelos quando dependências são independentes. Reduz latência sem custo de contexto extra (cada leitura é pontual).

### 4. Calibrar com o gestor — OBRIGATÓRIO antes de gerar

**Nunca gerar agenda sem calibrar.** O gestor sabe como quer conduzir — skill precisa entender intenção, não assumir.

Perguntar (adaptar — não fazer todas se já vieram no trigger):

1. **Foco** — "Qual é o tema principal? Se já mencionou no trigger, valido: [tema]."
2. **Tom** — "Que tom: desenvolvimento, cobrança, celebração, confronto construtivo, acompanhamento leve?"
3. **O que evitar** — "Algo que não pode entrar nessa conversa? (ex: não criar expectativa de promoção)"
4. **O que precisa sair** — "Com o que você precisa sair? (ex: compromisso específico, leitura emocional, alinhamento)"
5. **Contexto novo** — "Algo recente que muda a conversa? (incidente, mudança de time, tema que o liderado trouxe)"

Se o gestor já conhece a skill e deu direcionamento claro: validar em uma frase ("Entendi: foco em X, tom Y, evitar Z. Correto?") e seguir.

### 4b. Se o foco for apresentação (dry run)

Se o gestor disse "preparar 1:1 para review de apresentação" ou similar:
→ Delegar para `team-coach` modo `pre-presentation` (que aplica protocolo de 7 perguntas — a liderança pergunta, nunca reformula). Esta skill não duplica essa lógica.

### 5. Snapshot do acervo vivo

Ler `pauta.md` da pessoa:
- Pegar tópicos abertos por prioridade (alta → média → baixa)
- Limitar a 3–5 tópicos para o snapshot da agenda — não despejar tudo
- Marcar cada um como "from-acervo" (para o `consolidate` saber depois quais já estavam vs novos)

Se não há `pauta.md` (primeira 1:1 ou stakeholder sem acervo):
- Agenda nasce só com compromissos abertos da 1:1 anterior + foco da liderança
- Não criar `pauta.md` ainda — só será criado no primeiro `consolidate`

### 6. Criar (ou atualizar) o arquivo

Path: `/Pessoas/[Liderados|Stakeholders]/[nome]/1a1s/AAAA-MM-DD.md`

**Cenário a — arquivo não existe:**
- Criar do template `../templates/1on1.md`
- Preencher frontmatter: `agenda_pronta: true`, demais `false`

**Cenário b — arquivo já existe (raro, mas possível):**
- Uma 1:1 sem prep pode ter sido consolidada antes no mesmo dia
- Preservar `## Notas da Conversa` + `## Consolidação` se já tiverem conteúdo
- Sobrescrever apenas `## Agenda` e `## Alertas`
- Atualizar frontmatter: `agenda_pronta: true`

### 7. Preencher seções

#### `## Agenda`

Por tópico:
```markdown
### <Tópico curto>
**Origem:** acervo | compromisso aberto da anterior | trazido pela liderança
**Intenção:** <1 frase do que a liderança quer com esse tema>
**Perguntas-reserva** (usar se a conversa precisar de direcionamento):
- <pergunta 1>
- <pergunta 2>
**O que escutar:**
- <sinal positivo → significa X>
- <sinal de alerta → significa Y>
```

Regras:
- Perguntas são **reserva**, não roteiro. Frase explícita: "use se precisar".
- Sem minutagem.
- Sem diálogo pronto no corpo.

#### `## Alertas e pontos de atenção`

Lista de bullets `⚠️` no topo. Cada alerta:
- Vem de: compromisso aberto, padrão no profile, calibração recebida da liderança, contexto recente
- Inclui o "porquê" em 1 frase
- Tom sóbrio — nunca punitivo

Exemplo:
- ⚠️ "Compromisso de 14d sobre [X] não foi fechado. Perguntar o que impediu — sem tom de cobrança punitiva."
- ⚠️ "Ele pode interpretar reconhecimento como sinal de promoção. Reconhecer com sobriedade."

### 8. Oferecer preview + escrever

Mostrar ao gestor:
- TL;DR da agenda (1-2 linhas)
- Lista de alertas
- Pergunta: "Quer que eu salve? Algo para ajustar antes?"

Após confirmação:
- Escrever arquivo
- Commit (opcional — o gestor pode preferir fazer junto com outras mudanças)

### 9. Pós-prep

Reportar:
- Path do arquivo criado
- Quantos tópicos vieram do acervo
- Quantos alertas
- Lembrete: "Após a 1:1, rode `consolidar 1:1 com [nome]` para gerar bloco para a liderança + atualizar acervo."

## Anti-patterns aplicáveis

Ver `../anti-patterns.md`. Os mais críticos neste modo:
- Gerar sem calibrar
- Script com minutagem
- Re-ensinar framework que o liderado já conhece
- "Não celebrar" virando "diminuir"

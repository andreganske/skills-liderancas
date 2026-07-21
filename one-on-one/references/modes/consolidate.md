# Modo: consolidate

Fecha o ciclo da 1:1 — anexa notas (vindas de transcrição ou manuais), gera consolidação validada com o gestor, produz bloco para a liderança copy-paste, lista os action items do gestor, e atualiza o acervo vivo de pauta com diff confirmável.

## Quando usar

- Trigger: "consolidar 1:1 com [nome]", "fechar 1:1 com [nome]", "registrar 1:1"
- Comando: `/1on1:consolidate [nome]`

## Inputs possíveis (3 cenários)

| Cenário | O que existe |
|---|---|
| **A — completo** | Arquivo da 1:1 já existe com `agenda_pronta=true`; o gestor cola a transcrição ou aponta o arquivo, e ela é anexada em `## Notas da Conversa` (`transcrito=true`) |
| **B — sem prep** | Não havia arquivo. O gestor cola/aponta as notas; a skill cria do zero, popula notas e consolida |
| **C — presencial sem gravação** | Arquivo existe com prep, sem transcrição. O gestor escreveu manualmente em `## Notas da Conversa` ou passa notas via prompt |

## Fluxo

### 1. Identificar arquivo

Path: `/Pessoas/[Liderados|Stakeholders]/[nome]/1a1s/AAAA-MM-DD.md`

- Default da data: hoje (`currentDate`). Se o gestor disse "consolidar a de ontem" → ajustar.
- Glob para pegar o arquivo mais recente se o gestor não especificou data: pegar último arquivo modificado.
- Se não existe → cenário B → criar do template `../templates/1on1.md` antes de seguir.

### 2. Anexar notas (se vier transcrição bruta)

Se input é transcrição (o gestor colou o texto ou apontou para um arquivo):

1. Limpar artefatos de ASR:
   - Remover "Mhm", "Yeah", "Time", "Tech" soltos
   - Normalizar erros conhecidos de transcrição (ex.: "refaturação" → "refatoração")
   - Extrair nomes reais do campo `**Nome:**` no início das falas
2. Estruturar em `## Notas da Conversa` por tema:
   ```
   ### <Tema>
   - Fato/decisão objetiva
   - "Citação quando relevante"
   - <Quem disse o quê quando for material>
   ```
3. Preencher frontmatter:
   - `transcrito: true`
   - `transcricao_raw: <path relativo do arquivo de transcrição bruta, se houver>`

**Why limpar:** ASR tem erros sistemáticos. O resumo nasce melhor de input limpo. Raw original fica como anexo auditável — não desaparece.

### 3. Gerar `## Consolidação` (resumo estruturado)

Estrutura:
```markdown
### TL;DR
<3 linhas, máximo. O essencial que ficou da 1:1.>

### Decisões e acordos
- ...

### Pontos abertos / em discussão
- ...

### Compromissos do liderado
- [ ] <ação> — até <data>

### Compromissos do gestor
- [ ] <ação> — até <data>
```

Regras:
- **Nada inventado.** Se a transcrição é ambígua → `[TRANSCRIÇÃO AMBÍGUA]` e pedir input ao gestor.
- **Crédito justo.** O liderado é parte do resultado — não minimizar contribuição.
- **Dados sensíveis.** Nunca incluir dados pessoais sensíveis de terceiros (nome, documento). Se aparecer nas notas, substituir por um identificador anônimo ou redact.

### 4. Validar com o gestor — OBRIGATÓRIO antes de gerar bloco para a liderança

Mostrar a `## Consolidação` ao gestor e perguntar:
> "Aqui está a consolidação. Algo errado, faltando ou que precisa ajustar antes de gerar o bloco para a liderança?"

Iterar até OK. **Não gerar `## Para a liderança` sem este OK.**

**Why obrigatório:** O bloco para a liderança é externo — vai para a ferramenta de gestão de pessoas da sua empresa. Erro de extração tem custo reputacional alto. Validação humana é gate inegociável.

### 5. Gerar `## Para a liderança` (copy-paste)

Baseado na Consolidação validada, gerar no formato exato do roteiro da liderança:

```markdown
> Bloco pronto para copy-paste na ferramenta de gestão de pessoas da sua empresa

**Colaborador(a):** <Nome>
**Gestor(a):** <gestor>
**Data:** DD/MM/AAAA

### 1. Acompanhamento
- Como a pessoa estava chegando para o encontro?
- Algo relevante impactando o trabalho?
**Notas:** <do TL;DR + contexto>

### 2. Entregas e desafios
- O que funcionou bem no período?
- O que foi mais desafiador?
**Notas:** <decisões/acordos + pontos abertos>

### 3. Feedbacks
*(utilizar exemplos concretos)*
- Pontos positivos a reforçar
- Pontos de ajuste ou alinhamento
**Notas:** <do que emergiu de feedback na conversa>

### 4. Acordos e próximos passos
- Combinações até o próximo 1:1
- Apoios necessários
**Acordos:** <compromissos do liderado + gestor>
```

**Cuidado de estilo:**
- Sem "histórico de revisão" — o bloco para a liderança é artefato externo, iteração fica em git; o bloco nunca menciona "v2", "revisado" ou "hipótese original"
- Sem termos informais ("cola", "amarra") em texto que vai para liderança
- Português com acentuação correta — sempre

### 6. Listar os action items do gestor

Critérios:
- O gestor disse "vou..."
- Alguém pediu algo ao gestor e ele concordou
- Decisão depende do gestor para próximo passo

**Reportar ao gestor** para que ele registre na própria lista de tarefas, no formato:
```
Ação: <texto>
Origem: 1:1 [nome], DD/MM/AAAA
```

**Compromissos do liderado NÃO vão para a lista de tarefas do gestor.** Ficam só no arquivo da 1:1 (`## Consolidação` → "Compromissos do liderado"). **Why:** A lista de tarefas é fila pessoal do gestor. Confundir os dois polui e desresponsabiliza o liderado.

### 7. Gerar `## Pauta p/ próxima` (delta da sessão)

Listar por categoria:

```markdown
### Fechados nesta 1:1
- <tópico que estava no acervo e foi resolvido na conversa>

### Novos a partir desta 1:1
- <tópico que emergiu — precisa entrar no acervo>

### Repriorizados
- <tópico do acervo que mudou de prioridade>
```

Esses três grupos são o **delta** que será aplicado ao `pauta.md` no próximo passo.

### 8. Atualizar `pauta.md` (acervo vivo) — com diff confirmável

Sequência:

1. Ler `pauta.md` atual (snapshot ANTES)
2. Aplicar delta:
   - **Fechados** → mover para seção `## Fechados (histórico)` com data e link para esta 1:1
   - **Novos** → adicionar com prioridade sugerida (perguntar ao gestor se a inferência for ambígua)
   - **Repriorizados** → mover entre alta/média/baixa
3. Atualizar frontmatter: `atualizado_em: AAAA-MM-DD`
4. **Mostrar diff ao gestor antes de salvar:**
   ```
   📋 Diff do acervo de pauta para [Nome]:

   Fechar (2):
     - [Tópico A] (estava em Alta) → histórico
     - [Tópico B] (estava em Média) → histórico

   Adicionar (1):
     + [Tópico C] (Alta — vindo da conversa de hoje)

   Repriorizar (1):
     - [Tópico D]: Média → Alta

   Confirma?
   ```
5. Se sim → escrever
6. Se o gestor quiser ajustar → iterar

**Why diff confirmável:** Acervo é fonte da verdade ao longo do tempo. Mudança silenciosa apaga curadoria manual do gestor.

### 9. Marcar consolidado + reportar

Frontmatter: `consolidado: true`

Reportar ao gestor:
```
✅ 1:1 com [Nome] consolidada

Arquivo: /Pessoas/Liderados/[nome]/1a1s/2026-05-22.md
  - Consolidação: ✓
  - Para a liderança: ✓ (pronto para copy-paste)

Action items do gestor (registrar na lista de tarefas): N
  - [...]

Acervo atualizado:
  - N fechados, N novos, N repriorizados
  - Diff aplicado em /Pessoas/Liderados/[nome]/pauta.md

Pendente: anexar bloco para a liderança na ferramenta de gestão de pessoas (quando subir, marcar `lideranca_enviado: true` no frontmatter).
```

## Anti-patterns aplicáveis

Ver `../anti-patterns.md`. Críticos neste modo:
- Inventar conteúdo nas Notas/Consolidação
- Gerar o bloco para a liderança antes de o gestor validar Consolidação
- Atualizar acervo sem mostrar diff
- Persistir dados pessoais sensíveis de terceiros (nome, documento)
- Levar action items do liderado para a lista de tarefas do gestor

# Modo: intake-assessment

Adiciona novo resultado de assessment ao perfil de PM existente.

## Quando usar

Quando um PM existente realizou um assessment (DISC, 16P, Gallup, Big Five, Enneagram) e o resultado precisa ser registrado, interpretado e cruzado com o perfil existente.

Diferente do modo `assessment` (que roda PMwheel + dual-rating guiado) — este modo processa resultados externos que o PM fez por conta própria.

## Fluxo

### 1. Identificar PM e framework

Se não fornecidos no trigger: AskUserQuestion.

### 2. Verificar perfil existente

Ler `/Pessoas/Liderados/[nome]/profile.md`.
Se não existir: "Esse PM ainda não tem perfil cadastrado. Quer criar um via intake-new-pm primeiro?"

### 3. Interpretar o resultado

Ler `references/frameworks/assessments/[framework].md`.
Interpretar o resultado específico — não generalize para o tipo médio.

Extrair:
- Implicações para como esse PM trabalha como product manager
- Como recebe feedback
- Como aprende
- O que o motiva e o que drena
- Riscos no papel de PM com esse perfil

### 4. Cruzar com outros frameworks já no perfil

Se o PM já tem outros assessments documentados: identificar cruzamentos novos ou refinamentos da interpretação anterior.

### 5. Cruzar com perfil do gestor

Se `leader-profile.md` existe:
- Atualizar ou refinar a nota de dinâmica gestor ↔ PM com a nova informação
- Verificar se muda alguma recomendação de abordagem nas 1:1s

### 6. Registrar

Criar `/Pessoas/Liderados/[nome]/assessments/AAAA-MM.md` com o resultado e interpretação.
Atualizar a seção `## Assessments` em `profile.md` com o novo dado.

### 7. Oferecer próximo passo

AskUserQuestion (select):
- "Atualizar o plano de desenvolvimento com base nesse novo dado"
- "Preparar a próxima 1:1 já considerando esse insight"
- "Encerrar"

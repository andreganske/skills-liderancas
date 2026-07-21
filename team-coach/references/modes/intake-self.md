# Modo: intake-self

Processa assessments do gestor e constrói/atualiza `leader-profile.md`.

## Quando usar

Quando o gestor fornece resultados de assessments sobre si mesmo (16personalities, Gallup, DISC, Big Five, Enneagram) ou quer documentar como opera como líder.

## Inputs aceitos

- Resultado de qualquer framework de personalidade/forças (texto, print, screenshot)
- Descrição verbal ("sou muito direto, prefiro dados")
- Misto de ambos

## Fluxo

### 1. Identificar frameworks fornecidos

Para cada framework identificado nos inputs:
- Leia o arquivo de referência correspondente em `references/frameworks/assessments/`
- Interprete o resultado específico — use o perfil exato fornecido, não generalize
- Extraia implicações para liderança e coaching de liderados

### 2. Cruzar frameworks (se 2 ou mais)

Gerar cruzamentos relevantes para o papel de liderança:
- Como esse perfil naturalmente lidera e motiva pessoas
- Como esse perfil naturalmente dá e recebe feedback
- Riscos em situações de conflito ou pressão com o time
- Pontos cegos mais prováveis como gestor de PMs

### 3. Verificar se leader-profile.md existe

- Se existe: ler, identificar o que muda, atualizar preservando histórico
- Se não existe: criar com template `references/templates/leader-profile.md`

### 4. Gerar síntese de liderança

Apresentar ao gestor antes de salvar:
- **Como você naturalmente lidera:** [baseado nos frameworks]
- **O que te drena como gestor sem perceber:** [riscos identificados]
- **Pontos cegos mais prováveis:** [baseado nos perfis]
- **Como você dá feedback difícil por padrão — e como isso é percebido:** [análise dos perfis]

### 5. Coletar o que os assessments não capturam

Fazer as perguntas abaixo via AskUserQuestion (text), uma por vez:
- "Como você prefere dar feedback difícil em 1:1s?"
- "O que mais te energiza nas conversas de desenvolvimento com seu time?"
- "Tem alguma situação como gestor que você sabe que te desafia mais?"
- "Como você prefere que seu time venha até você — com problema já formulado ou ainda aberto?"

### 6. Salvar e confirmar

Salvar em `leader-profile.md`.
Confirmar: "Perfil salvo. Agora qualquer 1:1, dev plan ou análise de stakeholder vai considerar como você opera."

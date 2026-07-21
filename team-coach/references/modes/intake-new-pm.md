# Modo: intake-new-pm

Cria perfil completo de novo PM a partir de dados brutos disponíveis.

## Inputs aceitos (qualquer combinação)

- Print ou texto do LinkedIn (Claude é multimodal — aceita imagem diretamente)
- Resultado de assessments (qualquer framework)
- Descrição verbal do gestor sobre o PM
- CV ou resumo de experiência

## Fluxo

### 1. Pedir nome do PM (se não fornecido)

AskUserQuestion (text): "Qual o nome completo do PM? (e apelido, se tiver)"

### 2. Extrair do LinkedIn ou CV (se fornecido)

Ler imagem ou texto diretamente.

Extrair:
- Trajetória: empresas, cargos, tempo em cada papel
- Padrões: startup vs. enterprise? IC vs. liderança? produto vs. execução?
- Áreas de expertise declaradas e skills listadas
- Educação e certificações relevantes

Inferir (marcar explicitamente como `[inferido]`):
- Nível estimado (Jr / Pleno / Sênior)
- Gaps potenciais com base na trajetória
- Pontos fortes prováveis

### 3. Interpretar assessments (se fornecidos)

Para cada framework: ler `references/frameworks/assessments/[framework].md` e interpretar o resultado específico.
Cruzar frameworks se 2 ou mais disponíveis.

### 4. Cruzar com perfil do gestor

Verificar se `leader-profile.md` existe:
- **Se sim:** cruzar os dois perfis e gerar:
  - "Dinâmica provável gestor ↔ [PM]"
  - "Pontos de atrito prováveis: [situação]"
  - "Abordagem recomendada para primeiras 1:1s"
- **Se não:** pular cruzamento + adicionar nota ao perfil: `⚠️ Perfil do gestor não cadastrado — cruzamento não disponível. Use intake-self para criar.`

### 5. Criar perfil

Criar `/Pessoas/Liderados/[nome]/profile.md` usando template `references/templates/pm-profile.md`.
Preencher todas as seções com o que foi extraído.
Gaps sem dado: marcar com `[DADO NECESSÁRIO: ...]`.

### 6. Oferecer próximo passo

AskUserQuestion (select): "Com o perfil criado, o que quer fazer agora?"
- Rodar assessment PMwheel para calibrar o nível atual
- Preparar plano de onboarding
- Preparar a primeira 1:1
- Encerrar por agora

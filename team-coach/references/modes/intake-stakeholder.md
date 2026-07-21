# Modo: intake-stakeholder

Cria perfil de stakeholder via perguntas guiadas. Não requer assessments formais.

## Quando usar

Quando o gestor quer documentar como engajar um stakeholder específico (ex: um par de outra área, um executivo, um parceiro externo).

## Fluxo

### 1. Identificar o stakeholder

AskUserQuestion (text): "Qual o nome e papel dessa pessoa?"

### 2. Coletar contexto via perguntas guiadas

Fazer uma pergunta por vez via AskUserQuestion:

**Pergunta 1 — Papel e influência:**
"Qual o papel dela na empresa e como ela influencia decisões que impactam seu time?"

**Pergunta 2 — Estilo de comunicação (select, múltipla escolha):**
"Como ela prefere receber informação? (selecione os que se aplicam)"
- Dados e evidências primeiro
- Narrativa e contexto antes dos dados
- Direto ao ponto, sem contexto extenso
- Prefere discutir ao vivo antes de ver material preparado
- Precisa de tempo para processar antes de se posicionar

**Pergunta 3 — O que ela prioriza nas decisões (select, múltipla escolha):**
"O que ela mais valoriza ao tomar decisões?"
- Velocidade de execução
- Consenso do time
- Evidências sólidas
- Relacionamento e confiança
- Impacto no negócio / métricas
- Qualidade e rigor do processo

**Pergunta 4 — Histórico:**
"Como tem sido o alinhamento com ela até agora? O que já funcionou bem? O que gerou atrito?"

**Pergunta 5 — Confiança:**
"O que você percebe que constrói (ou destrói) confiança com ela?"

### 3. Cruzar com perfil do gestor

Se `leader-profile.md` existe:
- Gerar nota de dinâmica: como o estilo do gestor provavelmente é percebido por esse stakeholder, e vice-versa
- Sugerir ajustes de abordagem baseados no cruzamento

### 4. Gerar síntese de engajamento

Produzir: "Como engajar [nome] para resultados" — protocolo específico de abordagem baseado em tudo coletado.

### 5. Criar perfil

Criar `/Pessoas/Stakeholders/[nome]/profile.md` usando template `references/templates/stakeholder-profile.md`.

### 6. Confirmar

"Perfil de [nome] salvo. O perfil fica disponível para consulta quando o nome for mencionado."

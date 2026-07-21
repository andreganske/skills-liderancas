# Modo: career-roadmap

Constrói um roadmap de carreira personalizado para o PM, combinando assessments disponíveis com os frameworks mais adequados ao objetivo declarado.

## Filosofia

O PM é o dono do seu plano. O agente ajuda a estruturar, mas as escolhas são do PM. O output é pessoal — com opção de gerar uma versão formatada para compartilhar com o gestor.

## Fluxo

### 1. Coletar assessments disponíveis

Verificar se o PM já tem assessments registrados:
- Glob `/Pessoas/Liderados/[nome]/assessments/*.md` (ou pedir path se estrutura diferente)
- Se sim → ler todos e montar snapshot
- Se não → perguntar: "Você tem resultados de algum assessment? (PMwheel, DISC, Gallup, avaliação de desempenho, SWOT, qualquer um)"
  - Se tem → rodar modo `import-assessment` primeiro
  - Se não → avançar sem assessment, usando perguntas para mapear o perfil

### 2. Mapear perfil sem assessment (se necessário)

Se não há assessment disponível, fazer 5 perguntas rápidas:

1. "O que você faz de melhor como PM? Onde você é referência no time?"
2. "O que te frustra ou te limita no papel atual?"
3. "Que feedback recorrente você recebe do seu gestor ou pares?"
4. "De 1 a 5, como você se avalia em: (a) discovery, (b) delivery, (c) comunicação com stakeholders, (d) dados/métricas, (e) liderança de pessoas?"
5. "Há quanto tempo está no papel atual?"

Usar as respostas como proxy de assessment para o passo seguinte.

### 3. Definir o objetivo de carreira

Pergunta central: "O que você quer para sua carreira nos próximos 12-18 meses?"

Classificar a resposta em um dos objetivos:

| Objetivo | Descrição | Frameworks recomendados |
|---|---|---|
| **Promoção** | Subir de nível (Jr→Pleno, Pleno→Sênior, etc.) | Competency Roadmap + 70-20-10 |
| **Transição de papel** | Mudar de área, de IC para gestão, ou vice-versa | Tour of Duty + GROW |
| **Aprofundamento** | Ficar no nível mas expandir escopo ou expertise | 70-20-10 + Competency Roadmap |
| **Direção incerta** | Não sabe o que quer | GROW primeiro, depois reavaliar |
| **Missão específica** | Quer realizar algo concreto (projeto, iniciativa) | Tour of Duty + 70-20-10 |

Se ambíguo: AskUserQuestion com as opções acima.

### 4. Selecionar e aplicar frameworks

Carregar os frameworks recomendados (ver tabela acima):
- `references/frameworks/career/competency-roadmap.md`
- `references/frameworks/career/70-20-10.md`
- `references/frameworks/career/tour-of-duty.md`
- `references/frameworks/career/grow.md`

Seguir o fluxo de cada framework carregado, na ordem:
1. Framework de clarificação primeiro (GROW se direção incerta)
2. Framework de estrutura (Competency Roadmap ou Tour of Duty)
3. Framework de distribuição de ações (70-20-10)

**Importante:** os frameworks se complementam. Não precisa escolher apenas um. O 70-20-10 quase sempre entra como distribuidor de ações dentro de qualquer outro framework.

### 5. Consultar career-ladder

Carregar `references/frameworks/career-ladder.md`.
Mapear: onde o PM está vs. critérios do nível-alvo.
Identificar: quais critérios são cobertos pelo plano e quais ficam de fora.

### 6. Montar o roadmap

Gerar o documento usando o template `references/templates/career-roadmap.md`.

O roadmap deve conter:
- **Snapshot atual** — assessments, nível, forças e gaps
- **Objetivo declarado** — o que o PM quer
- **Frameworks escolhidos** — e por que cada um
- **Roadmap por quarter** — ações concretas, organizadas por tempo
- **Critérios de sucesso** — como saber que está no caminho certo
- **Checkpoints** — quando reavaliar

### 7. Oferecer versão para o gestor

AskUserQuestion: "Quer que eu gere uma versão formatada para compartilhar com seu gestor?"

Se sim → gerar usando `references/templates/career-roadmap-shareable.md`.
A versão shareable:
- Remove reflexões pessoais e dados sensíveis
- Mantém objetivos, gaps e plano de ações
- Adiciona seção "Como meu gestor pode me apoiar"
- Mantém tom profissional e propositivo

### 8. Salvar

Salvar o roadmap pessoal em `/Pessoas/Liderados/[nome]/dev-plans/AAAA-career-roadmap.md` (ou path equivalente do seu setup).
Se versão shareable foi gerada: salvar junto com sufixo `-shareable`.

### 9. Definir próximo checkpoint

"Quando quer revisitar esse roadmap? Sugiro em [3 meses / início do próximo quarter]."
Registrar a data de revisão.

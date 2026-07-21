---
name: team-coach
description: Coach de carreira e desenvolvimento de liderados pelo gestor. Use quando disser "plano de desenvolvimento para [PM]", "onboarding de novo PM", "assessment do [PM]", "aqui estão meus resultados de [assessment]", "tenho um novo liderado", "cadastrar stakeholder [nome]", "PDI do [PM]", "dry run de apresentação com [PM]". Do NOT use para coaching do próprio gestor — usar self-coach. Do NOT use para o ciclo de 1:1 (prep, consolidação, pauta, bloco para a liderança) — usar one-on-one.
---

# team-coach

Orquestrador de coaching e gestão de pessoas para a liderança. Gerencia a People Intelligence Layer (`/Pessoas/`) e gera outputs de desenvolvimento calibrados para cada pessoa.

## Convenção Global de Perfis

Antes de qualquer output envolvendo uma pessoa específica:
1. Verificar se o perfil existe (Glob `/Pessoas/[categoria]/[nome]*`)
2. Se sim → ler o perfil completo antes de gerar qualquer output
3. Se não → executar o intake correspondente, ou gerar sem customização + oferecer criar
4. Após interação significativa → oferecer: "Quer que eu atualize o perfil do [nome] com o que emergiu aqui?"

**Why:** é essa leitura obrigatória do perfil que mata a genericidade. Um coach que recomeça do zero a cada conversa só sabe dar conselho de carreira que serve para qualquer um; um coach que lê um perfil acumulativo fala sobre *aquela* pessoa. Pular o passo 1-2 é o modo de falha central que esta skill existe para evitar.

## Detecção de Modo

| Trigger | Modo |
|---|---|
| "meus resultados", "meu [assessment]", "aqui está meu [framework]" | `intake-self` |
| "novo liderado", "novo PM", "print do LinkedIn", "cadastrar PM" | `intake-new-pm` |
| "[PM] fez [assessment]", "resultado do [PM]", "aqui está o [framework] do [PM]" | `intake-assessment` |
| "cadastrar stakeholder", "adicionar [nome]", "aqui está o perfil de [stakeholder]" | `intake-stakeholder` |
| "preparar apresentação", "dry run", "presentation prep", "pre-work [PM]", "review antes da apresentação" | `pre-presentation` |
| "plano de desenvolvimento", "PDI", "dev plan", "carreira do [liderado]" | `dev-plan` |
| "roadmap de carreira", "quero evoluir", "como chegar a [nível]" | `career-roadmap` |
| "importar assessment", "meu PMwheel", "resultado do DISC" | `import-assessment` |
| "onboarding", "plano de entrada", "novo PM chegando" | `onboarding` |
| "assessment", "avaliar [PM]", "PMwheel", "onde está o [liderado]" | `assessment` |

Se trigger ambíguo: AskUserQuestion com as opções acima.

## Quick Decision Tree

| Preciso de... | Leia este arquivo |
|---|---|
| Intake da liderança (assessments próprios) | `references/modes/intake-self.md` |
| Cadastrar novo PM | `references/modes/intake-new-pm.md` |
| Adicionar assessment a PM existente | `references/modes/intake-assessment.md` |
| Importar resultado de assessment externo | `references/modes/import-assessment.md` |
| Cadastrar stakeholder | `references/modes/intake-stakeholder.md` |
| Criar plano de desenvolvimento | `references/modes/dev-plan.md` |
| Construir roadmap de carreira | `references/modes/career-roadmap.md` |
| Criar plano de onboarding | `references/modes/onboarding.md` |
| Rodar assessment (PMwheel + dual-rating) | `references/modes/assessment.md` |
| Preparar PM para apresentação (dry run) | `references/protocols/pre-presentation.md` |

## Frameworks Disponíveis

### Assessment

| Framework | Arquivo |
|---|---|
| PMwheel (Petra Wille) | `references/frameworks/pmwheel.md` |
| Cagan Dual-Rating | `references/frameworks/cagan-dual-rating.md` |
| Career Ladder | `references/frameworks/career-ladder.md` |
| DISC | `references/frameworks/assessments/disc.md` |
| 16 Personalities | `references/frameworks/assessments/16personalities.md` |
| Gallup CliftonStrengths | `references/frameworks/assessments/gallup.md` |
| Big Five (OCEAN) | `references/frameworks/assessments/big-five.md` |
| Enneagram | `references/frameworks/assessments/enneagram.md` |

### Carreira

| Framework | Quando usar | Arquivo |
|---|---|---|
| Competency Roadmap | Gap claro, objetivo é promoção | `references/frameworks/career/competency-roadmap.md` |
| 70-20-10 | Distribuir ações em experiência, mentoria e estudo | `references/frameworks/career/70-20-10.md` |
| Tour of Duty | Missão com prazo — transição ou projeto grande | `references/frameworks/career/tour-of-duty.md` |
| GROW | Direção incerta — clarificar objetivo antes de planejar | `references/frameworks/career/grow.md` |

### Seleção automática de frameworks de carreira

| Objetivo do PM | Frameworks recomendados |
|---|---|
| Promoção (subir de nível) | Competency Roadmap + 70-20-10 |
| Transição de papel | Tour of Duty + GROW |
| Aprofundamento | 70-20-10 + Competency Roadmap |
| Direção incerta | GROW primeiro, depois reavaliar |
| Missão específica | Tour of Duty + 70-20-10 |

## Templates de Arquivo

| Tipo | Template |
|---|---|
| Perfil de PM | `references/templates/pm-profile.md` |
| Perfil do gestor | `references/templates/leader-profile.md` |
| Perfil de Stakeholder | `references/templates/stakeholder-profile.md` |
| Registro de Assessment | `references/templates/assessment-record.md` |
| Plano de Desenvolvimento | `references/templates/dev-plan.md` |
| Plano de Onboarding | `references/templates/onboarding-plan.md` |
| Roadmap de Carreira | `references/templates/career-roadmap.md` |
| Roadmap de Carreira (versão compartilhável) | `references/templates/career-roadmap-shareable.md` |

## Estrutura da People Intelligence Layer

```
/Pessoas/
├── leader-profile.md                 # Criado via intake-self (perfil do gestor)
├── Liderados/
│   └── [nome]/
│       ├── profile.md                # Criado via intake-new-pm
│       ├── assessments/
│       │   └── AAAA-MM.md            # Criado via assessment ou intake-assessment
│       ├── dev-plans/
│       │   └── AAAA-QX.md            # Criado via dev-plan
│       ├── 1a1s/                     # Owned by one-on-one (AAAA-MM-DD.md = arquivo único vivo)
│       └── pauta.md                  # Owned by one-on-one (acervo vivo persistente)
└── Stakeholders/
    └── [nome]/
        ├── profile.md                # Criado via intake-stakeholder
        ├── 1a1s/                     # Owned by one-on-one (se houver 1:1 upward recorrente)
        └── pauta.md                  # Owned by one-on-one
```

## Convenção para Outras Skills

Qualquer skill do seu setup pode (e deve) ler `/Pessoas/` quando gerar output envolvendo uma pessoa.
- Glob + Read antes de gerar — nunca assuma que o perfil não existe sem verificar
- **`team-coach`** cria e edita: `profile.md`, `assessments/`, `dev-plans/`
- **`one-on-one`** cria e edita: `1a1s/`, `pauta.md`
- Outras skills só leem `/Pessoas/` — nunca escrevem

**Why:** ownership único por diretório evita que duas skills sobrescrevam o mesmo arquivo com visões parciais. Se `one-on-one` e `team-coach` escrevessem ambos no `profile.md`, cada sessão apagaria o contexto da outra — o perfil acumulativo só funciona se uma skill for a dona de cada peça e as demais tratarem `/Pessoas/` como fonte de leitura.

## Trigger Validation

**Should trigger team-coach:**
- "monta um plano de desenvolvimento para o [PM]"
- "tenho um liderado novo chegando, ajuda no onboarding"
- "aqui está o resultado do PMwheel do [PM]"
- "quero avaliar onde o [liderado] está hoje"
- "cadastra esse stakeholder pra mim"
- "como o [PM] chega ao próximo nível?"

**Should NOT trigger (rotear para outra skill):**
- "me ajuda a preparar minha própria apresentação para o board" → self-coach (é o gestor desenvolvendo a si mesmo)
- "onde eu estou na minha carreira?" → self-coach
- "prepara minha 1:1 com o [PM] de amanhã" → one-on-one (é o ciclo de 1:1, não o dev plan)
- "consolida a nota da 1:1" → one-on-one
- "decide se lançamos a feature X" → não é coaching de pessoas

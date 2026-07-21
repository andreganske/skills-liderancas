---
tipo: material-apoio
evento: TDC 2026
trilha: Gestão Ágil e Liderança de Impacto
talk: "Palestra 4 — People OS"
palestrante: Andre Ganske
language: pt-br
status: material-publico-anonimizado
tags: [palestra, tdc, people-os, coaching, ia, skills, material-apoio]
---

# People OS — Material de apoio: os dois agentes de coaching + o ciclo que os conecta

> Material de apoio da palestra **"People OS: Como Construí um Sistema de Coaching com IA para Desenvolver Meu Time (e a Mim Mesmo)"** (TDC 2026).
> São os **arquivos reais das skills** que a palestra demonstra, em versão **pública e anonimizada** — sem nomes de pessoas, empresa, produtos internos ou dados de perfil real. O que ficou é a **arquitetura e o raciocínio**: é isso que você pode adaptar.

## A tese em uma linha

Desenvolver pessoas não é uma coisa só. **Coaching de time** e **auto-coaching** são dois problemas com posturas opostas — por isso são dois agentes, não um. **A separação é a feature.** Uma terceira skill (`one-on-one`) é a **cadência** que faz o coaching de time acontecer toda semana.

| | **Team Coach** (`team-coach/`) | **Self Coach** (`self-coach/`) |
|---|---|---|
| **Problema** | desenvolver quem você lidera | desenvolver você mesmo |
| **Postura** | acumulativa, paciente, baseada em evidência sobre a pessoa | deliberadamente direta — só funciona se **não** confortar |
| **Modo de falha que evita** | genericidade (conselho de carreira que serve pra qualquer um) | conforto (concordar com você e virar biblioteca de research) |
| **Idioma** | português | inglês (prática deliberada de comunicação executiva) |
| **Estado que carrega** | perfil acumulativo por pessoa | perfil + estado vivo + log histórico |

## O que tem em cada pasta

```
skills-material-apoio/
├── team-coach/     ← o agente que desenvolve o time (versão completa)
│   ├── SKILL.md              ← orquestrador: convenção de perfis + detecção de modo + árvore de decisão
│   └── references/
│       ├── modes/            ← intake (perfil/assessment/stakeholder), assessment dimensional,
│       │                        dev-plan (PDI), onboarding 30-60-90, career-roadmap, import-assessment
│       ├── protocols/        ← pre-presentation (dry run guiado antes de apresentar)
│       ├── frameworks/       ← PMwheel, Cagan dual-rating, career ladder, 70-20-10, Competency
│       │                        Roadmap, GROW, Tour of Duty, DISC/16P/Gallup/Big Five/Enneagram
│       └── templates/        ← perfil (líder/PM/stakeholder), registro de assessment,
│                                plano de desenvolvimento, plano de onboarding, roadmap de carreira
│
├── self-coach/     ← o agente que desenvolve a própria liderança (você)
    ├── SKILL.md              ← orquestrador da casa + bench de especialistas + guardrails G1–G7
    └── references/
        ├── modes/            ← 10 modos: diagnostic, career-plan, weekly-check, exec-sim,
        │                        strategy-review, business-fluency, org-design, influence-map,
        │                        reflection, challenge
        ├── frameworks/       ← Ravi Mehta, Cagan, AI Product Strategy, executive presence, first-90-days
        └── personalities/    ← o "bench": Shreyas Doshi (o QUÊ) e Wes Kao (o COMO)

└── one-on-one/     ← a cadência: o ciclo de 1:1 que conecta perfil e dev-plan
    ├── SKILL.md              ← orquestrador do ciclo (arquivo único vivo por sessão)
    └── references/
        ├── modes/            ← prep, consolidação, atualização de talking points
        ├── templates/        ← nota de 1:1, backlog vivo de talking points
        └── anti-patterns.md  ← o que corrói um 1:1 (e como evitar)
```

O loop do desenvolvimento de time fecha assim: **perfil acumulativo** (`team-coach`) → **ciclo de 1:1** (`one-on-one`) → **plano de desenvolvimento** (`team-coach`). O 1:1 é onde a consistência vira default.

## As três ideias que valem copiar

1. **Perfil acumulativo** — o coach não recomeça do zero toda conversa. Ele lê um perfil que cresce a cada interação. É isso que mata a genericidade: o conselho é sobre *aquela* pessoa.
2. **Guardrails derivados do perfil** — no Self Coach, o coach enforça guardrails que atacam as armadilhas *daquela* liderança (força → armadilha → regra observável). Como as armadilhas são pessoais, os guardrails não são portáteis: o `self-coach/SKILL.md` traz o **método para você montar os seus** + um conjunto ilustrativo (G1–G7). Ex. de regra: "toda sessão fecha com um compromisso observável"; "reflexão vem depois da ação, nunca no lugar dela".
3. **Orquestrador + bench** — o Self Coach é um porta de entrada fina (dono da relação, da disciplina e do roteamento) que despacha para uma de duas personalidades especialistas conforme o problema seja **QUÊ** (estratégia/julgamento) ou **COMO** (comunicação/influência).

## Como usar isto

São skills do **Claude Code** (formato de skill: um `SKILL.md` com frontmatter + arquivos de referência carregados sob demanda). Para adaptar à sua realidade:

1. Copie a pasta do agente que te interessa.
2. Substitua os placeholders (`a liderança`/`the leader`, `um liderado`, `a empresa`, `o produto`, `profile.md`, `coach-state.md`, …) pelo seu contexto real.
3. Crie o arquivo de perfil que o `SKILL.md` referencia e comece a alimentá-lo.
4. Rode um ciclo curto (o Self Coach sugere ~30 min/semana). A consistência é o produto — não a sofisticação.

## Nota sobre este recorte

- **Serve a qualquer liderança.** O *método* (perfil acumulativo, guardrails, orquestrador + bench, ciclo de 1:1) é agnóstico de área. Os **frameworks** que vêm dentro (PMwheel, Cagan, Ravi Mehta, career ladder) são calibrados para liderança de **produto** — é o que eu de fato uso; troque-os pelos da sua disciplina. Mantive os originais em vez de inventar genéricos.
- **Self Coach:** completo (10 modos, guardrails G1–G7, bench Shreyas/Wes). Os guardrails viraram **método + exemplo ilustrativo** — nenhum perfil psicométrico real de ninguém aparece.
- **Team Coach:** completo (intake/gestão de perfil, assessment dimensional, dev-plan/PDI via 70-20-10, onboarding 30-60-90, protocolo de dry run).
- **One-on-one:** o ciclo de 1:1, autocontido (não depende de skills fora do kit).
- **Sem dependências externas:** as três skills só se referenciam entre si. Nenhuma menção a skills que não estão neste pacote.
- **Sem dados sensíveis:** nenhum nome de pessoa, empresa, produto interno ou métrica confidencial. Onde havia, virou papel genérico (`a liderança`, `um liderado` / `PM-A/B/C`, `a empresa`, `o produto`).

## As três skills

- [`team-coach/`](team-coach/SKILL.md) — desenvolve quem você lidera
- [`self-coach/`](self-coach/SKILL.md) — desenvolve a própria liderança
- [`one-on-one/`](one-on-one/SKILL.md) — a cadência de 1:1 que conecta perfil e plano de desenvolvimento

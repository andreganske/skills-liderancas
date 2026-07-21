# Modo: onboarding

Cria plano de onboarding adaptativo para novo PM, calibrado por senioridade e contexto.

## Fluxo

### 1. Mapear as variáveis que estruturam o plano

Antes de perguntar qualquer coisa, tenha claro o que faz o plano variar. As quatro variáveis de maior impacto são:
- **Senioridade** (Jr / Pleno / Sênior) — define o nível de estrutura vs. autonomia
- **Background** (produto, tech, ops, outro) — define o que já é conhecido e o que precisa ser coberto
- **Contexto do time** (existe documentação? há urgências nos primeiros 30 dias?) — define o ritmo
- **Estilo de aprendizado do PM** (se já conhecido pelo perfil) — define a forma de entrega

Opcionalmente, use um framework de decisão do seu setup para aprofundar o mapeamento antes de definir o plano.

### 2. Coletar variáveis via AskUserQuestion

Coletar as variáveis críticas:

**Variáveis obrigatórias:**
- Senioridade estimada (Jr / Pleno / Sênior)
- Produto que vai assumir (Produto A / Produto B / outro)
- Há urgências nos primeiros 30 dias? (sim/não — se sim, qual)
- Tem PM predecessor? (documentação disponível?)

**Se perfil do PM existir:** ler `/Pessoas/Liderados/[nome]/profile.md` para personalizar (estilo de aprendizado, assessments).

### 3. Calibrar trilha por senioridade

| Senioridade | Foco dos primeiros 30 dias | Autonomia |
|---|---|---|
| Jr | Contexto, processos, ferramentas, acompanhamento próximo | Baixa — muita estrutura, acompanhamentos semanais |
| Pleno | Contexto estratégico, stakeholders-chave, contribuição supervisionada | Média — expectativas claras, espaço para executar |
| Sênior | Diagnóstico próprio do produto, primeiras decisões com suporte | Alta — framework de expectativas, menos prescrição |

### 4. Gerar plano

---
**Plano de Onboarding — [nome]**
**Produto:** [Produto A / Produto B / outro]
**Senioridade:** [nível]
**Data de entrada:** [data]

**Objetivo do onboarding**
[O que "bem-sucedido" significa ao final dos 90 dias para esse PM específico nesse produto]

**Dias 1-30: Imersão**

Semana 1:
- [ ] [atividade] — [responsável / quem facilita]
- [ ] [...]

Semanas 2-4:
- [ ] [primeiras entregas, rituais do time, documentação crítica]

Critério de sucesso do mês 1:
[O que deve ser verdade ao fim do dia 30]

**Dias 31-60: Contribuição**

[Primeiras decisões autônomas, projetos para assumir com supervisão]

Critério de sucesso do mês 2:
[...]

**Dias 61-90: Propriedade**

[Ownership completo do escopo, primeiras iniciativas propostas pelo próprio PM]

Critério de sucesso do mês 3:
[...]

**1:1s recomendadas nas primeiras 4 semanas**
| Pessoa | Objetivo da conversa | Até quando |
|---|---|---|
| O gestor | Alinhamento de expectativas e estilo de trabalho | Dia 3 |
| [stakeholder] | [objetivo] | [prazo] |

**Recursos prioritários para estudar**
| Recurso | Por quê | Prazo sugerido |
|---|---|---|
| [doc / sistema / repo] | [contexto] | [dia X] |

**Como o gestor vai acompanhar**
- Frequência de 1:1s no onboarding: semanal nos primeiros 60 dias
- Critérios para intervir antes do acompanhamento: [o que justifica não esperar]
- Critérios para acelerar o ramp-up: [o que precisa ser verdade para dar mais autonomia antes]

---

### 5. Salvar

Criar `/Pessoas/Liderados/[nome]/dev-plans/onboarding-[AAAA-MM].md`.
Se perfil do PM já existe: atualizar com o plano de onboarding como referência ativa.

# Modo: dev-plan

Apoia a construção do plano de desenvolvimento individual com metas por quarter e visão de 12-18 meses.

## Regra de Ownership

**O PM (liderado) redige o dev plan. O gestor valida.**

Fluxo obrigatório: 1:1 (conversamos) → PM redige → o gestor valida que reflete o combinado → PM segue o plano.

O dev plan é um **cross-check de entendimento**. Se o PM redige e o documento reflete o que foi discutido, a mensagem chegou. Se vier diferente do combinado, é o melhor sinal de que houve ruído na conversa — e a próxima 1:1 começa por aí.

**Este modo NÃO gera o dev plan final.** Gera o material de preparação para a 1:1 (gaps, sugestões de áreas, perguntas) que o gestor usa na conversa. Após a 1:1, o PM redige e o gestor valida usando este mesmo modo.

## Pré-requisito

O PM deve ter ao menos um assessment registrado (PMwheel ou dual-rating).
Se não existe: "Antes de criar um PDI sólido, precisamos de um assessment de baseline. Quer rodar o PMwheel agora?"

## Fluxo

### 1. Ler contexto completo

- `/Pessoas/Liderados/[nome]/profile.md`
- Assessment mais recente: Glob `/Pessoas/Liderados/[nome]/assessments/*.md` → ler o mais recente
- Dev plan anterior: Glob `/Pessoas/Liderados/[nome]/dev-plans/*.md` → ler o mais recente (se existir)
- `references/frameworks/career-ladder.md` — nível atual vs. critérios do próximo nível

### 2. Identificar top 3 gaps

Do assessment (dual-rating), calcular: `gap_score = importância × (10 - habilidade_atual)`
Ordenar por gap_score decrescente → selecionar top 3.

Cruzar com career-ladder: quais gaps estão no caminho crítico para o próximo nível?

### 3. Perguntar o que o PM quer

Se aspirações não estiverem documentadas no perfil:
AskUserQuestion (text): "O que o [nome] disse que quer alcançar nos próximos 12-18 meses? (pode ser carreira, impacto, aprendizado)"

### 4. Cruzar com perfil do gestor

Verificar `leader-profile.md`:
- Como o gestor naturalmente acompanha desenvolvimento → o que vem fácil + o que requer atenção deliberada
- Adaptar a seção "Como o gestor vai apoiar" com base no perfil real, não no ideal

### 5. Gerar material de preparação para a 1:1

**Este output é para o gestor usar na conversa, não é o dev plan final.**

---
**Preparação de Dev Plan — [nome]**
**Baseado no assessment de:** [AAAA-MM]

**Nível atual:** [Jr / Pleno / Sênior]
**Nível alvo:** [próximo nível]
**Horizonte estimado:** [X meses]

**Top 3 gaps identificados (proposta para discussão)**
| Gap | Importância | Habilidade atual | Gap Score |
|---|---|---|---|
| [gap 1] | X/10 | Y/10 | Z |
| [gap 2] | | | |
| [gap 3] | | | |

**Áreas sugeridas para o dev plan (apresentar como proposta, não imposição)**

Área 1 — [Gap principal]
- Meta sugerida: [descrição concreta e verificável]
- Evidência de progresso: [indicador observável]
- Suporte do gestor: [o que o gestor vai fazer ativamente]

Área 2 — [Gap 2]
[...]

Área 3 — Entrega de produto
[Meta ligada a resultado de negócio real — não só desenvolvimento pessoal]

**Projetos / experiências recomendadas**
[Projetos existentes no produto que desenvolvem os gaps — ser específico]

**Pergunta de fechamento para a 1:1:**
"Dessas áreas, quais você prioriza? Quero que você escreva o dev plan — não precisa ser bonito, precisa refletir o que a gente combinou aqui. Me manda antes da próxima 1:1 e a gente valida juntos."

---

### 6. Após a 1:1 — validação do dev plan do PM

Quando o gestor receber o dev plan redigido pelo PM:

1. Ler o dev plan redigido pelo PM
2. Comparar com o material de preparação e as notas da 1:1
3. Identificar divergências: o que o PM entendeu diferente do combinado?
4. Gerar feedback para o gestor:
   - O que está alinhado com o combinado
   - O que diverge (sinal de ruído na conversa — trazer para a próxima 1:1)
   - O que está melhor do que o proposto (sinal de internalização)

### 7. Salvar

**Material de preparação:** salvar junto com o prep da 1:1 (não como arquivo separado).
**Dev plan final (redigido pelo PM):** salvar em `/Pessoas/Liderados/[nome]/dev-plans/AAAA-QX.md`.
Atualizar a seção "Plano de Desenvolvimento Ativo" em `profile.md` com referência ao novo arquivo.

**Nota:** o arquivo em dev-plans é o documento do PM, não da liderança. A liderança pode adicionar notas de validação no final.

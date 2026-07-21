# Modo: talking-points-update

Atualiza manualmente o acervo vivo de pauta de uma pessoa — adicionar, remover, repriorizar tópicos fora do ciclo de uma 1:1 específica.

## Quando usar

- Trigger:
  - "adicionar tópico para [nome]: [tema]"
  - "remover [tema] da próxima 1:1 com [nome]"
  - "atualizar pauta de [nome]"
  - "repriorizar [tema] para alta no acervo de [nome]"
- Comando: `/1on1:talking-points [nome]`

**Why existe:** Acervo vive entre 1:1s. O gestor precisa de uma forma rápida de "anota isso para a próxima 1:1 com X" sem abrir o arquivo da última sessão.

## Fluxo

### 1. Identificar pessoa

Glob `/Pessoas/Liderados/[nome]*` e `/Pessoas/Stakeholders/[nome]*`. Mesma lógica de desambiguação dos outros modos.

### 2. Ler acervo atual

Path: `/Pessoas/[Liderados|Stakeholders]/[nome]/pauta.md`

Se não existe:
- Oferecer criar do template `../templates/talking-points.md`
- Confirmar com o gestor antes — pode ser que a pessoa não tenha 1:1 recorrente (stakeholder ocasional)

### 3. Detectar intenção

Pelo trigger:

| Frase | Intenção |
|---|---|
| "adicionar tópico ... [tema]" | Add — capturar tema, prioridade |
| "remover [tema] ..." | Remove — listar abertos, pedir confirmação |
| "repriorizar [tema] para alta" | Reprio — capturar tema + nova prioridade |
| "atualizar pauta de X" (sem objeto direto) | Revisão geral — listar tudo, perguntar o que muda |

Se ambíguo → `AskUserQuestion` com as 4 opções acima.

### 4. Aplicar e mostrar diff

Mesma mecânica do step 8 de `consolidate.md`:

1. Snapshot ANTES
2. Aplicar mudança
3. Mostrar diff explícito:
   ```
   📋 Diff do acervo para [Nome]:

   Adicionar (1):
     + [Pipeline de discovery Q3] (Alta — adicionado manualmente)

   Confirma?
   ```
4. Se sim → escrever
5. Se o gestor ajustar → iterar

### 5. Atualizar frontmatter

- `atualizado_em: AAAA-MM-DD`
- Sem outras mudanças

### 6. Reportar

```
✅ Acervo de [Nome] atualizado.

Diff aplicado:
  + Pipeline de discovery Q3 (Alta)

Total no acervo: N abertos (X alta, Y média, Z baixa), M no histórico.
```

## Princípios

- **Sempre diff antes de escrever.** Mesma regra do `consolidate`.
- **Sem prioridade ambígua.** Se o gestor não disse, perguntar — não inferir.
- **Tópico curto, contexto opcional.** Acervo é índice, não documento. Detalhe vai no arquivo da 1:1 quando o tema for tratado.

## Anti-patterns

- Escrever direto sem mostrar diff → sempre confirmar
- Mover tópico para "Fechado" sem 1:1 associada → fechamento só via `consolidate` (que tem rastro). Aqui só add/remove/reprio.
- Apagar histórico fechado → histórico é auditável; nunca remover

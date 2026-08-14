---
tipo: material-apoio
evento: TDC 2026
trilha: Gestão Ágil e Liderança de Impacto
talk: "Palestra 4 — People OS"
palestrante: Andre Ganske
language: pt-br
status: material-publico
tags: [palestra, tdc, people-os, prompts, ia, gestao-de-pessoas, material-apoio]
---

# Prompts de IA para quem lidera pessoas

Doze prompts prontos para usar hoje, sem instalar nada e sem saber nada de IA. Cada um resolve um pedaço concreto do trabalho de liderar: preparar uma 1:1, ler uma autoavaliação, entrevistar um candidato, ensaiar uma conversa que você está adiando.

Funcionam em qualquer ferramenta de conversa com IA — ChatGPT, Copilot, Claude, Gemini. Você copia o bloco, troca o que está entre `[colchetes]` e cola o seu material junto.

---

## Como usar

**Uma conversa nova para cada prompt.** Threads longas misturam contextos e a qualidade cai.

**A IA não sabe nada além do que você colar.** Ela não conhece a pessoa, o time, a empresa nem o histórico. Resposta genérica quase sempre significa contexto de menos, não prompt ruim.

**Você continua sendo quem decide.** A IA propõe estrutura, pergunta o que você não perguntou e organiza o que já está na sua cabeça. Nada aqui vira decisão sozinha, e nada sai daqui para outra pessoa sem você reescrever com as suas palavras.

**Se a resposta vier ruim, responda a ela.** "Ficou genérico demais, use só o que eu colei" ou "está longo, corte pela metade" funcionam melhor do que começar de novo.

---

## Antes de colar qualquer coisa: privacidade

Este documento trata de material sobre pessoas — desempenho, avaliação, carreira, candidatos. Isso pede cuidado que um prompt de receita de bolo não pede.

- **Troque nomes por iniciais** ou por "a pessoa". Nenhum prompt aqui precisa do nome real para funcionar.
- **Não cole documento de terceiro** (avaliação, salário, laudo, feedback de outra pessoa) em conta pessoal ou gratuita.
- **Verifique o que a sua empresa liberou.** Muitas têm versão corporativa em que o conteúdo não é usado para treinar modelo. Use essa.
- **Regra prática:** se você não mandaria esse texto por e-mail para fora da empresa, não cole numa ferramenta pública.

---

## Parte 1 — O ciclo da 1:1

### 1. O hábito que muda tudo: obrigar a IA a perguntar antes de escrever

A causa número um de resposta ruim é a IA adivinhar o que você quer. Este prompt tira a adivinhação do caminho, e você pode colá-lo antes de qualquer um dos outros.

```
Vou te pedir para preparar [descreva a tarefa em uma frase].

Não escreva nada ainda. Primeiro me faça de 3 a 5 perguntas cujas
respostas mudariam de verdade o resultado — sobre contexto, sobre
o tom que eu quero e sobre o que preciso ter em mãos no final.

Faça uma pergunta por vez e espere minha resposta.
```

**Por que funciona:** você passa de "escreva algo sobre X" para uma conversa em que a IA coleta o que só você sabe. O custo são dois minutos; o ganho é uma resposta sobre a sua situação, não sobre uma situação média.

---

### 2. Preparar uma 1:1 — guia, não roteiro

**Quando usar:** antes de uma conversa individual que importa.
**Cole junto:** os temas que você quer tocar e o que ficou pendente da última vez.

```
Você vai me ajudar a preparar uma conversa individual com alguém do
meu time. Quero um GUIA, não um roteiro.

Contexto:
- Tempo de casa e função da pessoa: [...]
- O que ficou pendente da nossa última conversa: [...]
- Temas que quero tocar: [...]
- Tom que quero: [desenvolvimento / reconhecimento sóbrio /
  alinhamento / conversa difícil]
- Com o que eu preciso sair daqui: [...]
- O que NÃO pode entrar nessa conversa: [...]

Para cada tema, me dê:
1. A intenção em uma frase (o que eu quero com esse tema)
2. Duas perguntas de reserva, para usar só se a conversa travar
3. "O que escutar": um sinal de que está bem e um sinal de alerta,
   cada um com o que provavelmente significa

Depois, uma lista curta de pontos de atenção — coisas que podem dar
errado nessa conversa e por quê.

Regras:
- Sem divisão de tempo por tema
- Sem falas prontas para eu decorar
- Sem me explicar frameworks de gestão, eu conduzo a conversa
- Tom sóbrio: reconhecer sem inflar, cobrar sem punir
```

**Por que funciona:** roteiro cronometrado engessa a conversa e faz você ouvir menos. Alerta e pergunta de reserva fazem o contrário — liberam você para escutar, porque você já sabe onde pisar com cuidado.

**Se travar:** "Os pontos de atenção ficaram óbvios. Me dê os que eu provavelmente não pensei."

---

### 3. Consolidar a conversa depois que ela acabou

**Quando usar:** logo após a 1:1, com as notas ainda cruas.
**Cole junto:** suas anotações, mesmo desorganizadas, ou a transcrição.

```
Abaixo estão minhas notas de uma conversa individual com alguém do
meu time. Organize assim:

**Resumo** — no máximo 3 linhas, só o essencial
**Decisões e acordos** — o que ficou combinado
**Pontos abertos** — o que continua em discussão
**Compromissos da pessoa** — cada um com prazo, se houver
**Compromissos meus** — cada um com prazo, se houver

Regras inegociáveis:
- Não invente nada. Se algo está ambíguo nas notas, escreva
  [não ficou claro] em vez de completar com uma suposição
- Separe os compromissos por dono. Não junte tudo numa lista só
- Não interprete o que a pessoa "quis dizer", registre o que ela disse

Minhas notas:
[cole aqui]
```

**Por que funciona:** dar permissão explícita para dizer "não sei" é o que impede a IA de preencher lacunas com invenção plausível. Separar compromisso por dono evita a armadilha clássica de o gestor sair da conversa carregando a lista inteira.

**Continuação natural:** depois de aprovar o resumo, peça:

```
Agora liste os temas que devem voltar na próxima conversa, em três
grupos: fechados hoje, novos que surgiram, e antigos que mudaram de
prioridade.
```

Guarde essa lista num arquivo por pessoa. Na próxima 1:1, ela é o insumo do prompt 2 — e a preparação passa a levar dois minutos.

---

## Parte 2 — Desenvolver as pessoas

### 4. Transformar uma autoavaliação em três lacunas concretas

**Quando usar:** quando alguém preencheu uma autoavaliação, um assessment ou simplesmente listou o que acha que precisa melhorar.
**Cole junto:** o material, com o nome trocado por iniciais.

```
Abaixo está a autoavaliação de uma pessoa do meu time.

Para cada competência listada, estime dois números de 0 a 10:
- Importância para a função que ela ocupa hoje
- Domínio atual demonstrado no material

Calcule: importância x (10 - domínio). Ordene do maior para o menor
e me mostre as três primeiras.

Para cada uma das três:
- Uma frase dizendo o que muda no trabalho se essa lacuna fechar
- Um comportamento observável que provaria que fechou
- O que NÃO seria evidência (algo que parece progresso mas não é)

Onde o material não der base para estimar, escreva [sem evidência]
em vez de chutar.

Material:
[cole aqui]
```

**Por que funciona:** a conta desempata. Sem ela, todo mundo prioriza a lacuna mais visível — que costuma ser a menos importante. Multiplicar por importância faz a fraqueza irrelevante cair sozinha.

---

### 5. Preparar a conversa de plano de desenvolvimento (sem escrever o plano)

**Quando usar:** antes da conversa de carreira. Depois dela, quem escreve o plano é a pessoa.

```
Vou ter uma conversa de desenvolvimento com alguém do meu time.
Não escreva o plano — quem escreve é ela. Me prepare para a conversa.

Contexto:
- Função e tempo de casa: [...]
- Lacunas identificadas: [...]
- O que ela disse que quer nos próximos 12 a 18 meses: [...]
- O que existe hoje no time que poderia desenvolver isso: [...]

Me dê:
1. Três áreas possíveis para o plano, apresentadas como proposta
   para discutir, não como decisão tomada
2. Para cada área: uma meta concreta e verificável, o indicador que
   mostraria progresso, e o que EU preciso fazer para sustentar
3. Uma área ligada a resultado do negócio, não só a desenvolvimento
   pessoal
4. Duas perguntas para eu abrir a conversa sem já entregar a resposta
```

**Por que funciona:** plano de desenvolvimento escrito pelo gestor vira documento de gaveta. Escrito pela pessoa, vira compromisso — e a diferença entre o que ela escreve e o que vocês combinaram é o melhor termômetro de quanto da conversa realmente chegou.

---

### 6. Ler o plano que a pessoa escreveu como detector de ruído

**Quando usar:** quando o plano volta para você validar.

```
Abaixo estão duas coisas: minhas notas do que combinamos na conversa,
e o plano que a pessoa escreveu depois.

Compare os dois e me diga:
- O que está alinhado com o combinado
- O que diverge, e se a divergência parece ter vindo de eu ter
  explicado mal, dela ter entendido diferente, ou dela discordar
- O que ficou melhor do que o que eu propus

Não me diga se o plano é bom. Me diga onde as duas versões não batem.

Minhas notas:
[cole aqui]

O plano dela:
[cole aqui]
```

**Por que funciona:** a divergência é informação, não erro. Ela mostra exatamente onde a mensagem se perdeu — e essa é a primeira pauta da próxima conversa.

---

### 7. Ensaiar a conversa difícil antes de tê-la

**Quando usar:** feedback duro, mudança de escopo, decisão impopular.

```
Quero ensaiar uma conversa difícil. Você vai fazer o papel da outra
pessoa, e eu faço o meu.

Quem é a pessoa: [função, tempo de casa, como costuma reagir a
crítica, o que a motiva]
O que eu preciso dizer: [...]
O que eu quero que aconteça no final: [...]
Minha maior preocupação com essa conversa: [...]

Regras da simulação:
- Reaja como essa pessoa reagiria, não como a pessoa ideal reagiria
- Se eu enrolar ou suavizar demais, aponte e não deixe passar
- Faça a pergunta que eu não quero ouvir
- Três rodadas, e só depois saia do papel

Comece esperando minha primeira fala.
```

**Por que funciona:** você descobre no ensaio, e não na frente da pessoa, que a sua abertura não se sustenta. Instruir a IA a reagir como a pessoa real, e não como uma pessoa razoável, é o que separa ensaio útil de teatro.

**Depois das três rodadas:** "Sai do papel. Onde eu fui vago? Que frase minha pode ter sido lida de um jeito que eu não quis?"

---

## Parte 3 — Contratar

### 8. Perguntas que furam a apresentação ensaiada

**Quando usar:** antes de entrevistar alguém que vai apresentar um case, um projeto ou um portfólio.

```
Vou entrevistar uma pessoa candidata que vai apresentar [um case /
um projeto que ela conduziu]. A apresentação vai estar ensaiada.

Me dê UMA pergunta aberta para cada camada abaixo:

0. Contexto — o que ela sabia e o que ela não sabia quando começou
1. Problema — como ela chegou à conclusão de que era esse o problema
2. Decisão — por que esse caminho e não outro
3. Alternativa descartada — o que ela deixou de fora e o que custou
4. Evidência — o que ela usou para saber que estava funcionando
5. Pressão — como ela reagiria se a premissa principal caísse
6. Aprendizado — o que ela faria diferente e por quê

Regras:
- Perguntas abertas, que sirvam para qualquer área ou setor
- Não cite nada específico da minha empresa. A pergunta não pode
  virar um teste de conhecimento sobre a casa
- Nada que possa ser respondido com sim ou não
- Nada que julgue a solução dela. Quero avaliar o raciocínio

Abaixo de cada pergunta, escreva "o que observar": um sinal de
profundidade e um sinal de superfície.
```

**Por que funciona:** as sete camadas garantem que nenhuma dimensão fica sem sondagem — o viés entra justamente quando você aprofunda só no que gostou. Manter a pergunta genérica mede como a pessoa pensa, não o quanto ela pesquisou sobre você.

---

### 9. O que vigiar no histórico dessa pessoa

**Quando usar:** junto com o prompt 8, antes da entrevista.
**Cole junto:** currículo ou resumo da trajetória, sem nome.

```
Abaixo está a trajetória de uma pessoa candidata.

Me dê de 2 a 4 pontos de atenção: padrões de raciocínio que valem
observar em silêncio durante a entrevista, dado de onde ela vem.

Formato de cada um: "vem de [contexto] — observar se [padrão possível]".

Regras:
- São notas de leitura minhas, não veredito sobre a pessoa
- Nenhum deles pode virar pergunta na entrevista
- Não conclua nada de senioridade a partir de título de cargo
- Onde o material não permitir uma leitura, diga que não permite

Trajetória:
[cole aqui]
```

**Por que funciona:** o histórico informa o que você observa, nunca o que você pergunta. Perguntar "você não vem de um mundo em que a métrica já vinha pronta?" entrega a resposta. Observar em silêncio deixa a lacuna aparecer sozinha.

---

### 10. Avaliação por evidência, não por impressão

**Quando usar:** logo depois da entrevista, antes de conversar com o resto da banca.
**Cole junto:** suas anotações ou a transcrição.

```
Abaixo estão minhas anotações de uma entrevista. Monte minha
avaliação individual.

Para cada dimensão que eu listar — [liste as suas: entendimento do
problema, priorização, comunicação, uso de evidência, postura sob
pressão] — me dê:
- A evidência observada, citando o que a pessoa efetivamente disse
- Uma nota de 1 a 4 (1 = ausente, 2 = sinal fraco, 3 = sólido,
  4 = excepcional). Sem meio-termo, para forçar posição
- Uma frase de "por que essa nota e não a de cima nem a de baixo"

Regras inegociáveis:
- O que não foi perguntado vira NÃO SONDADO, não vira nota 3 de
  consolo. Liste esses buracos separadamente
- Avalie o raciocínio, não a solução que ela apresentou
- Não compare com nenhum outro candidato. A régua é o critério, não
  quem passou antes
- Se a anotação estiver ambígua, marque [ambíguo] e não preencha

No final: recomendação de contratar ou não, e os temas que ficaram
em aberto para uma próxima etapa.

Anotações:
[cole aqui]
```

**Por que funciona:** exigir a citação antes da nota impede que "pareceu sênior" vire avaliação. E o campo "por que essa nota e não a de cima" é o que te obriga a explicitar a régua — que é exatamente o que a banca precisa ouvir no debate.

---

## Parte 4 — Você

### 11. Me mostre o que eu não estou vendo

**Quando usar:** quando você está confortável demais com a sua própria leitura.

```
Quero que você me provoque, não que me apoie.

Minha situação: [descreva em 5 a 10 linhas — o que está acontecendo,
o que você decidiu, o que está adiando]
O que eu já tentei: [...]
A história que eu conto para mim mesmo sobre por que ainda não
resolvi: [...]

Me diga:
- Qual padrão você enxerga que eu provavelmente não quero enxergar
- Que evidência do que eu escrevi sustenta isso

Regras:
- Uma provocação só, a mais incômoda. Não empilhe várias
- Baseie no que eu escrevi, não em psicologia genérica
- Termine com uma pergunta que eu tenha que responder agora
```

**Variante mais leve, para o fim da semana:** troque a última parte por "me faça três perguntas sobre essa semana: uma sobre o que funcionou, uma sobre o que eu evitei, e uma sobre o que eu vou fazer diferente. Uma de cada vez."

**Por que funciona:** IA tende a concordar com você — é o comportamento padrão dela. Pedir explicitamente provocação ancorada em evidência do seu próprio texto é o que quebra isso. Uma provocação por vez, porque cinco viram ruído.

---

### 12. Ensaiar a conversa com quem decide

**Quando usar:** antes de pedir orçamento, defender uma decisão ou apresentar para alguém acima de você.

```
Você vai fazer o papel de [diretor / cliente / conselho / quem for].
Eu vou apresentar e você reage.

Quem é essa pessoa: [o que ela cobra, o que ela não tolera, o que
já disse não antes]
O que eu quero no final: [decisão / aprovação / orçamento / alinhamento]
Minha maior preocupação: [...]

No papel, você:
- Me interrompe se eu começar pelo detalhe em vez do impacto
- Pede número quando eu falar em termos vagos
- Ataca a premissa mais frágil do que eu disser
- Faz a pergunta que eu não quero ouvir

Três rodadas. Depois sai do papel e me diz: onde eu perdi você, e
qual seria a abertura de 30 segundos mais forte que a minha.

Minha abertura:
[cole aqui]
```

**Por que funciona:** quase toda apresentação para quem decide morre nos primeiros trinta segundos, por começar pelo caminho percorrido em vez do resultado. Você descobre isso no ensaio ou descobre na sala.

---

## O que faz esses prompts funcionarem

Se você entender estes seis pontos, escreve os seus próprios e não precisa mais deste documento.

1. **Papel e objetivo antes de tudo.** "Você vai me ajudar a preparar X, e eu preciso sair com Y" vale mais do que qualquer refinamento posterior.
2. **Material bruto ganha de descrição.** Colar suas anotações desorganizadas produz resultado melhor do que resumir bem o que aconteceu.
3. **Peça o formato.** Se você não disser como quer a saída, recebe cinco parágrafos corridos que ninguém lê.
4. **Diga o que você NÃO quer.** As restrições ("sem falas prontas", "sem me explicar frameworks", "sem comparar com outros") carregam mais informação do que os pedidos.
5. **Dê permissão para não saber.** `[não ficou claro]`, `[sem evidência]`, `NÃO SONDADO`. Sem isso, a lacuna vira invenção plausível — e invenção plausível é o erro mais caro, porque parece certa.
6. **Mande perguntar antes de gerar.** É o prompt 1, e ele melhora todos os outros.

---

## Quando não usar nada disso

- **Decisão sobre a vida de alguém.** Desligamento, promoção, nota final de avaliação. A IA organiza o material que sustenta a decisão; ela não toma a decisão.
- **Pessoa em sofrimento.** Problema de saúde, luto, crise pessoal. Isso pede presença, não estrutura.
- **Texto que vai direto para a pessoa.** Feedback, mensagem, resposta a candidato. Reescreva com as suas palavras, sempre. Quem recebe percebe quando não é você falando — e isso custa mais do que o tempo que você economizou.

---

## De onde vieram estes prompts

Cada prompt aqui é a **versão sem setup** de uma skill deste repositório. As skills
carregam mais: perfil acumulativo por pessoa, estado que sobrevive entre conversas,
guardrails e templates. Os prompts carregam só o método — que é o que dá para
experimentar em cinco minutos, numa aba do navegador.

| Prompts | Skill equivalente | O que a skill acrescenta |
|---|---|---|
| 1 a 3 | [`one-on-one/`](../one-on-one/SKILL.md) | arquivo único vivo por sessão, backlog de temas que persiste entre 1:1s |
| 4 a 7 | [`team-coach/`](../team-coach/SKILL.md) | perfil acumulativo, assessment dimensional, PDI via 70-20-10, dry run |
| 8 a 10 | *(sem equivalente aqui)* | o kit de contratação não faz parte deste recorte |
| 11 e 12 | [`self-coach/`](../self-coach/SKILL.md) | guardrails pessoais, bench de especialistas, log de compromissos |

Se algum destes prompts virar hábito, é sinal de que vale montar a skill —
o ganho da skill está justamente em não recomeçar do zero toda conversa.

Repositório: **github.com/andreganske/skills-liderancas**


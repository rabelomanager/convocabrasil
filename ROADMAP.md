# 🗺️ Roadmap — Convocação da Seleção 🇧🇷

Documento de planejamento das próximas fases do site. Não é um cronograma com datas — é a ordem
sugerida do que construir, com uma noção de tamanho de cada coisa e do que cada uma exige.

## Legenda

- 🟢 **Rápido** — dá pra fazer em cima do que já existe, só no navegador.
- 🟡 **Médio** — algumas telas/lógicas novas, mas ainda sem servidor.
- 🔴 **Grande** — recurso robusto, pode exigir servidor (banco de dados) e/ou muita lógica nova.
- 🖥️ **Precisa de servidor** — não dá pra fazer só com o arquivo local; exige um backend (ex.: Supabase).

---

## ✅ Onde estamos hoje (v1 — no ar em convocabrasil.vercel.app)

- Tela inicial (Copa 2030) + convocação de 26 jogadores.
- Base de ~1.500 jogadores brasileiros (Brasileirão + ligas do mundo), sem duplicatas, com Overall
  invisível (EA FC) para ordenar.
- Campo com arrastar-e-soltar, 9 formações, capitão, escalação automática.
- Filtros (posição, liga, clube, idade), fotos dos principais, pé de preferência.
- Tela de compartilhamento (imagem para WhatsApp/Instagram/X) + QR de apoio.

---

## 🎯 Fase 1 — Cobradores e bola parada  🟢

O primeiro passo natural: em cima da escalação que já existe, escolher quem cobra o quê.

- **Batedor de falta**, **batedor de escanteio** e **batedor de pênalti** — escolhidos entre os 11 em campo.
- **Sequência de cobradores de pênalti** — uma lista ordenável (1º, 2º, 3º…) para a disputa por pênaltis,
  montada arrastando os jogadores.
- Essas escolhas ficam salvas junto da escalação e aparecem na imagem de compartilhamento.

**Por que primeiro:** é leve, não precisa de servidor e já deixa a escalação "completa". Além disso,
essas informações vão **alimentar a simulação** da Fase 3 (quem bate o pênalti importa no jogo).

---

## 📊 Fase 2 — Estatísticas de escalações

Duas versões, bem diferentes em tamanho:

- **2A · Suas estatísticas (neste aparelho)**  🟢
  Quantas vezes *você* escalou cada jogador, seus mais convocados por posição, formação favorita.
  Dá pra fazer só no navegador (guardando o histórico localmente).

- **2B · Ranking global (todos os usuários)**  🔴 🖥️
  "Jogadores mais escalados por posição" somando **todo mundo que usa o site**. Isso é o que você
  pediu, e é ótimo — mas exige um **servidor/banco de dados** (ex.: Supabase) para juntar as
  convocações de todas as pessoas num lugar só. Sem backend, cada celular só conhece a própria história.

  > Aqui é onde o **Supabase** (que a gente tinha deixado de lado) finalmente faz sentido. Quando
  > quisermos ranking global, compartilhar convocação por link, ou placar entre amigos, é a hora de ligá-lo.

---

## 🏆 Fase 3 — Modo Copa do Mundo (simulação, estilo 7a0.com.br)  🔴

O grande sonho: a sua seleção **joga contra outras seleções do mundo**, num formato de Copa, com o
jogo sendo simulado e mostrado num campo — a dinâmica que você curte no 7a0.com.br. É a fase mais
pesada, então melhor quebrar em pedaços:

- **3A · Adversários (seleções do mundo)**  🟡🔴
  Precisamos de outras seleções para enfrentar. Duas abordagens:
  - *Simples:* cada seleção tem uma "força" geral (ataque/meio/defesa) — rápido de montar.
  - *Completa:* cada seleção com seu elenco real e overalls (mais pesquisa de dados, como fizemos com o Brasil).

- **3B · Motor de simulação**  🔴
  O "cérebro" que decide o resultado do jogo a partir dos **overalls**, da formação, dos **cobradores**
  (Fase 1) e de um tanto de **sorte** (senão todo jogo dá o mesmo placar). Gera gols, lances, cartões,
  e vai até a disputa de pênaltis usando a sua sequência de cobradores. Roda no navegador, sem servidor.

- **3C · Campo animado (a "transmissão")**  🔴
  Mostrar o jogo acontecendo: bolinha se movendo no campo, placar subindo, narração dos lances
  ("Gol do Brasil!"). É a parte mais trabalhosa (animação), mas é o que dá emoção — o coração do estilo 7a0.

- **3D · Chaveamento de Copa**  🟡
  Fase de grupos + mata-mata, mostrando o **seu caminho até o título** (oitavas, quartas, semi, final)
  e um troféu no fim. 🏆

**Dependência:** a Fase 1 (cobradores) deve vir antes, porque a simulação usa essas escolhas.

---

## 🧭 Ordem sugerida

1. **Fase 1** — cobradores e bola parada (rápido, e prepara o terreno da simulação).
2. **Fase 2A** — suas estatísticas locais (rápido, valor imediato).
3. **Fase 3**, em pedaços: 3A (adversários simples) → 3B (motor) → 3C (campo animado) → 3D (chaveamento).
4. **Fase 2B / Supabase** — ranking global e recursos online, quando decidirmos ligar um servidor.

---

## ❓ Decisões que vamos precisar tomar

- **Ligar um servidor (Supabase)?** Necessário para ranking global de mais escalados, compartilhar
  convocação por link e placares entre amigos. Enquanto for tudo "no seu aparelho", não precisa.
- **Dados das outras seleções:** força geral (simples) ou elenco completo real (mais rico, mais pesquisa)?
- **Nível de realismo da simulação:** mais "arcade e divertido" ou mais "estatístico e realista"?

---

## 💡 Backlog (ideias soltas para o futuro)

- Compartilhar a escalação por **link** (a pessoa abre e vê seu time).
- **Modo lendas** (craques históricos do Brasil).
- Escolher **técnico** e esquema tático que influencie a simulação.
- **Ranking** de quem fez a "convocação mais parecida com a oficial".
- Narração/replay dos melhores momentos do jogo simulado.

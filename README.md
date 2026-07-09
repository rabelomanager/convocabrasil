# Convocação da Seleção 🇧🇷 — Copa 2030

Você é o treinador da Seleção Brasileira: monte a sua convocação de 26 jogadores e escale o time num
campo, arrastando os jogadores. Tema verde-amarelo-azul, **sem login**, funciona no computador e no celular.

🌐 No ar em **convocabrasil.vercel.app** · 📷 Instagram: **@brasilconvoca**

## O que tem

- **~1.500 jogadores brasileiros** das principais ligas do mundo + Brasileirão completo + destaques da base
  (dados pesquisados em julho/2026, sem duplicatas — cruzando nome, clube e idade).
- **Tela inicial** com a chamada da Copa 2030.
- **Overall invisível** (usado só para ordenar "melhores primeiro"): baseado no **EA Sports FC** quando
  existe; senão, estimado por liga, estatísticas e comparação com jogadores da mesma posição.
- **Filtros**: posição (goleiro, laterais dir./esq., zagueiro, volante, meia, pontas dir./esq., centroavante),
  liga, clube, idade, busca por nome, "convocados na Copa 2026" e "convocados recentes".
- Jogadores podem ter **mais de uma posição**; **foto** e **pé de preferência** nos principais.
- Estatísticas mostradas são as **pela Seleção Brasileira** (jogos/gols/assistências), não do clube.
- Campo com **arrastar e soltar**, **9 formações**, **capitão** (toque no jogador → botão "tornar capitão")
  e **escalação automática**.
- **Cobradores de bola parada**: batedor de falta, de escanteio e a **sequência de cobradores de pênalti**.
- **Tela de compartilhamento**: gera uma imagem da escalação para WhatsApp, Instagram, X ou download.
- **Popup de apoio** com QR Code no canto.
- Salva a sua convocação no próprio navegador (localStorage).

## Como usar

Abra o arquivo `index.html` no navegador (dois cliques). É um site estático — **um único arquivo, sem
servidor, funciona offline**. Tudo (jogadores, fotos, QR) está embutido no próprio `index.html`.

## Atualizar o site no ar

O site já está publicado na Vercel, ligado a um repositório no GitHub. Para publicar uma versão nova:

1. Suba o `index.html` atualizado para o repositório no GitHub (substituindo o arquivo).
2. A Vercel republica sozinha em segundos, no mesmo link.

Primeira publicação (se for montar do zero): crie um repositório no GitHub, suba o `index.html` e importe
o repositório em https://vercel.com → **Add New… → Project** (site estático, sem configuração).

## Roadmap

Veja **[ROADMAP.md](ROADMAP.md)** para as próximas fases. Resumo:

- ✅ **Fase 1 — Cobradores de bola parada** (falta, escanteio, sequência de pênaltis) — concluída.
- **Fase 2 — Estatísticas de escalações** (suas, locais; e ranking global de mais escalados por posição,
  que exigiria um servidor/Supabase).
- **Fase 3 — Modo Copa do Mundo**: a sua seleção joga contra outras, com simulação e campo animado
  (estilo 7a0.com.br), até o título.

## Observações técnicas

- **Não busca dados ao vivo**: os jogadores ficam embutidos no arquivo (sites como Transfermarkt bloqueiam
  acesso automático de uma página). Atualizar a base exige uma nova pesquisa e reinjetar os dados.
- **Fonte de nome/clube/idade**: Transfermarkt. O EA FC é usado **apenas** para o número do Overall
  (os nomes/times dele nem sempre estão atualizados).
- **Sem backend hoje**: tudo roda no navegador. Um servidor (ex.: Supabase) só entra na Fase 2/3, para
  ranking global, compartilhar convocação por link ou a simulação online.

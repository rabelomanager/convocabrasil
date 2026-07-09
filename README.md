# Convocação da Seleção 🇧🇷 — Copa 2026

Site para você montar a sua convocação da Seleção Brasileira (26 jogadores) e escalar o time num campo, arrastando os jogadores. Tema verde-amarelo-azul, sem login, funciona no computador e no celular.

## O que tem
- **Quase 1500 jogadores brasileiros** das principais ligas do mundo (dados pesquisados em 06/07/2026).
- Overall baseado no **EA Sports FC** (invisível, usado para ordenar "melhores primeiro").
- Filtros por **posição, liga, clube, idade** e busca por nome.
- Jogadores podem ter **mais de uma posição**.
- **Foto** dos jogadores com overall acima de 80.
- Campo de futebol com **arrastar e soltar**, 5 formações, capitão e escalação automática.
- **Tela de compartilhamento**: gera uma imagem da escalação para WhatsApp, Instagram, X ou download.
- Salva a sua convocação no próprio navegador (localStorage).

## Como usar
Abra o arquivo `index.html` no navegador. É um site estático — **um único arquivo, sem servidor**.

## Publicar na Vercel (grátis, sem instalar nada)
1. Acesse https://vercel.com e entre com sua conta (pode usar o login do GitHub).
2. Clique em **Add New… → Project**.
3. Se você subiu este repositório para o GitHub, escolha **Import** no repositório.
   Ou, sem GitHub, use **Deploy** e **arraste a pasta `selecao`** inteira para a área de upload.
4. A Vercel detecta um site estático automaticamente (não precisa de configuração) e publica.
5. Pronto — você recebe um link público (ex.: `sua-selecao.vercel.app`).

## Observações
- **Não busca dados ao vivo**: os jogadores ficam embutidos no arquivo (sites como Transfermarkt bloqueiam acesso automático). Para atualizar, é preciso uma nova pesquisa.
- **Supabase não é necessário** neste momento: o app não tem backend nem login. Só faria sentido se um dia você quiser guardar convocações num servidor ou ter uma galeria pública.

# Wagner Fotografia — Estratégia, Análise e Produto

Repositório do projeto Wagner Oliveira | Eventos & Retratos (Grande Vitória/ES). Reúne três blocos:

1. **`analise/`** — auditoria do Instagram [@fotowagando](https://www.instagram.com/fotowagando/) sob óticas de posicionamento (fotógrafo de aniversário) e branding pessoal.
2. **`benchmarking/`** — pesquisa de mercado: preços, posicionamento de concorrentes, presença digital, playbook de vendas, referências, tech stack e add-ons.
3. **`galeria-qr/`** — produto/MVP de galeria interativa via QR code para festas (Next.js + Postgres + MinIO via Docker).

---

## Sumário — Análise do Instagram

| Documento | Conteúdo |
|---|---|
| [`analise/00-resumo-executivo.md`](analise/00-resumo-executivo.md) | Diagnóstico em uma frase, dados objetivos do perfil, índice |
| [`analise/01-posicionamento-aniversario.md`](analise/01-posicionamento-aniversario.md) | Análise do especialista em posicionamento para fotógrafos de aniversário |
| [`analise/02-instagram-branding-pessoal.md`](analise/02-instagram-branding-pessoal.md) | Análise do especialista em Instagram & Branding Pessoal |
| [`analise/03-plano-execucao-30-dias.md`](analise/03-plano-execucao-30-dias.md) | Plano de ação cronológico + métricas baseline e metas 30/90 dias |
| [`analise/04-prints-referencia.md`](analise/04-prints-referencia.md) | Índice dos prints capturados e metadados extraídos do DOM |
| [`prints/`](prints/) | 6 screenshots do perfil capturados via playwright-cli em 2026-04-25 |

## Sumário — Benchmarking

| Documento | Conteúdo |
|---|---|
| [`benchmarking/00-sintese-estrategica.md`](benchmarking/00-sintese-estrategica.md) | Síntese executiva da pesquisa de mercado |
| [`benchmarking/01-precos.md`](benchmarking/01-precos.md) | Tabelas de preços de concorrentes |
| [`benchmarking/02-posicionamento.md`](benchmarking/02-posicionamento.md) | Mapas de posicionamento |
| [`benchmarking/03-presenca-digital.md`](benchmarking/03-presenca-digital.md) | Análise de presença digital comparada |
| [`benchmarking/04-playbook-vendas.md`](benchmarking/04-playbook-vendas.md) | Playbook de vendas |
| [`benchmarking/05-referencias.md`](benchmarking/05-referencias.md) | Fontes e referências |
| [`benchmarking/06-tech-stack.md`](benchmarking/06-tech-stack.md) | Tech stack avaliado |
| [`benchmarking/07-addons-linguagem-cliente.md`](benchmarking/07-addons-linguagem-cliente.md) | Add-ons na linguagem do cliente |

## Produto — Galeria QR

Aplicação Next.js para galeria interativa de festas: convidados escaneiam QR, fazem upload pelo navegador (sem app), mídia aparece em slideshow ao vivo. Stack: Next.js + Postgres + MinIO (S3-compatible) via Docker Compose.

```bash
cd galeria-qr
cp .env.example .env
docker compose up
```

Detalhes em [`galeria-qr/README.md`](galeria-qr/README.md).

---

## TL;DR

> A bio promete três produtos (casamentos, aniversários, ensaios), mas a vitrine entrega quase só **ensaios femininos** + **carnaval pessoal**. O aniversariante que abre o perfil não vê provas de que Wagner é a pessoa certa para contratar.

**Maior alavanca:** decidir o sub-nicho âncora dentro de "aniversário" (smash the cake / festa infantil / debutante / aniversário adulto), reposicionar o grid em 90 dias e ativar o canal de captação que hoje não existe (sem link clicável, sem botão WhatsApp, categoria genérica).

---

## Como a coleta foi feita

```bash
playwright-cli open https://www.instagram.com/fotowagando/
playwright-cli press Escape          # fechar dialog de login
playwright-cli screenshot --filename=prints/01-perfil-topo.png
playwright-cli eval "() => document.querySelector('header section')?.innerText"
playwright-cli eval "() => [...document.querySelectorAll('main img')].map(i => i.alt)"
# scroll + screenshot até o paywall do Instagram
```

---

## Licença

Conteúdo analítico autoral. Os prints contêm imagens originais do perfil [@fotowagando](https://www.instagram.com/fotowagando/) e são reproduzidos aqui para fins de análise.

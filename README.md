# Análise de Posicionamento — @fotowagando

Auditoria estratégica do perfil Instagram [@fotowagando](https://www.instagram.com/fotowagando/) (Wagner Oliveira | Eventos & Retratos — Grande Vitória/ES) sob duas óticas especialistas:

1. **Posicionamento para fotógrafos de aniversário**
2. **Instagram & Branding Pessoal**

Coleta feita em **2026-04-25** via `playwright-cli`, com extração de DOM dos 28 posts visíveis e captura de prints do header, bio e grid.

---

## Sumário

| Documento | Conteúdo |
|---|---|
| [`analise/00-resumo-executivo.md`](analise/00-resumo-executivo.md) | Diagnóstico em uma frase, dados objetivos do perfil, índice |
| [`analise/01-posicionamento-aniversario.md`](analise/01-posicionamento-aniversario.md) | Análise do especialista em posicionamento para fotógrafos de aniversário |
| [`analise/02-instagram-branding-pessoal.md`](analise/02-instagram-branding-pessoal.md) | Análise do especialista em Instagram & Branding Pessoal — bio, highlights, grid, formato |
| [`analise/03-plano-execucao-30-dias.md`](analise/03-plano-execucao-30-dias.md) | Plano de ação cronológico + métricas baseline e metas 30/90 dias |
| [`analise/04-prints-referencia.md`](analise/04-prints-referencia.md) | Índice dos prints capturados e metadados extraídos do DOM |
| [`prints/`](prints/) | 6 screenshots do perfil capturados via playwright-cli |

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

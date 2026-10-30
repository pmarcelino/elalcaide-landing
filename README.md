# Landing page — elalcaide.investments

Site estático (HTML + CSS, sem build). Texto: `guidelines.md`. Logótipo original: `el-alcaide-logo.PNG`; versões web em `assets/` (`logo-mark.png`, `favicon.svg`, `apple-touch-icon.png`, `og-image.png`).

## Deploy

Custo: 0 €. GitHub Pages serve o repositório público [`pmarcelino/elalcaide-landing`](https://github.com/pmarcelino/elalcaide-landing), branch `main`, pasta `/`.

- **Publicar:** `git commit` + `git push`. O Pages reconstrói em ~1 min.
- **Domínio:** ficheiro `CNAME` (`elalcaide.investments`) + definição *Custom domain* no repo. HTTPS por certificado Let's Encrypt emitido pelo GitHub, *Enforce HTTPS* ligado.
  - Se o certificado não aparecer (≈30 min sem emissão, como a 30/out/2026), remover e voltar a pôr o domínio: `gh api -X PUT repos/pmarcelino/elalcaide-landing/pages -F cname=null`, depois `-f cname=elalcaide.investments`, e ligar `-F https_enforced=true` quando `https_certificate.state` for `approved`. Isto cria commits `Delete CNAME`/`Create CNAME` no GitHub → fazer `git pull --rebase` antes do próximo push.
- **DNS** (na Cloudflare; a GoDaddy só regista o domínio — ver `../email-contato/README.md`). Todos **DNS only** (proxy desligado), senão o GitHub não consegue emitir/renovar o certificado:

| Tipo | Nome | Conteúdo |
|---|---|---|
| A ×4 | @ | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` |
| AAAA ×4 | @ | `2606:50c0:8000::153` … `2606:50c0:8003::153` |
| CNAME | www | `pmarcelino.github.io` (o Pages redireciona para o apex) |

## Pré-visualizar localmente

`python3 -m http.server 8765` nesta pasta → http://127.0.0.1:8765/

## Portfólio

Secção *Nossos Investimentos* (`index.html`, lista `.portfolio`). Para um novo projeto, duplicar o `<li class="portfolio-item">`. Não publicar preços, números de unidade nem estado contratual. Ilustrações em SVG próprio; não usar fotos de incorporadoras sem autorização.

| # | Projeto | Fonte dos dados |
|---|---|---|
| 01 | Inside Brooklin (torre de studios do Condomínio Infinity Brooklin, Teixeira Duarte) — 2 studios de 21 m², pronto 2026 | [Página Teixeira Duarte](https://www.teixeiraduarte.com.br/imoveis/inside-brooklin/) |

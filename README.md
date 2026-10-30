# Landing page — elalcaide.investments

Static site (HTML + CSS, no build step). Copy source: `guidelines.md`. Logo source: `el-alcaide-logo.PNG`; web assets in `assets/`.

## Deploy

Custo: 0 €. GitHub Pages serve o repositório público [`pmarcelino/elalcaide-landing`](https://github.com/pmarcelino/elalcaide-landing), branch `main`, pasta `/`.

- **Publicar:** `git commit` + `git push`. O Pages reconstrói em ~1 min.
- **Domínio:** ficheiro `CNAME` (`elalcaide.investments`) + definição *Custom domain* no repo. HTTPS por certificado Let's Encrypt emitido pelo GitHub, *Enforce HTTPS* ligado.
- **DNS** (na Cloudflare; a GoDaddy só regista o domínio — ver `../email-contato/README.md`). Todos **DNS only** (proxy desligado), senão o GitHub não consegue emitir/renovar o certificado:

| Tipo | Nome | Conteúdo |
|---|---|---|
| A ×4 | @ | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` |
| AAAA ×4 | @ | `2606:50c0:8000::153` … `2606:50c0:8003::153` |
| CNAME | www | `pmarcelino.github.io` (o Pages redireciona para o apex) |

## Pré-visualizar localmente

`python3 -m http.server 8765` nesta pasta → http://127.0.0.1:8765/

## Portfólio

Secção *Nossos Investimentos* (`index.html`, lista `.portfolio`). Para um novo projeto, duplicar o `<li class="portfolio-item">`. Não publicar preços, números de unidade nem estado contratual.

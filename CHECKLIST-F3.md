# Checklist F3 — Publicar InovaLar no GitHub Pages + DNS

Data prevista: amanhã. Passos abaixo, com os valores exatos.

## Antes (repositório já pronto)
- [x] `.nojekyll` criado (evita o Jekyll processar o site)
- [x] `CNAME` com `pmorollo.shop` no repo (já existe)
- [x] `sitemap.xml`, `robots.txt`, canonical ok (commit `1480ccf` envido)
- [ ] Confirmar último push: `git push` em `C:\Users\pedro\.gemini\antigravity\scratch\inovalar`

## 1. Ativar GitHub Pages (3 min)
Acessar `https://github.com/pmorollo/inovalar` → aba **Settings** → **Pages** (menu lateral):

1. Em "Build and deployment", Source: **Deploy from a branch**.
2. Branch: **main** → pasta: **/ (root)** → **Save**.
3. Aguardar o badge "Your site is live at `https://pmorollo.github.io/inovalar/`" (leva ~1 min).
4. Depois de ativo, o Pages passa a servir o domínio customizado automaticamente porque o `CNAME` está no repo.

## 2. Registrar o domínio no Pages (opcional mas recomendado)
No mesmo Settings → Pages, seção "Custom domain":

1. Digitar `pmorollo.shop` → **Save**.
2. Marcar **Enforce HTTPS** (após o DNS propagar).

## 3. Configurar DNS no registrar
O domínio `pmorollo.shop` está registrado onde? (verificar — Namecheap/GoDaddy/Registrador BR).

Dependendo do registrar, usar UMA das duas opções:

### Opção 3A — se o registrar aceitar registros A (recomendado)
4 registros **A** apontando para os IPs do GitHub Pages:

| Tipo | Nome/host | Valor           |
|------|-----------|-----------------|
| A    | @         | 185.199.108.133 |
| A    | @         | 185.199.109.133 |
| A    | @         | 185.199.110.133 |
| A    | @         | 185.199.111.133 |

### Opção 3B — se só aceitar CNAME no apex (alguns registradores)
| Tipo  | Nome/host | Valor                    |
|-------|-----------|--------------------------|
| CNAME | @         | `pmorollo.github.io`     |

> Alguns registradores não permitem CNAME no apex; nesses casos a opção 3A é obrigatória.

## 4. Verificação (5–15 min após DNS)
- `ping pmorollo.shop` → deve resolver para `185.199.108.x` (ou retornar "host found").
- Acessar `https://pmorollo.shop` → deve carregar o site com cadeado HTTPS.
- Acessar `https://pmorollo.github.io/inovalar/` → mesmo conteúdo.
- Testar 1–2 páginas internas (ex.: `/artigos/tirar-mofo-parede.html`).

## 5. Pós-publicação (configurar hoje à noite ou amanhã)
- [ ] Criar conta no **Google Search Console** (`search.google.com/search-console`) e adicionar a propriedade `https://pmorollo.shop`.
- [ ] Enviar `https://pmorollo.shop/sitemap.xml`.
- [ ] Criar conta no Google Analytics 4 e adicionar a tag no `<head>` do `index.html` (avisa que eu insiro o snippet).

## Links úteis
- Docs oficiais GitHub Pages custom domain: `https://docs.github.com/pt/pages/configuring-a-custom-domain-for-your-github-pages-site`
- Lista de IPs do GitHub Pages (se mudar no futuro): `https://api.github.com/meta`
# Checklist F3 — corrigir HTTPS e publicar o InovaLar

Atualizado em 16 de agosto de 2026.

## Situação encontrada

- [x] `CNAME` contém `pmorollo.shop`.
- [x] `.nojekyll`, `robots.txt` e `sitemap.xml` existem no projeto.
- [x] Os 30 artigos e o catálogo foram publicados.
- [x] A propriedade do Search Console foi informada como já configurada pelo responsável.
- [x] O endereço público está saudável: em 16/08/2026, HTTPS respondeu com status 200 e HTTP redirecionou para HTTPS.
- [x] As alterações desta etapa foram enviadas ao branch `main`.

## 1. Conferir a origem do domínio

No GitHub, abrir o repositório do InovaLar em **Settings → Pages**:

1. Confirmar que a publicação usa a branch correta e a pasta `/ (root)`.
2. Em **Custom domain**, confirmar exatamente `pmorollo.shop`.
3. Não cadastrar `www.pmorollo.shop` no lugar do domínio principal sem decidir e configurar esse endereço separadamente.
4. Aguardar a verificação de DNS e a emissão do certificado antes de exigir HTTPS.

Documentação: https://docs.github.com/pt/pages/configuring-a-custom-domain-for-your-github-pages-site

## 2. Conferir o DNS no provedor do domínio

Para o domínio raiz `pmorollo.shop`, os registros A recomendados pelo GitHub Pages são:

| Tipo | Host | Valor |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

Verificar também:

- se existe A, AAAA, CNAME, encaminhamento ou proxy conflitante no host `@`;
- se a hospedagem que apresenta o certificado é realmente a que deve servir o site;
- se o domínio customizado aparece como verificado na configuração do Pages;
- se mudanças recentes de DNS já terminaram de propagar.

Não misturar registros de duas hospedagens diferentes. Se houver proxy de CDN, confirmar primeiro a configuração recomendada pelo respectivo provedor.

## 3. Confirmar o certificado

Depois que o GitHub Pages reconhecer o DNS:

- [x] aguardar a emissão do certificado para `pmorollo.shop`;
- [x] ativar **Enforce HTTPS** quando a opção estiver disponível;
- [x] abrir `https://pmorollo.shop/` sem aviso de certificado;
- [x] confirmar o certificado pela conexão HTTPS válida para `pmorollo.shop`.

## 4. Publicar a cópia validada

Esta etapa exige autorização explícita do responsável antes de qualquer push.

- [x] revisar o resumo do `git diff`;
- [x] criar um commit local identificando a conclusão dos 30 artigos;
- [x] solicitar e registrar a autorização de publicação;
- [x] enviar o conteúdo ao branch `main`;
- [x] acompanhar o GitHub Pages até o conteúdo responder no domínio.

## 5. Validar o site publicado

- [x] home abre em HTTPS;
- [x] `artigos.html` lista os 30 guias;
- [x] pelo menos um artigo novo abre corretamente;
- [x] imagens WebP respondem no domínio publicado;
- [ ] navegação, foco e leitura funcionam em largura móvel;
- [x] `robots.txt` abre;
- [x] `sitemap.xml` abre e contém 36 URLs;
- [x] não há redirecionamento para domínio inesperado nem erro 502.

## 6. Search Console

Com o endereço saudável:

- [ ] abrir a propriedade já criada para `pmorollo.shop`;
- [ ] enviar `https://pmorollo.shop/sitemap.xml`;
- [ ] inspecionar a home e `https://pmorollo.shop/artigos.html`;
- [ ] solicitar indexação apenas das páginas prioritárias, sem repetir pedidos em massa;
- [ ] acompanhar páginas descobertas, indexadas e excluídas nas semanas seguintes.

Ser verificado no Search Console não garante indexação imediata. O primeiro requisito é o Google conseguir acessar as páginas com HTTPS válido e resposta normal.

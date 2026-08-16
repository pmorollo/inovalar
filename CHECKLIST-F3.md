# Checklist F3 — corrigir HTTPS e publicar o InovaLar

Atualizado em 15 de agosto de 2026.

## Situação encontrada

- [x] `CNAME` contém `pmorollo.shop`.
- [x] `.nojekyll`, `robots.txt` e `sitemap.xml` existem no projeto.
- [x] Os 30 artigos e o catálogo foram concluídos na cópia de trabalho.
- [x] A propriedade do Search Console foi informada como já configurada pelo responsável.
- [ ] O endereço público está saudável: em 15/08/2026, `http://pmorollo.shop/` redirecionou para HTTPS e retornou `502 Bad Gateway` por incompatibilidade do certificado com o hostname.
- [ ] As alterações desta etapa foram enviadas ao repositório remoto.

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

- [ ] aguardar a emissão do certificado para `pmorollo.shop`;
- [ ] ativar **Enforce HTTPS** quando a opção estiver disponível;
- [ ] abrir `https://pmorollo.shop/` sem aviso de certificado;
- [ ] confirmar que o certificado apresentado inclui o hostname `pmorollo.shop`.

## 4. Publicar a cópia validada

Esta etapa exige autorização explícita do responsável antes de qualquer push.

- [ ] revisar o resumo do `git diff`;
- [ ] criar um commit local identificando a conclusão dos 30 artigos;
- [ ] solicitar ou registrar a autorização de push;
- [ ] enviar a branch correta ao remoto;
- [ ] acompanhar a execução do GitHub Pages até concluir.

## 5. Validar o site publicado

- [ ] home abre em HTTPS;
- [ ] `artigos.html` lista os 30 guias;
- [ ] pelo menos um artigo de cada categoria abre corretamente;
- [ ] imagens carregam em computador e celular;
- [ ] navegação, foco e leitura funcionam em largura móvel;
- [ ] `robots.txt` abre;
- [ ] `sitemap.xml` abre e contém 36 URLs;
- [ ] não há redirecionamento para domínio inesperado nem erro 502.

## 6. Search Console

Com o endereço saudável:

- [ ] abrir a propriedade já criada para `pmorollo.shop`;
- [ ] enviar `https://pmorollo.shop/sitemap.xml`;
- [ ] inspecionar a home e `https://pmorollo.shop/artigos.html`;
- [ ] solicitar indexação apenas das páginas prioritárias, sem repetir pedidos em massa;
- [ ] acompanhar páginas descobertas, indexadas e excluídas nas semanas seguintes.

Ser verificado no Search Console não garante indexação imediata. O primeiro requisito é o Google conseguir acessar as páginas com HTTPS válido e resposta normal.

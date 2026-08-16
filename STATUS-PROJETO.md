# Status do projeto — InovaLar

Atualizado em 15 de agosto de 2026.

## Resultado desta etapa

O conjunto editorial inicial chegou a **30 artigos prontos na cópia de trabalho**. A meta mínima de conteúdo foi atingida sem ativar anúncios, afiliados ou alegações de testes próprios.

O site agora contém:

- 30 artigos distribuídos em cinco grupos editoriais;
- 1 catálogo em `artigos.html` com acesso a todos os guias;
- 5 páginas principais e institucionais;
- 36 páginas HTML no total;
- 26 imagens WebP, incluindo 19 capas novas criadas para esta expansão;
- sitemap com as 36 URLs canônicas.

## Distribuição dos 30 artigos

| Grupo | Artigos |
|---|---:|
| Decoração e ambientes pequenos | 8 |
| Organização | 5 |
| Limpeza e conservação | 6 |
| Plantas e jardim | 4 |
| Eletros e casa inteligente | 7 |
| **Total** | **30** |

## Verificação do endereço público

O endereço informado, `http://pmorollo.shop/`, redirecionou para `https://pmorollo.shop/`, mas a página retornou **502 Bad Gateway** com a mensagem **Certificate verify failed: hostname mismatch**.

Isso indica incompatibilidade entre o certificado apresentado e o domínio solicitado. Enquanto o HTTPS não estiver correto, o site pode ficar indisponível para visitantes e rastreadores.

O responsável informou que o domínio já foi adicionado ao Google Search Console. Essa propriedade privada não foi acessada nesta etapa. Pesquisas públicas pelo domínio não mostraram páginas indexadas no momento da verificação, o que é compatível com o erro de acesso atual, mas não prova o estado interno da propriedade no Search Console.

## Validações concluídas na cópia de trabalho

- 36 páginas HTML encontradas, sendo 30 artigos.
- Exatamente um H1 em cada página.
- 36 títulos únicos.
- 36 descrições únicas.
- 36 URLs canônicas únicas.
- 36 URLs únicas no sitemap.
- Nenhum link ou recurso local apontando para arquivo inexistente.
- Todas as imagens WebP válidas, com 1376 × 768 pixels e sem arquivos vazios.
- Todos os artigos com pelo menos 500 palavras brutas na contagem do HTML convertido em texto.
- `git diff --check` sem erros.

O navegador em nuvem não pode acessar o servidor local da cópia de trabalho por política de isolamento. Por isso, a verificação visual pós-alterações deverá ser repetida no endereço público assim que o certificado e o deploy estiverem concluídos.

## O que ainda não foi feito

- Nenhum push para o repositório remoto.
- Nenhum deploy das alterações atuais.
- Nenhuma correção de DNS ou certificado, pois isso depende da configuração do provedor de hospedagem/domínio.
- Nenhum envio do sitemap atualizado no Search Console.
- Nenhum pedido manual de indexação das páginas novas.

## Próxima ação necessária

1. Corrigir a associação do domínio e o certificado HTTPS na hospedagem.
2. Obter autorização explícita do responsável para enviar as alterações ao repositório remoto.
3. Publicar a cópia validada.
4. Conferir home, catálogo e artigos em computador e celular no endereço público.
5. Enviar `https://pmorollo.shop/sitemap.xml` no Search Console já configurado.
6. Monitorar cobertura, impressões, cliques, CTR e posição.

## Cadência depois da publicação

A meta operacional permanece em dois artigos novos por semana. Mantido esse ritmo, o planejamento prevê 38 artigos no dia 28, 46 no dia 56, 54 no dia 84 e 60 no dia 105 após a publicação inicial.

Cada ciclo de 30 novos artigos começa com a mesma proporção do conjunto inicial — 8/5/6/4/7 — e pode ser ajustado quando o Search Console fornecer dados suficientes para mostrar quais grupos estão ganhando impressões e posições.

## Arquivos de continuidade

1. `AGENTS.md` — regras editoriais, técnicas e de publicação.
2. `PLANO-TRABALHO.md` — estratégia, pautas, cadência e critérios de medição.
3. `STATUS-PROJETO.md` — situação atual e bloqueios.
4. `CHECKLIST-F3.md` — passos para corrigir HTTPS e publicar com segurança.

Nenhum push, deploy ou monetização foi realizado nesta etapa.

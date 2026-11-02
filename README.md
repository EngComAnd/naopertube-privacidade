# Página da política de privacidade do Não Pertube

Site estático (HTML e CSS embutido, **sem script, sem cookie, sem recurso externo**) com a política em **português, inglês e espanhol** e um seletor de idioma por links. Mesmo desenho do site do SorteAí ([EngComAnd/sorteai-privacidade](https://github.com/EngComAnd/sorteai-privacidade)): esta pasta é a **cópia de partida**; o texto publicado vive no repositório público `EngComAnd/naopertube-privacidade`, e depois da criação dele a pasta sai daqui para não haver duas fontes.

```text
index.html                    # escolha do idioma
privacidade/{pt,en,es}/       # a política (endereço final: <site>/privacidade/<idioma>/)
404.html  .nojekyll
fonte/{pt,en,es}.html         # o texto de cada idioma (edite aqui)
versao.json                   # versão e vigência exibidas
scripts/gerar-pagina.py       # fonte -> páginas
scripts/verificar-pagina.py   # verificação (local, --publicar, --url)
```

## Editar e verificar

```bash
python3 scripts/gerar-pagina.py      # regenera as páginas
python3 scripts/verificar-pagina.py  # estrutura, idiomas, sem script, links, tamanho e contraste AA
python3 scripts/verificar-pagina.py --publicar   # falha se algum campo pendente restar
```

Não edite `privacidade/*/index.html` à mão: são gerados.

## Decisões herdadas do SorteAí (2026-11-02, do responsável pelo produto)

Controlador: o responsável como **pessoa física** (nome, cidade/UF e e-mail), sem CPF nem endereço completo; base legal dos anúncios = a do AdMob (consentimento onde a lei exige; nas demais regiões o Google é controlador independente); transferência internacional = garantias descritas na política do Google; foro = domicílio do consumidor; público = 13 anos ou mais; **versão 1**.

## O que o texto afirma sobre o app (conferir a cada lançamento)

Triagem local sem internet; histórico de 0 a 365 dias (padrão 3); grupos e horários; consulta (sem cópia) à agenda; contagem de "quem insiste" só em memória; um único banner em Configurações, sempre não personalizado, com consentimento onde exigido; apoio e "Remover anúncios" pela Google Play; backup desligado; captura de tela bloqueada. Mudou o que o app faz com dados? Atualize `fonte/*.html` **no mesmo lançamento** e a Data safety da Play.

## Antes de publicar

1. Revisão jurídica do texto; o inglês e o espanhol são tradução feita pelo agente e **precisam de revisão** por falante nativo.
2. Criar o repositório público `EngComAnd/naopertube-privacidade` com este conteúdo, `main` protegida e **Pages: Source = GitHub Actions**; rodar o fluxo `Publicar página` (manual).
3. `python3 scripts/verificar-pagina.py --publicar --url https://engcomand.github.io/naopertube-privacidade/privacidade` (status 200, https, HTML, sem cookie).
4. Usar `https://engcomand.github.io/naopertube-privacidade/privacidade/pt/` na Play Console e no AdMob (Privacidade e mensagens).

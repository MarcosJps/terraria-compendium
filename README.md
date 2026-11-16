# Terraria Compendium — v0.6.0-beta

**Guia visual independente de Terraria Vanilla, PT-BR.** Pergunta principal: *vou enfrentar o chefe X com a classe Y; o que equipar, onde consigo e como me preparo?*

O site é um **catálogo de consulta**, sem contas, mundo salvo, criador de builds, backend, banco ou checklist de mundo.

## Como abrir a versão pronta

Abra `Terraria-Compendium-Preview.html` no navegador, ou use um servidor local para o projeto modular:

```bash
npm run dev
# visite http://localhost:4173
```

Não exige `npm install` nem bibliotecas JavaScript em runtime. Há arquivos ES modules (`src/`) para manutenção e prévia HTML única para abrir sem instalação. Sprites são **remotos**, não estão incluídos no ZIP, e podem falhar em caso de conexão bloqueada/hotlink. Nesse caso, a interface usa fallback.

## Como desenvolver

```bash
npm run data:generate     # edita scripts/generate-boss-guide.py -> regenera src/data/boss-guide.js
npm test                  # 13 testes de conteúdo e reprodução
npm run build:preview     # produz Terraria-Compendium-Preview.html
npm run test:browser      # opcional: Python Playwright + Chromium instalados no computador
```

O teste de navegador usa imagens simuladas, não confirma sprites originais nem disponibilidade HTTP. Execute este teste em sistema com Python/Playwright configurado; o site em si não depende disso.

## O que tem nesta versão

- 18 chefes individuais e 72 visões chefe/classe (17 grupos básicos reaproveitados entre mecânicos).
- 286 fichas de referência, 246 com orientação preliminar e 4 verificadas individualmente contra fontes disponíveis; 4 receitas detalhadas com fonte, data e versão.
- 242 nomes permanecem em inglês, marcados **tradução pendente**.
- Guia das quatro classes, pesquisa por português/inglês com e sem acento, filtros de fase e Corrupção/Carmesim, ficha interna de obtenção e guia de preparação.
- Estratégias breves de chefe e notas distintas para Destruidor, Gêmeos e Esqueletron Alfa.
- Três encontros do Exército do Velho (Dark Mage, Ogre, Betsy) como índice de referência; sem loadout inventado.
- Foco mobile: lista de chefes recolhível, navegação direto ao painel, sprites limitados ao card e modal dentro da tela.
- Link por hash, como `#chefe=eye&classe=mage`, preferências locais com try/catch e botão copiar link.

## Limites importantes

Este projeto **ainda não é uma wiki completa**. Falta validar 282 fichas individualmente, diversos equipamentos cronologicamente e os sprites verdadeiros. Scripts e dados preservam estado pendente em vez de inventar. Não é seguro afirmar que toda combinação vale para a primeira tentativa em todas as dificuldades.

O ambiente de desenvolvimento conseguiu rodar o Chromium em memória, com imagens simuladas, mas bloqueou `file://` e `http://localhost` pelo administrador. Por isso, screenshots e smoke não comprovam o comportamento de rede real. Leia `docs/VALIDACAO.md` e `docs/PENDENCIAS.md` para detalhes.

## Fontes e uso de mídia

- Guia de classes atual: https://terraria.wiki.gg/wiki/Guide:Class_setups
- Wiki atual: https://terraria.wiki.gg/
- Versões: https://terraria.wiki.gg/wiki/Versions (referência 1.4.5.8 Desktop)
- Licenciamento: https://terraria.wiki.gg/wiki/Terraria_Wiki:Copyrights

A wiki *Legacy* não é utilizada. Os sprites pertencem à Re-Logic; o ZIP não os redistribui. Antes da publicação pública, audite cada uso e a política de hotlink/licenciamento.

**Importante:** o código legado com Supabase/contas da v0.4 não está incluído neste ZIP, para respeitar o escopo sem login ou banco. O ZIP original da v0.5 permanece separado como backup.

## Organização

```text
index.html
src/app.js                  # navegação/renderização vanilla JS
src/styles.css              # visual/responsividade/teclado
src/data/boss-guide.js      # GENERATED; não editar
src/data/events.js          # eventos
scripts/generate-boss-guide.py
scripts/build-standalone.py
scripts/serve.mjs
tests/*.test.js
tests/browser-smoke.py
docs/VALIDACAO.md
docs/AUDITORIA_PROGRESSAO.md
docs/TRADUCOES_PENDENTES.csv
docs/PENDENCIAS.md
CHANGELOG.md
CLAUDE.md
Terraria-Compendium-Preview.html
```

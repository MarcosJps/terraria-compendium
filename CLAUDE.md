# Terraria Compendium — orientações de engenharia v0.6

## Objetivo e escopo irrevogáveis

Site visual PT-BR orientado a consultas por **chefe + classe**, com obtenção e preparação, em até três toques quando possível. **Sem login, contas, mundos, banco, backend, checklists persistentes ou criador de builds.** Preferências de classe/fase/bioma podem usar localStorage com try/catch, e rota compartilhável por hash.

Frontend 100% vanilla HTML, CSS, JS ES modules e zero dependências JS em runtime. `npm test` usa o runner interno do Node. Smoke opcional usa Playwright Python instalado no ambiente de QA, não no site.

## Regra absoluta de geração

- Para dados de equipamento, EDITE SOMENTE `scripts/generate-boss-guide.py` e execute `npm run data:generate`. NUNCA altere `src/data/boss-guide.js` diretamente.
- A prévia é produzida por `scripts/build-standalone.py`; execute `npm run build:preview` após qualquer edição.
- Teste `npm test` sempre; quando houver browser disponível, execute `npm run test:browser`. Não confunda screenshots com imagens simuladas e verificação de rede real.

## Fontes e anti-invenção

- Priorize https://terraria.wiki.gg/wiki/Guide:Class_setups (moderno), nunca Legacy.
- Só marque `review:'verificado'` quando a fonte específica foi consultada; registre `verifiedAt` em ISO `YYYY-MM-DD`, `gameVersion` e `source`.
- Tradução só em `pt` quando revisada. Se ausente, exibir inglês com indicação e manter CSV de pendência.
- Receitas, ingredientes, condições de vendedor, preços, chances, valores numéricos só quando fontes conferidas.
- Não reproduza prosa da wiki. Reescreva concisamente em português simples.
- Exija que a progressão pré-chefe não inclua recompensas do próprio chefe nem de etapas futuras; alterações devem constar em `docs/AUDITORIA_PROGRESSAO.md`.
- Imagens sempre remotas, sem inclusão de sprites Re-Logic no ZIP. Confirme direitos/hotlink antes de publicar.

## Interface, segurança e acessibilidade

- CSS `image-rendering:pixelated`; limite imagem ao tamanho do card e do modal, inclusive em 390px.
- Roteamento por `#chefe=...&classe=...`, sem crash com hash malformado; escapar todos os dados interpolados em HTML.
- Não use manipuladores de eventos inline. CSP hash na prévia, `'self'` em módulos. Sem `eval`.
- Modal: fecha com Esc, prende/restaura o foco; controles com aria-label, foco visível, status aria-live de contagem, navegação com Tab/Enter e `/` para pesquisa.
- Prefers reduced motion; falha de imagem não pode quebrar layout. A experiência sem internet deve permanecer navegável para dados embutidos.

## Testes e documentação

- Não declare 'todos os itens validados' com apenas 4 registros verificados.
- Ao adicionar um chefe, garanta 4 classes ou marque-o como encontro opcional sem loadout (por ex., Old One’s Army).
- Mantenha `README.md`, `docs/VALIDACAO.md`, `docs/PENDENCIAS.md`, `docs/AUDITORIA_PROGRESSAO.md`, `docs/TRADUCOES_PENDENTES.csv` e `CHANGELOG.md` atualizados.

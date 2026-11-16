# Changelog — Terraria Compendium

## 0.6.0-beta — 2026-11-15

### Fase 0 — baseline
- Extraídos dados da v0.5 original e geradas capturas 1366px/390px em páginas: início, lista, chefe e ficha.
- Sete testes e build da v0.5 executados, com bloqueio explícito da navegação local do Chromium.

### Fase 1 — texto
- Corrigida a ficha Gold Bow, removida menção indevida a Demon Bow.
- Explicação de ouro/platina simplificada.
- Quarenta fichas sem obtenção ganharam contexto por categoria, mantendo marcação pendente.
- Removida a frase contraditória sobre montar combinação dentro de “seu mundo”.

### Fase 2 — progressão
- Corrigidas alternativas cronologicamente incompatíveis em Deerclops, Queen Bee, Skeletron, bioma maligno, Plantera, Empress e Moon Lord.
- Auditados automaticamente os 72 cenários quanto a bloqueios *cadastrados*, sem declarar auditoria editorial integral.
- Criado `docs/AUDITORIA_PROGRESSAO.md`, com matriz e pendências explícitas.

### Fase 3 — conteúdo
- Fichas diferenciam **verificado**, **dica inicial** e **pendente**. Quatro receitas foram verificadas em fontes específicas e registram data/versão.
- Estra­tégias iniciais por encontro, com notas diferentes para os três mecânicos.
- Exército do Velho: Dark Mage, Ogre e Betsy documentados como encontros opcionais por nível do evento, sem loadouts inventados.
- CSV com 242 traduções pendentes; fonte de eventos padronizada para domínio oficial.

### Fase 4 — experiência
- Filtro “Corrupção/Carmesim”, preferências locais com proteção contra storage bloqueado, links diretos por hash, copiar link e lista mobile recolhível.
- Seleção de chefe rola até painel, especialmente em telas pequenas.

### Fase 5 — acessibilidade e robustez
- Restrições estritas de dimensões para sprites, cards e modal; CSS pixelated preservado.
- Foco do modal preso/restaurado, Esc, atalho `/` para busca, aria-live com contagem resumida, foco visível e reduced motion.
- Falhas de sprite registradas globalmente; CSP da prévia usa hash do JavaScript gerado.

### Fase 6 — testes
- 13 testes Node, incluindo fontes, cronologia e reprodução da prévia.
- Smoke Chromium opcional: busca, chefes, classe, filtro, ficha, teclado, hash, fallback offline, 1366px e 390px.

### Fase 7 — QA
- Screenshots antes e depois salvas em `docs/`.
- Todas as restrições de rede/navegação e os riscos editoriais pendentes documentados em `docs/PENDENCIAS.md`.

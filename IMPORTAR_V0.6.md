# Publicação da v0.6 na branch develop

O projeto Terraria Compendium v0.6 está empacotado no arquivo **Terraria-Compendium-v0.6.zip** da conversa no ChatGPT. O ZIP contém o código modular, a prévia HTML, os scripts, os testes, imagens próprias e documentação.

## Envio pelo navegador

1. Baixe o ZIP da conversa e **extraia** o conteúdo no computador.
2. No GitHub, selecione a branch **develop**.
3. Clique em **Add file > Upload files** (Adicionar arquivo > Carregar arquivos).
4. Abra a pasta extraída `Terraria-Compendium` e arraste **o conteúdo dessa pasta**, incluindo pastas `src`, `scripts`, `docs`, `tests` e `assets`, para a área de upload. Não envie o ZIP como único arquivo: o GitHub precisa dos arquivos descompactados.
5. Confira que `index.html`, `package.json`, `README.md`, `CLAUDE.md` e `Terraria-Compendium-Preview.html` aparecem na raiz do repositório.
6. Confirme a alteração em **develop** com a mensagem `feat: importar Terraria Compendium v0.6-beta`.

Depois, para publicar uma versão estável, abra um Pull Request de `develop` para `main`, revise e faça merge.

## Rodar localmente

```bash
npm test
npm run build:preview
npm run dev
```

O site usa HTML, CSS e JS puro, sem dependências de frontend em runtime e sem login/banco. Sprites do Terraria ficam remotos.

**Observação:** o conteúdo v0.6 não está incluído neste arquivo; ele precisa ser importado a partir do ZIP original.

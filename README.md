# Realidade Aumentada — Escola Municipal Dr. Raymundo Nonato de Magalhães Cordeiro

Projeto de realidade aumentada com MindAR + A-Frame.

## Publicar no GitHub Pages

1. Crie um repositório público, por exemplo `RA-Esc-Magalhaes-Cordeiro`.
2. Envie para a raiz do repositório: `index.html`, `01-gerar-target.html`, `.nojekyll` e a pasta `assets`.
3. Ative GitHub Pages em **Settings → Pages → Deploy from a branch → main → /(root) → Save**.
4. Abra a URL HTTPS do GitHub Pages.

## Gerar o targets.mind

Abra a página publicada:

`https://SEU-USUARIO.github.io/RA-Esc-Magalhaes-Cordeiro/01-gerar-target.html`

Clique em **COMPILAR E BAIXAR**. O navegador baixará `targets.mind`.

Depois, no GitHub, faça upload de `targets.mind` para a **raiz do repositório**, ao lado de `index.html`.

Recarregue a página principal e permita o uso da câmera.

## Estrutura final

```text
index.html
01-gerar-target.html
targets.mind
.nojekyll
assets/
  imagem-alvo.png
  logo.png
```

## Resultado

Ao apontar a câmera para `imagem-alvo.png`, o logo da escola aparece sobre o marcador, em pé, girando continuamente no eixo X.


## Versão corrigida para celular
Esta versão força o vídeo da câmera, o canvas e a cena do MindAR a ocupar toda a viewport do celular, evitando que a câmera apareça apenas em uma faixa lateral.

# Brasão em realidade aumentada

Página web que reconhece o brasão impresso da Escola Municipal Dr. Raymundo Nonato de Magalhães Cordeiro e faz o selo levantar devagar do papel, ficar em pé sobre a folha e girar.

Feita com A-Frame + AR.js (carregados por CDN). Não precisa de servidor, build nem instalação.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | A página. É o que abre no navegador. |
| `marcador.patt` | O padrão que o AR.js procura na imagem da câmera. |
| `marcador.png` | O marcador para imprimir (brasão dentro da moldura preta). |
| `marcador-a4.pdf` | O mesmo marcador já diagramado em A4, com 15 cm de lado. |
| `logo-3d.png` | O brasão recortado, sem fundo, usado no 3D. |

Mantenha todos os arquivos na mesma pasta: a página procura por eles pelo nome.

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub (público).
2. Envie os arquivos desta pasta para a raiz do repositório (botão **Add file → Upload files**).
3. Vá em **Settings → Pages**.
4. Em *Source*, escolha **Deploy from a branch**; em *Branch*, escolha `main` e a pasta `/ (root)`. Salve.
5. Em um ou dois minutos o endereço aparece na mesma tela, no formato
   `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

O endereço do GitHub Pages é https, que é o que o navegador exige para liberar a câmera.

## Como usar

1. Imprima o `marcador-a4.pdf` em folha A4, sem "ajustar à página".
2. Abra o endereço do GitHub Pages no celular ou no computador.
3. Toque em **Ligar a câmera** e permita o acesso.
4. Aponte para o marcador impresso, com a folha inteira dentro do quadro.

A moldura preta faz parte do marcador: é ela que o AR.js usa para calcular a posição. Não corte, não dobre e evite reflexo de luz direta sobre a folha.

## Ajustes comuns

Tudo fica no `index.html`, dentro da tag `<template id="cena">`.

- **Velocidade da subida**: `dur: 3000` nas animações `animation__sobe` e `animation__pe` (milissegundos). Se mudar esse valor, mude também o `setTimeout(..., 3000)` no script, que é o que dispara o giro no momento certo.
- **Velocidade do giro**: `dur: 9000` em `animation__rodopio`. Quanto maior, mais lento.
- **Altura final**: o `0 0.78 0` em `animation__sobe`. A unidade 1 equivale ao lado do marcador.
- **Tamanho do brasão**: `width` e `height` da tag `<a-image>`.
- **Trocar a imagem**: substitua `logo-3d.png` por outro PNG com fundo transparente, de preferência quadrado.

## Se quiser gerar um marcador novo

Para outro desenho, crie a moldura na mesma proporção (borda preta ocupando 25% de cada lado, desenho no quadrado central) e gere o `.patt` em https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html com *Pattern Ratio* 0.50.

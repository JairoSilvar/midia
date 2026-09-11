# Portal de Mídia v5.1

## Arquivos
- `index.html` — app completo
- `manifest.webmanifest` — PWA
- `sw.js` — service worker (só cache da interface)
- `playlist.example.json` — modelo de playlist (renomeie para `playlist.json` se for usar)
- `vercel.json` — headers e SPA no Vercel

## Deploy
1. Suba estes arquivos na raiz do repositório (substitua o `index.html` antigo).
2. Commit + push → Vercel publica sozinho.

## playlist.json (opcional)
Copie `playlist.example.json` → `playlist.json` e coloque URLs HTTPS das suas faixas.

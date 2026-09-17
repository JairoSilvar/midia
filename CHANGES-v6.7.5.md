# Painel Mídia v6.7.5 — Legacy Compatibility

Atualização cirúrgica sobre a v6.7.4, focada no iPad 3 / iOS 9.3.5 Safari, sem alterar CSS, layout ou RADIO_CHANNELS.

## Alterações
- Adicionada camada de parsing de URL baseada em elemento `<a>`, evitando dependência do construtor moderno `new URL()` e de `URLSearchParams` nos fluxos de rádios salvas, YouTube e biblioteca.
- Adicionado helper de remoção DOM compatível com navegadores antigos.
- Navegação “Início” alterada para `scrollIntoView(true)` com fallback para `window.scrollTo(0,0)`, sem options object.
- Mantidos/expandidos polyfills ES5, incluindo `findIndex`, `Object.assign`, `Array.from`, `Number.isFinite`, `NodeList.forEach`, `HTMLCollection.forEach` e `Element.remove`.
- Mantida a arquitetura de mídia estabilizada da v6.7.4, incluindo exclusividade Rádio ↔ YouTube ↔ Biblioteca e proteção por token.
- Cache do Service Worker atualizado para `painel-midia-v675-ui`.

## Preservação
- Nenhuma alteração em `RADIO_CHANNELS`.
- Total Hits preservada.
- Continental preservada.
- Favoritos, histórico, biblioteca, timer, temas e demais recursos preservados.
- Nenhuma mudança visual intencional.

## Validação estática
- JavaScript inline verificado com `node --check`.
- Ausência de `new URL(`, `searchParams`, `scrollIntoView({`, `radioAudioPool`, `__portalInvalid` e `:has(` no HTML final.

## Teste físico necessário
A validação definitiva de iOS 9 exige o iPad 3 real. Testar carregamento inicial e, depois: Rádio A → Rádio B → YouTube → Biblioteca → Total Hits → Stop → Continental → Stop → Total Hits.

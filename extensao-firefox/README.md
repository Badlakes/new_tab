# Extensão Firefox — Minha Nova Aba

Esta extensão substitui a nova aba diretamente no Firefox e mostra a página publicada em:

`https://badlakes.github.io/new_tab/`

Por carregar essa página dentro da extensão, as atualizações enviadas ao GitHub Pages aparecem automaticamente. O GIF é carregado pela própria extensão para evitar problemas de fundo dentro do quadro incorporado. Para trocar o endereço no futuro, edite apenas `src` e a URL do GIF em `new-tab.html`.

## Testar no Firefox

1. Digite `about:debugging#/runtime/this-firefox` na barra de endereço.
2. Clique em **Load Temporary Add-on…**.
3. Selecione o arquivo `manifest.json` desta pasta.
4. Abra uma nova aba com `Ctrl+T`.

O teste temporário é removido ao fechar o Firefox. Para instalar a extensão de forma permanente no Firefox normal, é necessário gerar um pacote `.xpi` assinado pelo Mozilla Add-ons; não é preciso publicar a extensão para todo mundo, ela pode ser assinada como **unlisted**.

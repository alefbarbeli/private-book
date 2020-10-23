---
title: Como abrir o Vue-Devtools em produção
date: 2020-10-23 15:29:05
tags:
---

É possível abrir o Vue-Devtools em produção ajudando a descobrir o porque do BUG rolar em produção e não em desenvolvimento. Porem algumas funcionalidades do devtools não vão estar disponíveis como o tracking do Vuex.

1. Abra o Chrome Inspector, na aba de Sources (Código Fonte), procure na pasta **js** pelos arquivos com o nome **pkg.app~*.*.js**
2. Dentro destes arquivos abra eles e clique no botão de Beautifier(Pretty Print) do Chrome, canto inferior esquedo da área de código - Botão {}
![](https://i.imgur.com/kkQHkD3.png)

3. Busque por $mount dentro dos arquivos, adicione um breakpoint na linha que inicia a montagem do Vue.
![](https://i.imgur.com/6Onu56y.png)

4. Aperte ESC para abrir o console na parte inferior do Chrome Inspector, e recarregue a página.

5. Quando a página regarregar, espere o breakpoint ativar, e no console digite `t["default"].config.devtools = true`, de continue no breakpoint.
![](https://i.imgur.com/lIYczus.png)

6. Feche e abra novamente o Chrome Inspector, e o Vue-Devtools estará ativado.
![](https://i.imgur.com/p6I4JyY.png)
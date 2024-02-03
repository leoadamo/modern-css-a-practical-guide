---
title: Scoped CSS
layout: section
transition: slide-up
---

<!-- Scoped CSS -->
<section>
  <h1 class="section-title">
    Scoped CSS
  </h1>
</section>

---
hideInToc: true
---

# Scoped CSS

- Assim como os _layers_, também auxilia em um melhor controle da cascata e na forma como queremos que os estilos sejam aplicados;
- Comportamento semelhante com o que já é implementado por alguns frameworks como _Vue_, _React_ e _Svelte_, por exemplo;
- Garante que os estilos definidos em um bloco (escopo) não "vazem", gerando efeitos colaterais indesejados ao longo do _codebase_;
- Favorece a definição de seletores CSS de complexidade menor e menos dependentes da estrutura do DOM.

---
hideInToc: true
---

# Scoped CSS

- Para limitar o alcance dos nossos seletores CSS por meio da definição de um escopo, fazemos uso da palavra-chave `@scope`:

```css
@scope (.card) {
  img {
      border-color: green;
  }
}
```

<br>

- Aceita um parâmetro adicional opcional (_scoping limit_) que determina o limite do escopo:

```css
@scope (.card) to (.card__content) {
  img {
      border-color: green;
  }
}
```

---
hideInToc: true
---

# Scoped CSS

- Possibilita definir estilos para o elemento _root_ do escopo, propriamente dito, por meio do seletor `:scope`;
- Por padrão, todos os estilos definidos para os elementos de um escopo herdam esse seletor por debaixo dos panos;
- É possível atingir os mesmos resultados utilizando o `&` ao invés do seletor `:scope`, no entanto suas especificidades são diferentes:

```css
@scope (#sidebar) {
  img { /* Seleciona todas as imagens filhas de #sidebar. Especifidade (0, 0, 1) */ }

  :scope img { /* Também seleciona todas as imagens filhas de #sidebar. Especifidade (0, 1, 1) */ }

  & img { /* Também seleciona todas as imagens filhas de #sidebar. Especifidade (1, 0, 1) */ }
}
```

<!-- Docs -->
<AppReferences class="mt-[48px]">
  <AppLink url="https://developer.chrome.com/docs/css-ui/at-scope" title="Limit the reach of your selectors with the CSS @scope at-rule" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/zYbRWLB" title="Demo" class="text-4xl" />

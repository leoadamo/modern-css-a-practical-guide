---
title: Selectors
layout: section
transition: slide-up
---

<!-- Selectors -->
<section>
  <h1 class="section-title">
    Selectors
  </h1>
</section>

---
hideInToc: true
layout: section
---

# :has()

---
hideInToc: true
---

# :has()

- Permite que os estilos sejam aplicados ao checar se um elemento contém filhos ou ancestrais específicos;
- Também possibilita que a busca seja feita com base no estado dos elementos. Por exemplo:

```css
/* Seleciona todos os elementos "h1" que possuírem um elemento "p" como filho, não importando o nível */
h1:has(p) {}

/* Seleciona todos os elementos "h1" que possuírem um elemento "p" como filho direto */
h1:has(> p) {}

/* Seleciona todos os elementos "h1" forem seguidos imediatamente por um elemento do tipo "p" */
h1:has(+ p) {}

/* Seleciona o elemento "li" que for antecessor a outro "li" com o estado de hover */
li:has(+ li:hover)
```

<!-- Docs -->
<AppReferences class="mt-[52px]">
  <AppLink url="https://www.smashingmagazine.com/2023/01/level-up-css-skills-has-selector/" title="Level Up Your CSS Skills With The :has() Selector" />
</AppReferences>

---
hideInToc: true
layout: section
---

# :is()

---
hideInToc: true
layout: section
---

# :where()

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/gOqBqVR?editors=1100" title="Demo" class="text-4xl" />
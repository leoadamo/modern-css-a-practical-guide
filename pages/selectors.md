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

# :is()

---
hideInToc: true
---

# :is()

- Possibilita o agrupamento de múltiplos seletores, aplicando os mesmos estilos para cada um deles;
- Evita a declaração manual de cada combinação de seletores que receberão os estilos em questão. Por exemplo:

```css
/* Declaração manual */
section h1, section h2, section h3, section h4, section h5, section h6, 
article h1, article h2, article h3, article h4, article h5, article h6, 
aside h1, aside h2, aside h3, aside h4, aside h5, aside h6, 
nav h1, nav h2, nav h3, nav h4, nav h5, nav h6 {
  color: #BADA55;
}

/* Utilizando :is() */
:is(section, article, aside, nav) :is(h1, h2, h3, h4, h5, h6) {
  color: #BADA55;
}
```

<!-- Docs -->
<AppReferences class="mt-[32px]">
  <AppLink url="https://grrr.tech/posts/2023/using-new-pseudo-class-selectors-in-2023/#is" title="Using new pseudo-class selectors in 2023" />
</AppReferences>

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

# :where()

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/gOqBqVR?editors=1100" title="Demo" class="text-4xl" />
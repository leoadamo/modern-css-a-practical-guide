---
title: Container queries
layout: section
transition: slide-up
---

<!-- Container queries -->
<section>
  <h1 class="section-title">
    Container queries
  </h1>
</section>

---
hideInToc: true
layout: image-right
image: https://web.dev/static/blog/cq-stable/image/media-queries-vs-containe-fa94919e025e3_856.png
---

# Container queries

- São similares às `@media` _queries_, porém estão relacionadas ao tamanho do elemento ancestral definido como container, ao invés da _viewport_;
- Favorecem a flexibilidade, uma vez que os componentes podem ser customizados de acordo com o contexto onde estão sendo utilizados;
- Auxiliam no desenvolvimento de componentes isolados.

---
hideInToc: true
---

# Container queries

- Para utilizar, é necessário definir o elemento que atuará como um _container_:

```css
.card-container {
  container: card / inline-size;
}
```
<br>

- Em seguida, podemos customizar os filhos desse container, com base nas dimensões reais do pai:

```css
.card {
  display: grid;
  grid-template-columns: 1fr;
}

@container card (min-width: 800px) {
 .card {
   grid-template-columns: repeat(2, 1fr);
 }
}
```

<!-- Docs -->
<AppReferences class="mt-[16px]">
  <AppLink url="https://developer.mozilla.org/en-US/blog/getting-started-with-css-container-queries/" title="Getting started with CSS container queries" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/xxBJMap?editors=1100" title="Demo" class="text-4xl" />
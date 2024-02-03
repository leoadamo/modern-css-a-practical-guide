---
title: CSS subgrid
layout: section
transition: slide-up
---

<!-- CSS subgrid -->
<section>
  <h1 class="section-title">
    CSS subgrid
  </h1>
</section>

---
hideInToc: true
---

# CSS Subgrid

- Surgiu com o propósito de possibilitar o desenvolvimento de _layouts_ mais complexos;
- Resolve algumas limitações que o _flexbox_ e o _CSS Grid_ por si só possuem;
- Permite a criação de sistemas de grid aninhados;
- Declarando a propriedade `grid-template-columns/grid-template-rows: subgrid` em um elemento, podemos fazer com que o mesmo **herde** as definições de grid do elemento pai.

<div class="grid grid-cols-2 gap-4 m-t-4">
  
  ```html
  <div class="main-grid-container">
    <div class="grid-item">
      <div class="subgrid-item">
        <!-- ... -->
      </div>
      <div class="subgrid-item">
        <!-- ... -->
      </div>
    </div>
  </div>
  ```

  ```css
  .main-grid-container { 
    display: grid; 
  }

  .grid-item {
    display: grid;
    grid-template-columns: subgrid;
    grid-template-rows: subgrid;
  }
  ```
</div>

<!-- Docs -->
<AppReferences class="mt-[16px]">
  <AppLink url="https://ishadeed.com/article/learn-css-subgrid/" title="Learn CSS Subgrid" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/abMGKKR?editors=1100" title="Demo" class="text-4xl" />


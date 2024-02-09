---
title: Pseudo-class selectors
layout: section
transition: slide-up
---

<!-- Pseudo-class selectors -->
<section>
  <h1 class="section-title">
    Pseudo-class selectors
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
  <AppLink url="https://grrr.tech/posts/2023/using-new-pseudo-class-selectors-in-2023/#is" title="Using new pseudo-class selectors in 2023 - :is()" />
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

- Permite que os estilos sejam aplicados a um elemento com base na existência de filhos ou irmãos específicos;
- Também possibilita que a busca seja feita com base no estado dos elementos. Por exemplo:

```css
/* Seleciona todos os elementos "article" que possuírem um elemento "h2" como filho, não importando o nível */
article:has(h2) {}

/* Seleciona todos os elementos "article" que possuírem um elemento "h2" como filho direto */
article:has(> h2) {}

/* Seleciona todos os elementos "article" forem seguidos imediatamente por um elemento do tipo "h2" */
article:has(+ h2) {}

/* Seleciona o elemento "li" que for antecessor a outro "li" com o estado de hover */
li:has(+ li:hover)
```

<!-- Docs -->
<AppReferences class="mt-[42px]">
  <AppLink url="https://www.smashingmagazine.com/2023/01/level-up-css-skills-has-selector/" title="Level Up Your CSS Skills With The :has() Selector" />
</AppReferences>

---
hideInToc: true
layout: section
---

# :where()

---
hideInToc: true
---

# :where()

- Possui um comportamento extremamente parecido com o seletor `:is()`, tendo como principal diferença a sua especificidade;
- Enquanto o seletor `:where()` possui especificidade _0_, o seletor `:is()` leva em consideração a especificidade do <span class="underline">seletor mais específico</span> dentre a lista de argumentos.

```css
/* Declaração manual */
article h1,
article h2,
article h3,
article h4 {
  font-size: 30px;
}

/* Utilizando :where() */
article:where(h1, h2, h3, h4) {
  font-size: 30px;
}
```

<!-- Docs -->
<AppReferences class="mt-[18px]">
  <AppLink url="https://grrr.tech/posts/2023/using-new-pseudo-class-selectors-in-2023/#where" title="Using new pseudo-class selectors in 2023 - :where()" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/xxBapRv" title="Demo" class="text-4xl" />

---
hideInToc: true
layout: section
---

# :user-valid / :user-invalid

---
hideInToc: true
---

# :user-valid / :user-invalid

- Ambas vieram para aprimorar as até então já existentes `:valid` e `:invalid` pseudo-classes;
- Diferenciam-se das suas predecessoras uma vez que os estilos só serão aplicados ao elemento **após** a interação do usuário.

```css
/* Sintaxe */
input:user-valid,
select:user-valid,
textarea:user-valid {
  border-color: green;
}

input:user-invalid,
select:user-invalid,
textarea:user-invalid {
  border-color: red;
}
```

<!-- Docs -->
<AppReferences class="mt-[32px]">
  <AppLink url="https://web.dev/articles/user-valid-and-user-invalid-pseudo-classes" title="The :user-valid and :user-invalid pseudo-classes" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/web-dot-dev/pen/wvNJGrO" title="Demo" class="text-4xl" />

<!-- Os seletores :is() e :where() são classificados como "forgiving selectors", ou seja, caso algum seletor seja inválido dentro da lista de argumentos, ele será ignorado e os demais terão os estilos aplicados
  O seletor :has() é classificado como um "non-forgiving selector", ou seja, caso algum seletor seja inválido dentre a lista de argumentos, todo o bloco de estilo será ignorado pelo navegador -->
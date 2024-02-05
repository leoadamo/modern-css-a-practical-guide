---
title: Individual transform properties
layout: section
transition: slide-up
---

<!-- Individual transform properties -->
<section>
  <h1 class="section-title">
    Individual transform properties
  </h1>
</section>

---
hideInToc: true
---

# Individual transform properties

- Proporcionam uma maior flexibilidade no código;
- Evitam repetições, uma vez que cada propriedade pode ser modificada individualmente;
- Possibilitam uma melhor ergonomia e _DX_;
- Tornam o uso de animações (`@keyframes`) mais simples e intuitivo;
- Suportadas pela grande maioria dos _browsers_ da atualidade.

Utilizando a propriedade `transform` como estamos acostumados:

```css
.my-element {
  transform: translateX(50%) rotate(30deg) scale(1.2);
}

.my-element:hover {
  /* Necessário repetir toda a linha, mesmo que a única mudança seja no scale(2) */
  transform: translateX(50%) rotate(30deg) scale(2); 
}
```

---
hideInToc: true
---

# Individual transform properties

Utilizando _individual transform properties_:

```css
.my-element {
  translate: 50% 0;
  rotate: 30deg;
  scale: 1.2;
}

.my-element:hover {
  /* Não é necessária a repetição, basta alterar apenas o que precisamos. */
  scale: 2;
}
```
---
hideInToc: true
---

# Individual transform properties

- Diferentemente das regras declaradas com a propriedade `transform` - onde as propriedades são aplicadas de acordo com a ordem declarada - aqui a ordem não importa, ou seja, declarando elas assim:

```css
.my-element {
  scale: 1.2;
  rotate: 30deg;
  translate: 50% 0;
}
```

- Nos dará o mesmo resultado do exemplo anterior, pois, a aplicação das propriedades será sempre igual: `translate` > `rotate` > `scale`.

<!-- Docs -->
<AppReferences class="mt-[64px]">
  <AppLink url="https://web.dev/articles/css-individual-transform-properties" title="Finer grained control over CSS transforms with individual transform properties" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/vYPRJGr" title="Demo" class="text-4xl" />
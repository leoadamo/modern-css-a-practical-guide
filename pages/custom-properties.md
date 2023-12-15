---
title: CSS custom properties
layout: section
transition: slide-up
---

<!-- CSS custom properties -->
<section>
  <h1 class="section-title">
    CSS custom properties
  </h1>

  <small class="text-gray-600">
    <i>(aka variables)</i>
  </small>
</section>

---
hideInToc: true
---

# CSS custom properties

- Não necessitam de um pré-processador CSS;
- Ficam disponíveis no _runtime_ da aplicação, facilitando testes e depuração;
- Podem ser combinadas com pré-processadores CSS, como SASS, Stylus e PostCSS, por exemplo;
- Podem ter os seus valores redefinidos dentro de CSS _media-queries_;
- Aceitam valores parciais, o que facilita a composição de variáveis e a escalabilidade;
- Levam em consideração a estrutura do DOM e podem ser escopadas em elementos específicos ou através de classes mais genéricas (_cascade_);
- Podem ser manipuladas através do javascript;

---
hideInToc: true
---

# CSS custom properties

- Normalmente são definidas dentro do elemento `:root` de uma aplicação, através da sintaxe `--nome-da-variavel`:

```css
:root {
  --default-ff: 'Poppins', sans-serif;
  --primary-color: #bd93f9;
  --secondary-color: #50fa7b;
}
```
<br>

- São acessadas utilizando a função `var()` do CSS, que recebe como parâmetro o nome da variável a ser utilizada:

```css
.my-element {
  font-family: var(--default-ff);
  color: var(--primary-color);
}
```
<!-- Docs -->
<AppReferences class="mt-[20px]">
  <AppLink url="https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties" title="Using CSS custom properties (variables) - MDN" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/gOqBqVR?editors=1100" title="Demo" class="text-4xl" />
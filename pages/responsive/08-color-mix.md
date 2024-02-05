---
title: color-mix()
layout: section
transition: slide-up
---

<!-- color-mix() -->
<section>
  <h1 class="section-title">
    color-mix()
  </h1>
</section>

---
hideInToc: true
---

# color-mix()

- Solução nativa do CSS para viabilizar o que até então só era possível com o uso de pré-processadores: a mistura de cores;
- Suporta diversos formatos de cores (`RGB`, `sRGB`, `HSL`, `LCH`, entre outros);
- O resultado final varia de acordo com o [color space](https://developer.chrome.com/docs/css-ui/high-definition-css-color-guide) escolhido, podendo apresentar resultados bem distintos entre eles;
- Suportado praticamente pela grande maioria dos navegadores mais atuais ([Can I use - color-mix()](https://caniuse.com/?search=color-mix())).

```css {all|2,6|3|4|5|all}
.very-light-blue {
  background-color: color-mix(
    in oklab, /** Color space (srgb, lch, hsl...) */
    blue 10%, /** Color 1 + percentage  */
    white /** Color 2 + percentage (optional) */
  );
}
```

<!-- Docs -->
<AppReferences class="mt-[32px]">
  <AppLink url="https://developer.chrome.com/docs/css-ui/css-color-mix" title="CSS color-mix()" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/zYbaWRb" title="Demo" class="text-4xl" />
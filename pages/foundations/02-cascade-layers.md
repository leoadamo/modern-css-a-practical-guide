---
title: Cascade layers
layout: section
transition: slide-up
---

<!-- Cascade layers -->
<section>
  <h1 class="section-title">
    Cascade layers
  </h1>
</section>

---
hideInToc: true
---

# Cascade layers

- Possibilitam uma melhor gestão e controle sobre a arquitetura CSS e o conhecido "efeito cascata" _(cascade)_;
- Ajudam a evitar ou até mesmo resolver os recorrentes problemas com _especificidade_ de seletores;
- Auxiliam na organização e na manutenção dos arquivos CSS existentes em um projeto;
- São extremamente úteis quando lidando com _codebases_ muito grandes, _design systems_ ou até mesmo com estilos de terceiros;
- Sua ordem de precedência é determinada pela ordem na qual os _layers_ são **declarados** (o que vem depois, tem maior prioridade);
- Estilos fora de _layers_ tem maior prioridade que os demais;
- Suportada pela grande maioria dos navegadores mais modernos ([Can I use - Cascade Layers](https://caniuse.com/css-cascade-layers)).

---
hideInToc: true
layout: quote
---

# "A precedência de um layer se sobrepõe a especificidade de qualquer seletor."

Una Kravets, Chrome for Developers.

---
hideInToc: true
---

# Cascade layers

- A definição de _layers_ é bastante simples, partindo da palavra-chave `@layer`;
- Qualquer nome é aceito, inclusive no formato `kebab-case`.

Definindo layers sequencialmente em um mesmo arquivo:

```css
@layer base {
  a { /* (0, 0, 1) */
    color: red; /* Ignorado */
  }

  .link { /* (0, 1, 0) */
    color: blue; /* Ignorado */
  }
}

@layer typography {
  a { /* (0, 0, 1) */
    color: green; /* Afeta TODOS os links. */
  }
}
```

---
hideInToc: true
---

# Cascade layers

Definindo todos os layers de uma só vez no topo de um arquivo (**recomendada**):

```css
/* global.css */
@layer base, typography, utilities;

/* 
  Uma vez definidos, podemos atribuir as regras de estilo a cada layer
  e a ordem em que essa definição será feita não irá alterar o resultado final. 
*/

@layer typography {
  a { 
    color: green;
  }
}

@layer base {
  a {
    color: red;
  }
}
```

---
hideInToc: true
---

# Cascade layers

Combinando _layers_ com a importação de arquivos:

```css
/* Base */
@import '../styles/base/base.css' layer(base); /* Body and base styles */
@import '../styles/base/theme.css' layer(theme); /* Theme variables */
@import '../styles/base/utilities.css' layer(utilities); /* Base utilities */

/* Layouts */
@import '../styles/components/post.css' layer(layouts); /* Post layout */

/* Components */
@import '../styles/components/cards.css' layer(components); /* Imports card */
```

<!-- Docs -->
<AppReferences class="mt-[78px]">
  <AppLink url="https://www.jefersonsilva.me/articles/organise-your-css-with-cascade-layers" title="Organise your CSS with Cascade Layers" />
</AppReferences>

---
hideInToc: true
layout: section
---

<AppLink url="https://codepen.io/leoadamo/pen/abMKpPb?editors=1100" title="Demo" class="text-4xl" />
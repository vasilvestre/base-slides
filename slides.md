---
titleTemplate: '%s'
theme: seriph
background: https://source.unsplash.com/1920x1080/?developer
highlighter: shiki
lineNumbers: true
info: false
css: unocss
hideInToc: true 
---
# Étendre Sylius 1.12

API (Platform)

<div class="abs-br m-6 flex gap-2">
  <a rel='nofollow' href='https://github.com/vasilvestre/extending-sylius-1.12-09-22' border='0' style='cursor:default'><img src='https://chart.googleapis.com/chart?cht=qr&chl=https%3A%2F%2Fgithub.com%2Fvasilvestre%2Fextending-sylius-1.12-09-22&chs=180x180&choe=UTF-8&chld=L|2' alt=''></a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: center
hideInToc: true
---

# De quoi on parle ?

<Toc />

---
layout: center
class: text-center
src: ./pages/presentations.md
---

---
layout: section
title: Sylius 1.12
level: 1
---
# Sylius 1.12

---
layout: section
title: Sylius ?
level: 2
---

# Sylius ?

---
layout: center
hideInToc: true
---

* Ecommerce
* Symfony
* Headless (ou non)
* Pas ~~(faible)~~ dette technique
* Customisable
* Testé

---
layout: two-cols
hideInToc: true
src: ./pages/sylius_and_apip.md
---

---
layout: center
title: Nouveautés annoncées
level: 2
---

<img src="/1.12-release-content.png" width="620" height="501">

---
layout: center
src: ./pages/date_et_contenu.md
---

---
layout: section
title: Contexte projet
level: 1
---

# Contexte projet

## Les marketplaces

<!-- + d'explications du contexte et de chaque point -->
---
layout: center
title: Tendance
level: 2
---

# Tendance

<img src="/marketplace_stats.png" height="381" width="600">

---
layout: center
src: ./pages/problematiques.md
---

---
layout: section
src: ./pages/sections/exemples.md
---

---
src: ./pages/sections/ajout_siret.md
---

---
src: ./pages/sections/profil_publique.md
---

---
src: ./pages/sections/unicite_produit.md
---

---
layout: center
title: Bonus
level: 1
---

# Bonus : méthodologie

<!-- Normalizer, ItemDataProvider, Handler -->
---
hideInToc: true
layout: center
---

<h3>Visiter le profiler partie Request Attributes</h3>

<img src="/profiler_methodologie.png" width="620" height="501">

---
hideInToc: true
layout: center
---

<h3>Depuis la 6.1</h3>

<img src="/symfony-profiler-serializer.png">

---
layout: end
hideInToc: true
---

<!-- Remercier Akawaka, le staff nottament Thibault et Grégoire Hebert -->
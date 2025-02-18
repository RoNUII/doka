---
title: "`aria-busy`"
description: "Одно из дополнительных состояний изменяющихся областей, которое помогает скринридерам дождаться завершения всех изменений и рассказать о них за один раз."
authors:
  - doka-dog
keywords:
  - доступность
  - ARIA
  - ARIA-атрибут
  - live region
  - живая область
  - интерактивная область
related:
  - a11y/aria-intro
  - a11y/aria-attrs
  - a11y/aria-roles
tags:
  - doka
  - placeholder
---

## Кратко

[Состояние изменяющихся областей](/a11y/aria-attrs/#atributy-izmenyayushchihsya-oblastey) из [WAI-ARIA](/a11y/aria-intro/#specifikaciya). `aria-busy` указывает на то, что элемент сейчас изменяется, поэтому вспомогательная технология должна подождать и пока ничего не рассказывать пользователям.

## Пример

```html
<section role="feed" aria-busy="false">
  <h2>Пока вас не было</h2>
  <article aria-posinset="5" aria-setsize="-1">
    <!-- Содержание поста -->
  </article>
  <article aria-posinset="6" aria-setsize="-1">
    <!-- Содержание поста -->
  </article>
</section>
```

## Как пишется

Добавьте к тегу атрибут `aria-busy` с одним из двух значений:

- `true` — изменения произошли и о них можно рассказать.
- `false` (по умолчанию) — изменения не ожидаются.

`aria-busy` можно использовать для всех тегов и [ARIA-ролей](/a11y/aria-roles/).

Чтобы `aria-busy` работал правильно, не обойтись без [JavaScript](/js/). Когда изменения в живой области завершены, переключите значение атрибута с `false` на `true`.

## Как понять

«Живая» область — это область страницы, в которой что-то постоянно обновляется из-за внешних событий. Например, появляется уведомление или ошибка у поля, когда пользователь ввёл неправильные данные. Так пользователи [скринридеров](/html/screenreaders/) могут узнать об изменениях автоматически, без перехода к этой части страницы.

`aria-busy` пригодится для интерактивных элементов, в которых происходит одновременно много изменений. С помощью этого атрибута можно накапливать изменения и рассказывать о них пользователям один раз. К примеру, атрибут можно использовать в ленте новостей социальной сети.

---
layout: page
title: css
description: css
categories: language
---

h2. {{ page.title }}

### selectors

- `#element-id`
- `.class-name`
- `element-type`
- `:hover` (for links, when hovered over)
- specificity (`id` > `class` > `type`) takes precedence over order

### arrangements

- display: div, h1-h6, form
- inline: svg, a, span
- inline-block: in a line, but can adjust their width and height

### position

- static     (default)
- relative   (relative to natural position)
- fixed      (fixed position in browser window)
- absolute   (relative to parent element)

content) padding) border) margin

### relative units

- em         relative to element's font size
- rem        relative to root element's font size
- %          relative to parent element's font size

default font size for root element is typically 16px

### media

`@media` - queries to determine size of screen and apply specific
styles in response

```
@media screen and (min-width:992px) {
}
```

target small devices and use query to adjust for larger devices
or maybe the opposite

### flexbox layout

flexbox layout: distributing items within a container
(can match vertical heights of child items)

```
box-sizing: border-box /* so padding + border included in size of element */

<div class="flex-container">
    <div class="flex-item"></div>
     <div class="flex-item"></div>
     <div class="flex-item"></div>
</div>

.flex-container { display:flex; }
.flex-item { flex-basis:25%; } /* horizontal space */
    also justify-content, align-items, flex-wrap
```

### frameworks

"A CSS framework is a pre-written set of CSS files that apply styles
to your elements"; bootstrap and materialize

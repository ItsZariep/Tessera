---
layout: post
title: "Customizing pagination"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/customizing-pagination.jpg
---

Welcome! This guide explains how to customize pagination on your index/home page.

Tessera uses `jekyll-paginate` plugin to manage pagination

---

## Where to Add Custom Styles

Tessera includes a special file:
 `assets/css/custom.css`

This file is automatically loaded by the theme, making it the best place to write your own CSS. It allows you to:

* Override existing styles
* Add new styles for custom components
* Tweak layout, colors, typography, spacing, and more

Since this file is separate from the main theme CSS, your custom styles won’t be overwritten when the theme updates and you only need to define the specific changes you need.

---

## Setting up

If pagination is not working, probably you need to define plugin usage on your `_config.yml`:

```
plugins:
  - jekyll-paginate
```

After that, you need to set your `index.html` like this:

```
---
layout: home
title: Tessera
paginate: 9
---
```

- layout: Need to be `home` to work properly with Tessera theme
- title: The title of your index / home page
- paginate: The number of post you want on your main grid

---

## Customizing (CSS)

You need to use your [`custom.css`]({% post_url 2025-05-16-modify-css-styles %}) for those customizations

### Posts per grid's row

```
#posts-container {
    grid-template-columns: repeat(auto-fill, minmax(30%, 1fr));
}

```

Grid's row is calculated with percentages, by default is 30% (3 posts).

#### examples

- 60% (or more): 1 post
- 50%: 2 posts
- 30%: 3 posts
- 23%: 4 posts

### Post image aspect ratio

```
.post-image-wrapper {
    padding-top: 52.36%;
}
```

The aspect ratio is calculated by the percentage of padding, there is a list of common aspect ratios:

- `52.36%`: `1.91:1`  (OG:Image standard)
- `56.25%`: `16:9` (Landscape)
- `62.50%`: `16:10` (Landscape)
- `66.66%`: `3:2` (Classic)
- `75%`: `4:3` (Standard)
- `80%` : `5:4` (Portrait)
- `100%`: `1:1` (Square)

### Post image fill mode

```
.post-image {
    object-fit: cover;
}
```

Fill mode is managed by CSS object-fit:

-Here’s a list of common CSS `object-fit` fill modes used for controlling how content (usually images or videos) fills the dimensions of a container:

### Common `object-fit` values

1. **`fill`**

   * **Description**: Stretches the content to fill the container, ignoring aspect ratio.
   * **Result**: May cause distortion.

2. **`contain`**

   * **Description**: Scales the content to fit within the container while preserving aspect ratio.
   * **Result**: No cropping, but may leave empty space (letterboxing).

3. **`cover`**

   * **Description**: Scales the content to completely cover the container while preserving aspect ratio.
   * **Result**: Content is cropped to fill the container.

4. **`none`**

   * **Description**: Keeps the content at its original size.
   * **Result**: No scaling, may overflow the container.

5. **`scale-down`**

   * **Description**: Acts like `none` or `contain`, whichever results in a smaller image.
   * **Result**: Only scales down the image if it's larger than the container.

### Pagination controls

```
.pagination-controls a {
    text-decoration: none;
    border: 1px solid var(--grey1);
    padding: 4px 8px;
    margin: 0 4px;
    display: inline-block;
    color: var(--fg);
    border-radius: 4px;
}
```

## Change Pagination controls logic:

[Copy `_includes/pagination-controls.html` to your site]({% post_url 2025-05-16-modifying-html-components %}), take account you need knowledge about Jekyll Liquid logic.
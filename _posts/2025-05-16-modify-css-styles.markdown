---
layout: post
title: "Modifyng CSS Styles"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/modifyng-css-styles.jpg
---

# Customizing CSS Styles in the Tessera Jekyll Theme

Welcome! This guide explains how to customize **CSS styles** when using the **Tessera** Jekyll theme.

Tessera is built for flexibility and makes it easy to override default styles without editing the core theme files. The recommended way to apply your own styles is by using the `assets/css/custom.css` file.

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

## How to Use It

1. **Open** (or create) the file at `assets/css/custom.css` in your site’s root directory.
2. **Write your custom styles** as needed. For example:

```css
/* Change the size of the right pane */
#right-container {
	width: 30%;
}
```

3. **Save the file and rebuild your site.** Tessera will automatically include your custom styles in the final output.

---

## Example: Changing Theme Colors

Here’s a simple example of how you might override the theme's color scheme:

```css
:root {
	--bg: #0f2200;
	--fg: #d1ffac;
}
```

---

By using `custom.css`, you keep your changes clean, organized, and upgrade-safe. It's the recommended method for styling your Tessera-based Jekyll site.

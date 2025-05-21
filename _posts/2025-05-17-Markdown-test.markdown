---
layout: default
title: "Markdown-test"
author: "ItsZariep"
date: 2025-05-17
image: /assets/img/thumb/markdown-test.jpg
categories: [jekyll, markdown, features]
tags: [jekyll, markdown, cheatsheet]
---


# Jekyll Markdown Features

This document demonstrates **all major Markdown features** supported by **Jekyll**.  
Jekyll uses **kramdown** as its default Markdown engine (unless configured otherwise).  

---

## Headings

# H1
## H2
### H3
#### H4
##### H5
###### H6

---

## Emphasis

- *Italic* or _Italic_
- **Bold** or __Bold__
- ***Bold & Italic***
- ~~Strikethrough~~ (GFM)

---

## Lists

### Unordered List

- Item 1
- Item 2
  - Subitem
    - Sub-subitem

### Ordered List

1. First
2. Second
   1. Subitem
   2. Subitem

---

## Links

- [Inline link](https://jekyllrb.com)
- [Reference link][jekyll-site]
- <https://github.com>

[jekyll-site]: https://jekyllrb.com

---

## Images

![Site Logo]({{ site.baseurl }}/assets/img/avatar.webp)
---

## Code

### Inline Code

Use the `jekyll serve` command.

### Code Block

#### Fenced (with syntax highlighting)

```ruby
def hello
  puts 'Hello, Jekyll!'
end
````

#### Indented

```
def hello
  puts 'Hello from indent!'
end
```

---

## Blockquotes

> “Jekyll is a static site generator.”
> — GitHub

---

## Tables (GFM)

| Feature     | Supported |
| ----------- | --------- |
| Tables      | ✅         |
| Fenced Code | ✅         |
| Emoji       | ✅         |

---

## Task Lists (GFM)

* [x] Write Markdown
* [ ] Push to GitHub
* [ ] Celebrate 🎉

---

## Emoji (GFM)

\:smile: \:rocket: \:octocat:

---

## Horizontal Rule

---

## HTML Support

You can use raw HTML:

<div style="color: red;">This is red text using HTML.</div>

---

## Liquid Tags (Jekyll-specific)

### Variables

```liquid
{{ page.title }} — {{ site.time | date: "%B %d, %Y" }}
```

### Control Structures

```liquid
{% if page.author %}
Author: {{ page.author }}
{% endif %}
```

### Include

```liquid
{% include userbox.html %}
```

---

## Highlight Tag (Jekyll/kramdown)

{% highlight html %}

<div>Hello Jekyll!</div>
{% endhighlight %}

---

## Footnotes

Here's a sentence with a footnote.[^1]

[^1]: This is the footnote text.

---

## Abbreviations

\*\[HTML]: Hyper Text Markup Language

HTML is a markup language.

---

## Definitions

Apple
: A fruit.

Orange
: Another fruit.

---

## Math (if using a plugin or MathJax)

```math
E = mc^2
```

Or inline: $a^2 + b^2 = c^2$

---

## TOC (with plugin or Liquid)

* Table of Contents
  {\:toc}

---

## Conclusion

This page covers **all standard and extended Markdown features** that are usable in a **Jekyll** site, including support for:

* GitHub-Flavored Markdown (GFM)
* Jekyll’s Liquid templating
* Raw HTML
* Syntax highlighting

> Customize your `_config.yml` to enable additional plugins or alter Markdown behavior.
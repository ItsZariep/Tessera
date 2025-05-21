---
layout: post
title: "Custom URL Structure"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/custom-url-structure.jpg
---

Welcome! This guide explains how to set custom URL Structure

This method doesn't require any plugin, is a base Jekyll feature

---

## Setting up

Jekyll uses option `permalink` in  `_config.yml` to set pages/posts URLs

## Examples

### Post title only

```yaml
permalink: /:title.html
```

### Year/Month/Title

```yaml
permalink: /:year/:month/:title/
```

Generates URLs like:
`/2025/05/custom-url-structure/`

### Category and Title

```yaml
permalink: /:categories/:title/
```

Generates URLs like:
`/tutorial/custom-url-structure/`

### Full Date and Title

```yaml
permalink: /:year/:month/:day/:title/
```

Generates URLs like:
`/2025/05/16/custom-url-structure/`

### Pretty URLs (No file extension)

```yaml
permalink: /:categories/:year/:title/
```

Generates URLs like:
`/tutorial/2025/custom-url-structure/`

### Static Folder and Title

```yaml
permalink: /blog/:title/
```

Places all posts under `/blog/`, e.g.:
`/blog/custom-url-structure/`
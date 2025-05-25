---
layout: post
title: "Configure jekyll-archives"
date: 2025-05-16
categories: Tutorial
image: /assets/img/thumb/configure-jekyll-archives.jpg
---

Welcome! This guide explains how to configure `jekyll-archives` on your site

This method requires `jekyll-archives` plugin

> NOTE: `Jekyll-archives` is not available for Github Pages, if you want to use this feature on GitHub, please use GitHub Actions instead

## Setting up

- Archives needs setup on _config.yml:

```
jekyll-archives:
  enabled:
    - year
    - month
    - categories
    - tags
  layout: archive
  permalinks:
    year: /archives/:year/
    month: /archives/:year/:month/
    category: /category/:name/
    tag: /tag/:name/
```

You can remove section
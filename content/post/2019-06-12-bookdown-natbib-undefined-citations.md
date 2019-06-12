---
title: Bookdown natbib undefined citations
author: Mark Chen
date: '2019-06-12'
slug: bookdown-natbib-undefined-citations
categories:
  - R
tags:
  - Bookdown
description: ''
thumbnail: ''
---

I came across the warnings like below when I built my book using `bookdown`.

```
...
Package natbib Warning: Citation `schmitt_detection_2012' on page 30 undefined 
on input line 1443.
...
```

I did not find the solution by searching. In reflection, it is due to I did not include `index.Rmd` in the list of `Rmd` files in `_bookdown.yml`. I set `rmd_files` in `_bookdown.yml` to order the `Rmd` files, rather than order them by their file names.
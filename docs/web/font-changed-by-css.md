---
layout: post
title: Font changed by CSS
parent: Web UI
nav_order: 2
date: 2020-01-06
---

# Custom font changed by CSS

## 1. Issue

When I created a page with React, and added some text with custom font. I was challenged by UX of our team, because what I made was different from that he designed.

**What I made**

![](/assets/images/font_issued.png)

**What UX designed**

![](/assets/images/font_designed.png)

You may notice the difference of comma after 'Hello'.

## 2. Solution

Anwser firstly, add these two CSS attributes to the text element:
```
font-feature-settings: normal;
font-variant-numeric: normal;
```

After I tried many different combinations of CSS attributes in Chrome dev tools, and found this.

```
font-feature-settings: 'tnum', "tnum";
font-variant-numeric: tabular-nums;
```

Value of attributes above(tnum ortabular-nums ) aims to show number as monospace, and therefore the comma is stretched.

More details are descripted in [official docs](https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings).
---
layout: default
title: GIF
parent: Components
nav_order: 8
---

# GIF
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

The `GIF-Component` is used to display a GIF. You can upload `.gif` files to the editor and then select your GIF from the list. The GIFs are indentified by their file name, so you can't upload multiple GIFs with the same name. You don't need to upload the GIFs to your server, as all GIFs are stored in the savepoint/usage files. But you should remove all GIFs that you don't use and only upload GIFs in the resolution you need (so don't upload a 1000x2000 GIF if you scale it down to 120x240) as this would make the server start much slower.

Dithering is also available for GIFs.

You can configure whether the GIF should by paused by default or not through the `PAUSE BY DEFAULT` checkbox.

![]({{site.baseurl}}/assets/components/gif.png)

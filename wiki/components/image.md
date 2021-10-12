---
layout: default
title: Image
parent: Components
nav_order: 2
---

# Image
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

The `Image-Component` is used to display an image. You can upload `.png` and `.jpg` images to the editor and then select your image from the list. The images are indentified by their file name, so you can't upload multiple images with the same name. You don't need to upload the images to your server, as all images are stored in the layout files. But you should remove all images that you don't use and only upload images in the resolution you need (so don't upload a 1000x2000 image if you scale it down to 120x240) as this would make the server start much slower.

![]({{site.baseurl}}/assets/components/image.png)

## Dithering

You can enable image dithering by checking the `DITHERING` checkbox. As minecraft maps can only display very few colors image dithering can help to improve the look of your converted image.

Without dithering:

![]({{site.baseurl}}/assets/components/image_d_off.png)


With dithering:

![]({{site.baseurl}}/assets/components/image_d_on.png)

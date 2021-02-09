---
layout: default
title: Remote Image
parent: Components
nav_order: 9
---

# Remote Image
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

The `Remote-Image-Component` is used to display a images that are diynamically loaded from a web server (URL). You can specify the URL the image should be loaded from in the `IMAGE` text input. In the URL you can use PlaceholderAPI placeholders and `%UUID%`, `%UUID-U%` (UUID without dashes) and `%NAME%`. So you can load different images for different players (e.g. `https://visage.surgeplay.com/head/%UUID_U%` to load the player head). The image is loaded once the player is in sight of the GUI. You can add a child component that will be displayed while the image is being loaded. You can check the `PREVIEW LOADING COMPONENT` checkbox to preview that component in the editor. If no loading component is added then the image will be invisible until it gets loaded.

Dithering is also available for remote images (this will increase the load time!).

![]({{site.baseurl}}/assets/components/remote-image.png)

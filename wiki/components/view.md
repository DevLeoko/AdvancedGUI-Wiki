---
layout: default
title: View
parent: Components
nav_order: 7
---

# View
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

The `View-Component` only shows one of its child components at once. The view component can have multiple child components and by default only the first one is visible. Through the `View-Action` you can check which of child components should be visible to the player. An example of where one might use this is when you have a menu with a start page, stats page, rules page and info page. By default you want to show the start page and when the user clicks on the stats button you can use a view action to change the view to the stats page.

Use the `Show component` dropdown to preview different view child components in the editor.
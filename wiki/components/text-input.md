---
layout: default
title: Text Input
parent: Components
nav_order: 11
---

# Text Input
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

The `Text-Input-Component` is used to get text input from a player. When the text-input component is empty then the `PLACEHOLDER` text is displayed with the `PLACEHOLDER COLOR` (e.g. `Name...` in the image below). Once a player hovers the input field the background color changes to it's active color and a pulsating cursor appears. The player can input text by either normally writing to the chat which will only update the input value when the player actually sends his message. Or the player can open the chat and start his message with `// ` (e.g. `// Hello there`) which will enable the input to update directly as the player types (only works for 1.10+).

The `MAX INPUT LENGTH` defines how many characters can be displayed at once in the input field. When the user enters more characters then possible the input text will shift to the left. So a player can input more characters then the `MAX INPUT LENGTH`. Andjust this value so that the text does not go outside the input box.

![]({{site.baseurl}}/assets/components/text-input.png)

## Use input value

The input value that the player typed in is available as a PlaceholderAPI placeholder called `%advancedgui_textinput_XXX%` where `XXX` is the component ID. So it can be used both inside the GUI and in other plugins. This value is only available while the player interacts with the GUI.

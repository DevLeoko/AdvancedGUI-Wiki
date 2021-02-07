---
layout: default
title: Basics
nav_order: 3
---

# Basics
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Layout

A layout defines how a GUI looks and how it behaves. You can place multiple GUIs ingame that have the same layout. GUIs are rendered per player, so if one player triggers a change to the GUI other players won't normally be able to see this change.

A layout consists of:
- A name (can be changed at the top left of the web editor)
- A size (can be changed at the top of the web editor)
- Components

# Components

A component defines a certain part of a layout. For example there are `Text-Components` that render some text or there are `Rect-Components` which render colored rectanges. A component can also consist of other components (we then call them child-components). For example a `Group-Component` can group multiple component together. Or a `Hover-Component` has two child components; Where one is normally displayed and the other one is displayed when it gets hovered.

Each component has:
- A name (just for organization in the web editor)
- A uniqe ID (used by developers)
- Visibility value - whether the component is (currently) visible
- Click actions (*optional*)

# Click actions

These actions get executed when a player clicks on a component. Almost every component can have these click actions. An example of an action would be the `Command Action` that runs a command when triggered. Actions can also consist of other actions. For example the `Permission-Check(Action)` has two child actions. When this action gets triggered in checks whether the player that triggered it has a certain permission and if so executes the first action and if not the second one.
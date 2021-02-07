---
layout: default
title: Home
nav_order: 1
description: "AdvancedGUI Wiki / Documentation"
permalink: /
---

# Create truly interactive GUIs
{: .fs-9 }

AdvancedGUI enables you to intuitively build interactive GUIs through a web editor and display them in ItemFrames or hand-held maps. 
{: .fs-6 .fw-300 }

[Open web editor](https://advancedgui.netlify.app/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Join our discord](https://discord.gg/ycDG6rS){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started

### Dependencies

[ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) is **required**.

Using [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) is optional but adds a lot of functionality to your GUIs through *Placeholder-Checks*, so you might want to install that too.

For the *Money-Check* to work and for `run command as OP`, you will also need to install [Vault](https://www.spigotmc.org/resources/vault.34315/) (optional).

### Installation

Just put the AdvancedGUI and ProtocolLib plugins into your `plugins/` folder and restart your server.

### Quick Start

This is a really quick walkthrough on how AdvancedGUI works:

#### Creating your first GUI:
To create a GUI you use our [web editor](https://advancedgui.netlify.app/).

You get started by clicking `Add component` on the bottom-left and see where your creativity takes you from there. 
Once you are satisfied with your GUI you should do two things:
1. `Export savepoint` - This gives you a file that you can later import back into the web editor if you want to do any more changes or share your GUI.
2. `Export for usage` - This gives you a file converted to a format that is understood by the plugin. You are not able to import this file back into the editor!
Place the usage `.json`-file in the `layout/` folder of AdvancedGUI and do `/ag reload`. Now your GUI should be available ingame. You can see all your Layouts with `/ag layouts`.

#### Placing and GUIs ingame:
You can place a GUI with `/ag place [Layout-Name]` and clicking the top-left ItemFrame of a matching ItemFrame grid. Or you can obtain a GUI Item with `/ag item [Layout-Name] (Player)` if it's a 1x1 GUI.

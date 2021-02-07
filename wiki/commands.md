---
layout: default
title: Commands & Permissions
nav_order: 2
---

# Commands & Permissions
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Permissions

The `/ag item` command requires the user to have the `ag.item` permission. All other commands require the `ag.manage` permission.

## Commands
### Help
`/ag help`

This command shows all available commands.

### Place a GUI
`/ag place [Layout-Name] (Interaction radius) (-invisible)`

This command is used to place a GUI. After executing this command you will have to right-click the top-left ItemFrame of an ItemFrame gird that is large enough for the GUI.

The `Interaction radius` defines the distance in blocks that the player has to be in to be able to interact with the GUI and for the GUI to have a full frame rate (~20 fps).

The `-invisible` can be added to make the ItemFrames invisible, which also makes them flat (only works in 1.16+).

### Reframe (fix)
`/ag reframe`

This command refreshes all map-items in a GUI (fix when item-frames are empty)

### Break / Remove a GUI
`/ag break`

After performing this command you can right-click a GUI to remove it.

### Delete / Remove a GUI
`/ag delete [ID]`

This command deletes the GUI with the given `ID`.

### Obtain GUI item
`/ag item [Layout-Name] (Player) (Slot)`

This command is used to obtain a hand-held map item for 1x1 layouts.

With the `player` argument you can specify the target player and the `slot` to put the item in. This will overwrite any item currently in this slot.

### Reload
`/ag reload (-resource)`

This command reloads the configuration and all layouts.

The `-resource` flag will also clear the resource cache. This might be neccessary to reload images that you have changed in a layout but will cause the reload to take longer.

### List all GUIs
`/ag list`

Lists all active GUIs

### List all layouts
`/ag layouts`

List all available layouts

### Plugin info
`/ag`
---
layout: default
title: Placeholders
nav_order: 7
---

# Placeholders
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Placeholders can be used in every text field of a layout: the text of `Text-Components` (with `CONTAINS PLACEHOLDERS` enabled), the command of command actions, the message of message actions, the value of metadata actions, the URL of `Remote-Image-Components` and the placeholder checks.

## PlaceholderAPI

As long as [PlaceholderAPI](https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders) is installed on your server all of its placeholders are available (e.g. `%player_name%`).

### Update interval

By default these placeholders are parsed on every tick for every player that is interacting with a GUI. Some placeholders are expensive to parse (e.g. when they read from a database), so you can make AdvancedGUI reuse the previously parsed value for a while through the `PlaceholderParseInterval` option in the `config.yml`:

```yaml
# How often (in milliseconds) PlaceholderAPI placeholders are re-parsed for each player.
PlaceholderParseInterval: 0
```

The interval is given in milliseconds, so `1000` parses each placeholder at most once per second per player and `5000` once every five seconds. The default `0` parses on every tick.

## Metadata placeholders

`%meta.<key>%` gets replaced with the value that was stored under `<key>` through a metadata action.

## Instance placeholders

Instance placeholders are replaced with values of the GUI the player is currently interacting with. This keeps your layouts portable: you can place the same layout somewhere else and commands that interact with the world keep working without having to edit the layout.

On wall GUIs everything is resolved against the top-left ItemFrame of the GUI (the anchor), on handheld GUIs against the player holding the map.

- `%instance.x%`, `%instance.y%`, `%instance.z%` - the block coordinates of the anchor
- `%instance.pos%` - the anchor as `x y z` (drop-in for command coordinates)
- `%instance.world%` - the name of the world the GUI is in
- `%instance.direction%` - the direction the GUI is facing (e.g. `NORTH` or `FLOOR_EAST`; handheld: the direction the player is facing)
- `%instance.center%` - the center of the GUI as `x y z` (may contain decimals)
- `%instance.id%` - the ID of the GUI (handheld: the ID of the map)
- `%instance.layout%` - the name of the layout
- `%instance.offset.<dx>.<dy>.<dz>%` - the anchor shifted along the world axes, as `x y z`
- `%instance.rel.<right>.<up>.<front>%` - the anchor shifted relative to the orientation of the GUI, as `x y z`. Here `right` follows the x-axis of the GUI, `up` points to the top of the GUI and `front` out of the GUI towards the player looking at it.

So a command action such as `setblock %instance.rel.0.0.-1% air` always targets the block that the top-left ItemFrame hangs on, no matter where the GUI is placed or which way it is facing.

---
layout: default
title: Actions
nav_order: 5
---

# Actions
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Command action

The command action executes a certain command. The command should be entered **without** a leading slash and can contain the `%player%` placeholder which will be replacedd with the name of the player that executed the action. The command can be run as console, as an operator (bypasses player permissions) or as the normal player.

### Run BungeeCord commands

As AdvancedGUI is a Spigot plugin it can not run bungee commands directly. But you can use a plugin such as [HopeCommander](https://www.spigotmc.org/resources/hopecommander.81455/) which enables you to use the command `hopecommander <bungee-command>` to execute bungee commands from spigot (e.g. `hopecommander send %player% lobby` will send the player to the lobby server). Just make sure to run the command as console.

## Message action

The message action sends a message to the player that triggered the action. You can use color codes and PlaceholderAPI placeholders.

## Visiblity action

The visiblity action changes the visiblity of the component with the provided `COMPONENT ID`.

## View action

The view action changes what child component of a view component is currently shown the the player. Enter the id of the view component `VIEW ID` and the `TARGET ID` of the child component that should be made visible. All other child components will become invisible.

## Delay action

The delay action will delay its child actions by the given amount of ticks (1 tick = 50ms).

## List action

The list action is used to group multiple child actions together. It executes them one after another in the given order. This action mostly used in checks to have multiple action in the psitive or negative outcome.

## Checks action

The check action can have two child actions and executes the first one if a given check passes for the player and the second one if not. Use list actions to use more than one action in each case.
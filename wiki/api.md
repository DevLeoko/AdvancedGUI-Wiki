---
layout: default
title: API - Getting started
nav_order: 7
---

# API - Getting started
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


[Visit Java Docs](https://advancedgui.app/apidocs/){: .btn .btn-purple }

---

# Installation

The AdvancedGUI API is available as a Maven dependency. To start using the API, add these snippets to your `pom.xml`

```xml
<repository>
  <id>respark-releases</id>
  <name>Respark - Maven Repository</name>
  <url>https://maven.respark.dev/releases</url>
</repository>
```

```xml
<dependency>
  <groupId>me.leoko.advancedgui</groupId>
  <artifactId>AdvancedGUI</artifactId>
  <version>2.2.8</version>
</dependency>
```

also make sure to declare AdvancedGUI as a dependency in your `plugin.yml`

```yaml
depend: [AdvancedGUI]
```

# Introduction

When working with the AdvancedGUI API the most common use-case is to extend the functionallity of a GUI Layout that was build with the web editor.
Building the complete Layout from scratch by code, can be a lot of work so it is best practice to build as much as you can in the web editor and then use the API to modify that existing layout. In the following we will look at some ways you can do that.

# First steps

The layout-file of the layout that you want to extend should be place into the `layout/` folder - same as the regular layout files.

First you need to create a class, that will handle the extension logic:
```java
public class MyLayoutExtension implements LayoutExtension {
    public static final String LAYOUT_NAME = "LAYOUT-NAME";

    @Override
    @EventHandler
    public void onLayoutLoad(LayoutLoadEvent event) {
        if (layout.getName().equals(LAYOUT_NAME)) {
            // Your extension code goes here
        }
    }
}
```

the `onLayoutLoad(...)` method will be called each time a new layout is loaded (e.g. on server start or through _/ag reload_). So this is the best place to make your changes. As this method gets called for all layouts it is important to check for the layout name and only extend the layout you are interested in.

Add this line to your plugins `onEnable(...)` method to register the extension:
```java
@Override
public void onEnable() {
    LayoutManager.getInstance().registerLayoutExtension(new MyLayoutExtension(), this);
}
```

This also registers the class as a regular spigot event-listener so you can listen to AdvancedGUI events like `GuiInteractionExitEvent` in your extension class.

# Accessing components

Components are the heart of a layout, they define how the layout behaves and renders. Each layout has a template component-tree which is represented by a group-component at the top which contains a numer of child components which again can contain child components of their own. This component-tree gets copied once a new player starts an interaction, so each interaction has its own component-tree. In most cases changes should be made to the template component-tree. You can access the defaut component-tree through:

```java
Layout layout = event.getLayout();
GroupComponent componentTree = layout.getTemplateComponentTree();
```

To access a specific component by its ID in the component-tree you simply call:
```java
Component component = componentTree.locate("COMPONENT-ID");
```
or to get the specific component class returned (e.g. TextComponent):
```java
TextComponent component = componentTree.locate("COMPONENT-ID", TextComponent.class);
// same as: TextComponent component = (TextComponent) componentTree.locate("COMPONENT-ID");
```

# Examples of component properties

Depending on the type of component, there are several things you might want to do to intoduce custom logic

## Setting custom click action

```java
componentTree.locate("COMPONENT-ID").setClickAction((interaction, player, primaryTrigger) -> {
    Bukkit.broadcastMessage(player.getName()+" click the component!");
});
```

**Important:** To modify components in a click action (e.g. hide some component) you have to locate the component on the component-tree of the interaction not the template component-tree.
As the template one got copied for the interaction and the player now sees his own component-tree.

```java
componentTree.locate("COMPONENT-ID").setClickAction((interaction, player, primaryTrigger) -> {
    if(player.isSneaking())
      interaction.getComponentTree().locate("COMPONENT-ID-2").setHidden(true);
});
```

So this would be **wrong**:
```java
componentTree.locate("COMPONENT-ID").setClickAction((interaction, player, primaryTrigger) -> {
    if(player.isSneaking())
      componentTree.locate("COMPONENT-ID-2").setHidden(true);
});
```

## Setting custom checks

```java
CheckComponent component = componentTree.locate("COMPONENT-ID", CheckComponent.class);
component.setCheck((context, player, primaryTrigger) -> player.isSleeping());
```

## Setting other custom properties

Most components have their own properties, for example you could change the color of a rectangle component or set the active view of a view component

```java
Color orange = new Color(242, 120, 75);
componentTree.locate("COMPONENT-ID", RectComponent.class).setColor(orange);
```

```java
componentTree.locate("COMPONENT-ID", ViewComponent.class).setView("COMPONENT-ID-2");
```

# Inserting a new component

Place a dummy component in the web editor at the position you want to have your own component. Then locate the dummy component and replace it with your own one:

```java
DummyComponent dummyComponent = componentTree.locate("COMPONENT-ID", DummyComponent.class);
dummyComponent.setComponent(myComponent);
```

Where `myComponent` could by any component you would like: A basic component you can also place through the editor, components that are only available through the API (like `ListComponent` or `HoverDetectorComponent`) or even your very own component. To create your own component, just create a new class and extend `Component` or `RectangularComponent` if your component has an overall rectangular shape. A tutorial on how to create your own component is coming soon.
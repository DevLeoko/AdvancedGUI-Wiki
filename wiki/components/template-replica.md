---
layout: default
title: Template & Replica
parent: Components
nav_order: 10
---

# Template & Replica
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

The `Template-Component` and `Replica-Component` are used when multiple components (or group of components) look the same or very similar. These components enable you to only create & design the component once in the template component and then copy it through replica components. You can change the look of the replica components by using variables from the template component. When you change something in the template component, all replica components will adjust automatically.

![]({{site.baseurl}}/assets/components/template-n-replica.png)

## Template

A `Template-Component` can smimilar to a group component have multiple child components. In the template component's settings you can define variables. Those variables can then be used in the child components. Text variables can be used in any text input and number variables in most number inputs. You use them by typing in `#VARIABLE_NAME` so for example if you have a variable called `mapName`, you could have a text component with the text `Play on the #mapName map!`. To use number variables in number inputs, you have to press the `#` key to enable text input. This only works for some inputs.

![]({{site.baseurl}}/assets/components/template-settings.png)

## Replica

A `Replica-Component` will replicate templates. You type in the `TEMPLATE ID` of the template that should be replicated and then can adjust all available variables.

![]({{site.baseurl}}/assets/components/replica-settings.png)

## Note for developers

Once exported, all template and replica components are transpiled into group components with the variables resolved to their values. The template components become group components with the same ID and all child components stay the same. The replica components also become group components with the same ID and all the child components from the template get copied accordingly, while their IDs change from their original ID `XXX` to `XXX#YYY` where `YYY` is the ID of the replica component.
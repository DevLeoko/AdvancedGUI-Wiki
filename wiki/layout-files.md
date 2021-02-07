---
layout: default
title: Layout Files
nav_order: 1
---

# Layout Files

A GUI's layout and behaviour is defined in a layout file. These layout files can be create through the web editor. There are two kinds of layout files:

### Savepoints

You use savepoint files to save your work in the web editor. These files can be imported back into the web editor but can not be directly used on your server. To use a savepoint file on your server you will need to import it into the web editor and export the usage file.


### Usage

Usage files are the ones you place into the `plugins/AdvancedGUI/layouts/` folder to get the GUI onto your server. **But these files can not be imported back into the web editor!** So make sure to always also export a savepoint file when you are done with your GUI.

## Examples
You can download some example savepoint files that are used on our showcase-server `AGShowcase.hopefuls.de` here:

[Download example savepoints](https://content.hopefuls.de/AdvancedGUI/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

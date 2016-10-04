---
layout: post
title: Document functionalities of Syncfusion SfDockingManager control for UWP
description: Features of document window on SfDockingManager control for UWP
platform: uwp
control: SfDockingManager
documentation: ug
---

# Document Windows

Document window is one of the state in the `SfDockingManager`. To make children of the `SfDockingManager` as Document, set its `DockState` values as Document.

All the Document windows are added in a `DocumentContainer`, content can be switched by clicking the item header or choosing item from tab strip menu.

![](Document-Windows-images/Document-Windows-img1.jpeg)


## Closing Document Windows

A Document window can be closed using the close button provided in header or using the `Close` context menu item.

`CloseAll` context menu item is used to close all the document tab items in the DocumentContainer.

`CloseAllButThis` context menu item is used to close all the document tab items except the sender raising command in the Document Container.

## Floating Document Windows

A Document window can be moved to float state by dragging or double clicking the item header.

## Document Container behavior with DockFill

Dock windows are allowed to occupy the remaining space when DockFill property is set to true. SfDockingManager does not reserve space for DocumentContainer. So child windows with Document state are hidden in the layout.


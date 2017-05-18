---
layout: post
title:  Events | SfKanban | uwp | Syncfusion
description: This section contains the detailed information about the Kanban dragging and column generated events.
platform: uwp
control: SfKanban
documentation: ug
---

# Events

## ItemTapped

This event is triggered when you tap on any card. The argument contains the following information.

* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedColumnTopic.html)          - Used to get the column of the selected card.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardTopic.html) 			- Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardIndexTopic.html) 			- Used to get the index of the card in a column.

## DragStart

This event is triggered when you start to drag a card. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragStartEventArgsClassIsCancelTopic.html)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardTopic.html)			- Used to get the underlying model of the card.
* [`KeepCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragStartEventArgsClassKeepCardTopic.html)		- Determines whether to keep the dragged card in the source location itself, until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedColumnTopic.html) 	- Used to get the source column of card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardIndexTopic.html)		- Used to get the index of the card in source column.   

## DragEnd  

This event is triggered when whenever dragging is cancelled. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEndEventArgsClassIsCancelTopic.html)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardTopic.html)			- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedColumnTopic.html) 	- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardIndexTopic.html)		- Used to get the index of the card in source column.
* [`TargetKey`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEndEventArgsClassTargetKeyTopic.html) 	- Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEndEventArgsClassTargetColumnTopic.html)	- Used to get the current column which is the drop target for the card.
* [`TargetCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEndEventArgsClassTargetCardIndexTopic.html)		- Used to get the index of the card in target column.

## DragEnter 

This event is triggered when a card enters into a column while dragging. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEnterEventArgsClassIsCancelTopic.html)				- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardTopic.html)				- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedColumnTopic.html) 		- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardIndexTopic.html)			- Used to get the index of the card in source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEnterEventArgsClassCurrentColumnTopic.html)		- Used to get the column upon which the card enters.
* [`CurrentIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEnterEventArgsClassCurrentIndexTopic.html)			- Used to get the index of the card in current column.

## DragLeave 

This event is triggered when a card leaves a column while dragging. The argument contains the following information.

* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardTopic.html)                - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedColumnTopic.html)        - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardIndexTopic.html)         - Used to get the index of the card in source column.
* [`LeftColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragLeaveEventArgsClassLeftColumnTopic.html)		- Used to get the column from which the card leaves.
* [`PreviousCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragLeaveEventArgsClassPreviousCardIndexTopic.html)   -   used to get the index of the card left.

## DragOver

This event is triggered when a card is dragged to a new index within a column. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragOverEventArgsClassIsCancelTopic.html)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardTopic.html)			- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedColumnTopic.html) 	- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragEventArgsClassSelectedCardIndexTopic.html)		- Used to get the index of the card in source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragOverEventArgsClassCurrentColumnTopic.html)	- Used to get the current column which is the drop target for the card.
* [`CurrentIndex`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanDragOverEventArgsClassCurrentIndexTopic.html)		- Used to get the new index of the card in current column.

## ColumnsGenerated 

This event will be fired after the columns are generated automatically. You can access the auto-generated columns using SfKanban.ActualColumns property.


## ColumnGenerated

This event is triggered when a column generated.

* [`Columns`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanColumnsGeneratedEventArgsClassColumnsTopic.html)  -  used to get the generated columns.
* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanColumnGeneratedEventArgsClassIsCancelTopic.html)   -  used to cancel the generated column added to the SfKanban.
* [`CurrentColumn`](https://help.syncfusion.com/cr/cref_files/uwp/sfkanban/frlrfSyncfusionUIXamlKanbanKanbanColumnGeneratedEventArgsClassCurrentColumnTopic.html)   -   used to get the current generated column.
---
layout: post
title:  Kanban Events | SfKanban | uwp | Syncfusion
description: This section contains the detailed information about the kanban dragging and column generated events.
platform: uwp
control: SfKanban
documentation: ug
---

# Events

## CardTapped

This event is triggered when you tap on any card. The argument contains the following information.

* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumn.html)          - Used to get the column of the selected card.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCard.html) 			- Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCardIndex.html) 			- Used to get the index of the card in a column.
* [`SelectedRowIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedRowIndex.html) - Used to get the index of dragging card's row.
* [`SelectedColumnIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumnIndex.html) - Used to get the index of dragging card's column.

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfKanban. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference, based on which the event argument is shown.

>**NOTE**
The default value of the `CardTappedCommandParameter` is `null`.

## CardDoubleTapped

The [`CardDoubleTapped`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.SfKanban~CardDoubleTapped_EV.html) event is triggered when you double tap on any card. The argument contains the following information:

* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs~SelectedCard.html) - Used to get the selected card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs~SelectedCardIndex.html) - Used to get the index of dragging card in a column.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDoubleTappedEventArgs~SelectedColumn.html) - Used to get the column of the selected card.
 
## DragStart

This event is triggered when you start to drag a card. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs~IsCancel.html)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCard.html)			- Used to get the underlying model of the card.
* [`KeepCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragStartEventArgs~KeepCard.html)		- Determines whether to keep the dragged card in the source location itself, until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumn.html) 	- Used to get the source column of card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCardIndex.html)		- Used to get the index of the card in source column.   

## DragEnd  

This event is triggered when whenever dragging is canceled. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs~IsCancel.html)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCard.html)			- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumn.html) 	- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCardIndex.html)		- Used to get the index of the card in source column.
* [`TargetKey`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs~TargetKey.html) 	- Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs~TargetColumn.html)	- Used to get the current column which is the drop target for the card.
* [`TargetCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs~TargetCardIndex.html)		- Used to get the index of the card in target column.
* [`TargetRowIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs~TargetRowIndex.html) - Used to get the target row index where the card is going to be inserted.
* [`TargetColumnIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEndEventArgs~TargetColumnIndex.html) - Used to get the target column index where the card is going to be inserted.

## DragEnter 

This event is triggered when a card enters into a column while dragging. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs~IsCancel.html)				- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCard.html)				- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumn.html) 		- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCardIndex.html)			- Used to get the index of the card in source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs~CurrentColumn.html)		- Used to get the column upon which the card enters.
* [`CurrentIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs~CurrentIndex.html)			- Used to get the index of the card in current column.
* [`CurrentRowIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs~CurrentRowIndex.html) - Used to get the current index of the card's row.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEnterEventArgs~CurrentColumnIndex.html) - Used to get the current index of the card's column.

## DragLeave 

This event is triggered when a card leaves a column while dragging. The argument contains the following information.

* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCard.html)                - Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumn.html)        - Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCardIndex.html)         - Used to get the index of the card in source column.
* [`LeftColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs~LeftColumn.html)		- Used to get the column from which the card leaves.
* [`PreviousCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs~PreviousCardIndex.html)   -   Used to get the index of the card left.
* [`PreviousRowIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs~PreviousRowIndex.html) - Used to get the previous card's row index while drag enter into next column.
* [`PreviousColumnIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragLeaveEventArgs~PreviousColumnIndex.html) - Used to get the previous card's column index while drag enter into next column.


## DragOver

This event is triggered when a card is dragged to a new index within a column. The argument contains the following information.

* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs~IsCancel.html)			- Used to cancel the drag action.
* [`SelectedCard`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCard.html)			- Used to get the underlying model of the card.
* [`SelectedColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedColumn.html) 	- Used to get the source column of the card.
* [`SelectedCardIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragEventArgs~SelectedCardIndex.html)		- Used to get the index of the card in source column.
* [`CurrentColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs~CurrentColumn.html)	- Used to get the current column which is the drop target for the card.
* [`CurrentIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs~CurrentIndex.html)		- Used to get the new index of the card in current column.
* [`CurrentRowIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs~CurrentRowIndex.html) - Used to get the current index of the card's row.
* [`CurrentColumnIndex`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanDragOverEventArgs~CurrentColumnIndex.html) - Used to get the current index of the card's column.

## ColumnsGenerated 

This event will be fired after the columns are generated automatically. You can access the auto-generated columns using SfKanban.ActualColumns property.


## ColumnGenerated

This event is triggered when a column generated.

* [`Columns`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanColumnsGeneratedEventArgs~Columns.html)  -  used to get the generated columns.
* [`IsCancel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs~IsCancel.html)   -  used to cancel the generated column added to the SfKanban.
* [`CurrentColumn`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfKanban.UWP~Syncfusion.UI.Xaml.Kanban.KanbanColumnGeneratedEventArgs~CurrentColumn.html)   -   used to get the current generated column.
---
layout: post
title: Events | SfGantt | UWP | Syncfusion
description: This section describes the event of the Syncfusion SfGantt in UWP platform such as BeginCellEdit, EndCellEdit, SelectionChanging, SelectionChanged, and more.
platform: uwp
control: SfGantt
documentation: ug
---

# Events of Syncfusion SfGantt

**BeginCellEdit**

Occurs when editing is started in grid cell. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.BeginCellEditEventArgs.html#Syncfusion_UI_Xaml_Gantt_BeginCellEditEventArgs_Item): Gets the editing task item.
* [`MappingName`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.BeginCellEditEventArgs.html#Syncfusion_UI_Xaml_Gantt_BeginCellEditEventArgs_MappingName): Gets the current cell mapping name.
* [`Cancel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.BeginCellEditEventArgs.html#Syncfusion_UI_Xaml_Gantt_BeginCellEditEventArgs_IsCancel): Sets the value to True to cancel the editing.

**EndCellEdit**

Occurs when editing is completed in grid cell. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.EndCellEditEventArgs.html#Syncfusion_UI_Xaml_Gantt_EndCellEditEventArgs_Item): Gets the edited task item.
* [`MappingName`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.EndCellEditEventArgs.html#Syncfusion_UI_Xaml_Gantt_EndCellEditEventArgs_MappingName): Gets the current cell mapping name.
* [`OldItem`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.EndCellEditEventArgs.html#Syncfusion_UI_Xaml_Gantt_EndCellEditEventArgs_OldItem): Gets the old details of the edited task.

**SelectionChanging**

Occurs when a task is selected through mouse or touch interaction. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Gantt_SelectionChangingEventArgs_Item): Gets the selected task item.
* [`Index`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Gantt_SelectionChangingEventArgs_Index):  Gets the selected index.

**SelectionChanged**

Occurs when a task is selected through mouse or touch interaction. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Gantt_SelectionChangedEventArgs_Item): Gets the selected task item.
* [`Index`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Gantt_SelectionChangedEventArgs_Index):  Gets the selected index.

**TaskExpanding**

Occurs when a task is going to be expanded. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskExpandingEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskExpandingEventArgs_Item): Gets the parent task of the expanding item.

**TaskExpanded**

Occurs when a task is expanded. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskExpandedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskExpandedEventArgs_Item): Gets the parent task of the expanded item.

**TaskCollapsing**

Occurs when a task is going to be collapsed. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskCollapsingEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskCollapsingEventArgs_Item): Gets the parent task of the item that is going to be collapsed.

**TaskCollapsed**

Occurs when a task is collapsed. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskCollapsedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskCollapsedEventArgs_Item): Gets the parent task of the collapsed item.

**TaskRelationshipEstablished**

Occurs when the link is established between two tasks through mouse or touch interaction. This event contains the following arguments:

* [`StartTask`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskRelationshipEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskRelationshipEventArgs_StartTask): Gets the start task of the relation.
* [`EndTask`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskRelationshipEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskRelationshipEventArgs_EndTask): Gets the end task of the relation.
* [`Relationship`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskRelationshipEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskRelationshipEventArgs_Relationship): Gets the type of the relation as StartToStart (SS), StartToFinish (SF), FinishToFinish (FF), or FinishToStart (FS).

**TaskBarProgressChanging**

Occurs when dragging the progress bar through mouse or touch interaction. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangingEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarProgressChangingEventArgs_Task): Gets the task when the progress value is being changed.
* [`NewValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangingEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarProgressChangingEventArgs_NewValue): Gets the current value of the progress.

**TaskBarProgressChanged**

Occurs when the taskbar is being dragged. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarProgressChangedEventArgs_Task): Gets the task when the progress value has been changed.
* [`OldValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarProgressChangedEventArgs_OldValue): Gets the previous progress value.
* [`NewValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarProgressChangedEventArgs_NewValue): Gets the current progress value.

**TaskBarDragStart**

Occurs when the taskbar is going to be dragged. This event contains the following argument.

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragStartEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragStartEventArgs_Task): Gets the task that is dragged.

**TaskBarDragDelta**

Occurs when the taskbar is being dragged. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragDeltaEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragDeltaEventArgs_Task): Gets the task that is dragged.
* [`NewStartDate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragDeltaEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragDeltaEventArgs_NewStartDate): Gets the current start date of the task bar.
* [`NewFinishDate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragDeltaEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragDeltaEventArgs_NewFinishDate): Gets the current finish date of the task bar.

**TaskBarDragCompletedEventArgs**

Occurs when the taskbar dragging is completed. This event contains the following argument.

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragCompletedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragCompletedEventArgs_Task): Gets the task that is dragged.
* [`OldStartDate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragCompletedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragCompletedEventArgs_OldStartDate): Gets the start date before dragging.
* [`OldFinishDate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarDragCompletedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarDragCompletedEventArgs_OldFinishDate): Gets the finish date before dragging.

**TaskBarResizeStart**

Occurs when the taskbar resizing is started. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeStartEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeStartEventArgs_Task): Gets the task that is resized.
* [`ResizingDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeStartEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeStartEventArgs_ResizingDirection): Gets the direction in resized task.

**TaskBarResizeDelta**

Occurs when the taskbar is resized. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeDeltaEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeDeltaEventArgs_Task): Gets the task that is resized.
* [`ResizingDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeDeltaEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeDeltaEventArgs_ResizingDirection): Gets the direction in resized task.
* [`ModifiedValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeDeltaEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeDeltaEventArgs_ModifiedValue): Gets the current start date or finish date based on the resizing direction.

**TaskBarResizeCompleted**

Occurs when the taskbar resizing is completed. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeCompletedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeCompletedEventArgs_Task): Gets the task that is resized.
* [`ResizingDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeCompletedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeCompletedEventArgs_ResizingDirection): Gets the direction in resized task.
* [`OldValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskBarResizeCompletedEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskBarResizeCompletedEventArgs_OldValue): Gets the value before resizing the task.


**TaskGenerated**

Occurs when a task is generated in the view. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskEventArgs.html#Syncfusion_UI_Xaml_Gantt_TaskEventArgs_Task): Gets the task that has been added.

## See also

[How to disable editing for a specific cell in gantt](https://www.syncfusion.com/kb/7724/how-to-disable-editing-for-a-specific-cell-in-gantt)
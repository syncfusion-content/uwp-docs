---
layout: post
title: Events
platform: uwp
control: SfGantt
documentation: ug
---

# Events

**BeginCellEdit**

Occurs when editing is started in grid cell. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.BeginCellEditEventArgs~Item.html): Gets the editing task item.
* [`MappingName`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.BeginCellEditEventArgs~MappingName.html): Gets the current cell mapping name.
* [`Cancel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.BeginCellEditEventArgs~IsCancel.html): Sets the value to True to cancel the editing.

**EndCellEdit**

Occurs when editing is completed in grid cell. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.EndCellEditEventArgs~Item.html): Gets the edited task item.
* [`MappingName`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.EndCellEditEventArgs~MappingName.html): Gets the current cell mapping name.
* [`OldItem`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.EndCellEditEventArgs~OldItem.html): Gets the old value of the edited task.

**SelectionChanging**

Occurs when a task is selected through mouse or touch interaction. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SelectionChangingEventArgs~Item.html): Gets the selected task item.
* [`Index`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SelectionChangingEventArgs~Index.html):  Gets the selected index.

**SelectionChanged**

Occurs when a task is selected through mouse or touch interaction. This event contains the following arguments:

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SelectionChangedEventArgs~Item.html): Gets the selected task item.
* [`Index`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SelectionChangedEventArgs~Index.html):  Gets the selected index.

**TaskExpanding**

Occurs when a task is going to be expanded. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskExpandingEventArgs~Item.html): Gets the parent task of the expanding item.

**TaskExpanded**

Occurs when a task is expanded. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskExpandedEventArgs~Item.html): Gets the parent task of the expanded item.

**TaskCollapsing**

Occurs when a task is going to be collapsed. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskCollapsingEventArgs~Item.html): Gets the parent task of the item that is going to be collapsed.

**TaskCollapsed**

Occurs when a task is collapsed. This event contains the following argument.

* [`Item`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskCollapsedEventArgs~Item.html): Gets the parent task of the collapsed item.

**TaskRelationshipEstablished**

Occurs when the link is established between two tasks through mouse or touch interaction. This event contains the following arguments:

* [`StartTask`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskRelationshipEventArgs~StartTask.html): Gets the start task of the relation.
* [`EndTask`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskRelationshipEventArgs~EndTask.html): Gets the end task of the relation.
* [`Relationship`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskRelationshipEventArgs~Relationship.html): Gets the type of the relation as StartToStart (SS), StartToFinish (SF), FinishToFinish (FF), or FinishToStart (FS).

**TaskBarProgressChanging**

Occurs when dragging the progress bar through mouse or touch interaction. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangingEventArgs~Task.html): Gets the task when the progress value is being changed.
* [`NewValue`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangingEventArgs~NewValue.html): Gets the current value of the progress.

**TaskBarProgressChanged**

Occurs when the taskbar is being dragged. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangedEventArgs~Task.html): Gets the task when the progress value has been changed.
* [`OldValue`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangedEventArgs~OldValue.html): Gets the previous progress value.
* [`NewValue`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarProgressChangedEventArgs~NewValue.html): Gets the current progress value.

**TaskBarDragStart**

Occurs when the taskbar is going to be dragged. This event contains the following argument.

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragStartEventArgs~Task.html): Gets the task that is dragged.

**TaskBarDragDelta**

Occurs when the taskbar is being dragged. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragDeltaEventArgs~Task.html): Gets the task that is dragged.
* [`NewStartDate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragDeltaEventArgs~NewStartDate.html): Gets the current start date of the task bar.
* [`NewFinishDate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragDeltaEventArgs~NewFinishDate.html): Gets the current finish date of the task bar.

**TaskBarDragCompletedEventArgs**

Occurs when the taskbar dragging is completed. This event contains the following argument.

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragCompletedEventArgs~Task.html): Gets the task that is dragged.
* [`OldStartDate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragCompletedEventArgs~OldStartDate.html): Gets the start date before dragging.
* [`OldFinishDate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarDragCompletedEventArgs~OldFinishDate.html): Gets the finish date before dragging.

**TaskBarResizeStart**

Occurs when the taskbar resizing is started. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeStartEventArgs~Task.html): Gets the task that is resized.
* [`ResizingDirection`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeStartEventArgs~ResizingDirection.html): Gets the direction in resized task.

**TaskBarResizeDelta**

Occurs when the taskbar is resized. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeDeltaEventArgs~Task.html): Gets the task that is resized.
* [`ResizingDirection`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeDeltaEventArgs~ResizingDirection.html): Gets the direction in resized task.
* [`ModifiedValue`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeDeltaEventArgs~ModifiedValue.html): Gets the current start date or finish date based on the resizing direction.

**TaskBarResizeCompleted**

Occurs when the taskbar resizing is completed. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeCompletedEventArgs~Task.html): Gets the task that is resized.
* [`ResizingDirection`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeCompletedEventArgs~ResizingDirection.html): Gets the direction in resized task.
* [`OldValue`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskBarResizeCompletedEventArgs~OldValue.html): Gets the value before resizing the task.


**TaskGenerated**

Occurs when task is generated in the view. This event contains the following arguments:

* [`Task`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.TaskEventArgs~Task.html): Gets the task which is added.
# Events

**BeginCellEdit**

Occurs when the editing is started in the grid cell. The arguments contain the following information.

* Item - Gets the current cell editing item.
* MappingName – Gets the current cell mapping name.
* Cancel – Sets the value as True to cancel the editing.

**EndCellEdit**

Occurs when the editing is completed in the grid cell. The arguments contain the following information.

* Item - Gets the item value which is edited.
* MappingName – Gets the current cell mapping name.

**SelectionChanging**

Occurs when the task selection is changing through mouse or touch interaction. The arguments contain the following information.

* Item - Gets the item value which is selected.
* Index -  Gets the selected index.

**SelectionChanged**

Occurs when the task is selected through mouse or touch interaction. . The arguments contain the following information.

* Item - Gets the item value which is selected.
* Index -  Gets the selected index.

**TaskExpanding**

Occurs when the task is going to be expanded. The arguments contain the following information.

* Item - Gets the parent task of the expanding item.

**TaskExpanded**

Occurs when the task is expanded.  The arguments contain the following information.****

* Item - Gets the parent task of the item that is expanded.

**TaskCollapsing**

Occurs when the task is going to be collapsed. The arguments contain the following information.

* Item - Gets the parent task of the item that is going to be collapsed.

**TaskCollapsed**

Occurs when the task is collapsed. The arguments contain the following information.****

* Item - Gets the parent task of the item that is collapsed.

**TaskRelationshipEstablished**

Occurs when the link is established between two tasks through mouse or touch interaction. The arguments contain the following information.****

* StartTask - Gets the start task of the relation.
* EndTask – Gets the end task of the relation.
* Relationship – Gets the type of the relation as StartToStart(SS), StartToFinish(SF), FinishToFinish(FF) or FinishToStart(FS).

**TaskBarProgressChanging**

Occurs while dragging the progress bar through mouse or touch interaction. The arguments contain the following information.****

* Task - Gets the task in which the progress value is changing.
* NewValue - Gets the current value of the progress.

**TaskBarProgressChanged**

Occurs after progress bar dragging is completed through mouse or touch interaction. The arguments contain the following information.****

* Task - Gets the task in which the progress value is changed.
* OldValue – Gets the previous progress value.
* NewValue - Gets the current value of the progress.

**TaskBarDragStart**

Occurs when the taskbar dragging is started. The arguments contain the following information.****

* Task - Gets the task which is dragged.

**TaskBarDragDelta**

Occurs when the taskbar dragging is performed. The arguments contain the following information.****

* Task - Gets the task which is dragged.
* NewStartDate - Gets the current start date of the task bar.
* NewFinishDate - Gets the current finish date of the task bar.

**TaskBarDragCompletedEventArgs**

Occurs when the taskbar dragging is completed. The arguments contain the following information.****

* Task - Gets the task which is dragged.

**TaskBarResizeStart**

Occurs when the taskbar resizing is started. The arguments contain the following information.****

* Task - Gets the task which is resized.
* ResizingDirection - Gets the direction in which task is resized.

**TaskBarResizeDelta**

Occurs when the taskbar is resized. The arguments contain the following information.****

* Task - Gets the task which is resized.
* ResizingDirection - Gets the direction in which task is resized.
* ModifiedValue – Gets the current start date or finish date based on the resizing direction.

**TaskBarResizeCompleted**

Occurs when the taskbar resizing is completed. The arguments contain the following information.****

* Task - Gets the task which is resized.
* ResizingDirection - Gets the direction in which task is resized.


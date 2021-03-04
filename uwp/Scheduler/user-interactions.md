---
layout: post
title: User Interactions in Syncfusion SfSchedule control for UWP
description: How to perform the drag and drop operations, resize the appointments and Dispose the resources in Schedule control.
platform: uwp
control: SfSchedule
documentation: ug
---

# User Interactions in UWP Scheduler (SfSchedule)

## Change the default context menu
When you tap the schedule or appointment, our built-in context menu will be opened and triggered the [ContextMenuOpening](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.ContextMenuOpeningEventArgs.html) event. You can create your own context menu by setting `e.Cancel` to true in the `ContextMenuOpening` event. It will avoid to open the default context menu. 


{% highlight c# %} 

        schedule.ContextMenuOpening += Schedule_ContextMenuOpening;
        private void Schedule_ContextMenuOpening(object sender,ContextMenuOpeningEventArgs e)
        {
            e.Cancel = true;
        }

{% endhighlight %}   


## Change the default editor
[AppointmentEditorOpening](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentEditorOpeningEventArgs.html) event occurs when opening the appointment editor by selecting edit option in the context menu or double tapping the appointment. You can create your own appointment editor by setting `e.Cancel` to true in the `AppointmentEditorOpening` event. It will avoid to open the default editor. 

{% highlight c# %} 

      schedule.AppointmentEditorOpening += Schedule_AppointmentEditorOpening;
      private void Schedule_AppointmentEditorOpening(object sender,AppointmentEditorOpeningEventArgs e)
        {
            e.Cancel = true;
        }

{% endhighlight %}   


## Drag-Drop
You can use the Context menu to easily drag and drop the appointments from one timeslot to another timeslot by selecting the `Resize` option available in Context menu item.

### Appointment Start Dragging

The event will be triggered when appointment is started to dragging. The [AppointmentStartDraggingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentStartDraggingEventArgs.html) contains the following properties.

*	**Appointment**- Gets the dragging appointment, this argument is of type object.
*	**Cancel**- Set this Boolean property to True to disable the drag and drop option.


{% highlight c# %} 

      schedule.AppointmentStartDragging += Schedule_AppointmentStartDragging;
      private void Schedule_AppointmentStartDragging(object sender,Syncfusion.UI.Xaml.Schedule.AppointmentStartDraggingEventArgs e)
        {
        
        }

{% endhighlight %}   


### Appointment End Dragging

The event will be triggered when appointment is dropping. The [AppointmentEndDraggingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentEndDraggingEventArgs.html) contains the following properties.

*	**Appointment**- Gets the dragging appointment, this argument is of type object.
*	**From** – Get the appointment initial dragging time.
*	**Resources** - gets the current resource of the appointment.
*	**To** – Gets the dropping time.
*	**Cancel**- Set this Boolean property to True to disable the drag and drop option.


{% highlight c# %} 

        schedule.AppointmentEndDragging += Schedule_AppointmentEndDragging;
        private void Schedule_AppointmentEndDragging(object sender,AppointmentEndDraggingEventArgs e)
        {
        
        }

{% endhighlight %}   


### Appointment Dragging

The event will be triggered when drag and drop the appointment. The [AppointmentDraggingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentDraggingEventArgs.html) contains the following properties.

*	**Appointment**- Gets the dragging appointment, this argument is of type object.
*	**From** – Get the appointment initial dragging time.
*	**Resources** - gets the current resource of the appointment.
*	**RefreshAppointment** - Set True to refresh the appointment position with current dragging time.
*	**To** – Gets the dropping time.
*	**Cancel**- Set this Boolean property to True to disable the drag and drop option.


{% highlight c# %} 

         schedule.AppointmentDragging += Schedule_AppointmentDragging;
         private void Schedule_AppointmentDragging(object sender,AppointmentDraggingEventArgs e)
        {
       
        }

{% endhighlight %}   


## Resizing
You can use the Context menu to resizing a Selected Appointment as per required start and end time of schedule in an interactive manner by selecting the `Resize` option available in Context menu item.

### Appointment Start Resizing

The event will be triggered when appointment is started to resizing. The [AppointmentStartResizingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentStartResizingEventArgs.html) contains the following properties.

*	**Appointment**- Gets the resizing appointment, this argument is of type object.
*	**Cancel**- Set this Boolean property to True to disable the resize option.


{% highlight c# %} 

         schedule.AppointmentStartResizing += Schedule_AppointmentStartResizing;
         private void Schedule_AppointmentStartResizing(object sender,AppointmentStartResizingEventArgs e)
        {
          
        }

{% endhighlight %}   


### Appointment End Resizing

The event will be triggered when finishing the appointment resizing. The [AppointmentEndResizingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentEndResizingEventArgs.html) contains the following properties.

*	**Appointment**- Gets the resizing appointment, this argument is of type object.
*	**From** - Get the appointment start resizing time.
*	**ResizeType** - gets the ResizeType.
*	**To** - Gets the end resizing time.
*	**Cancel** - Set this Boolean property to True to disable the drag and drop option.


{% highlight c# %} 

          schedule.AppointmentEndResizing += Schedule_AppointmentEndResizing;
          private void Schedule_AppointmentEndResizing(object sender,AppointmentEndResizingEventArgs e)
        {
          
        }

{% endhighlight %}   


### Appointment Resizing

The event will be triggered when resizing the appointment. The [AppointmentResizingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.AppointmentResizingEventArgs.html) contains the following properties.

*	**Appointment**- Gets the resizing appointment, this argument is of type object.
*	**From** - Get the appointment start dragging time.
*	**ResizeType**- gets the `ResizeType`.
*	**RefreshAppointment** - Set True to refresh the appointment position with current resizing time.
*	**To** - Gets the end resizing time.

{% highlight c# %} 

           schedule.AppointmentResizing += Schedule_AppointmentResizing;
           private void Schedule_AppointmentResizing(object sender,AppointmentResizingEventArgs e)
        {
          
        }

{% endhighlight %}

---
layout: post
title: Events | SfSchedule | uwp | Syncfusion
description: Events
platform: uwp
control: SfSchedule
documentation: ug
---

# Events

Event can be used for handle various operation such as Appointment Editor Opening and Closed or while opening or closing the Context Menu and events ItemsSourceChanged, ScheduleTapped, ScheduleDoubleTapped are used for customization purposes.

## Appointment Editor Events

### AppointmentEditorOpening

Occurs when the appointment editor is opening. 

The **AppointmentEditorOpening** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. An **AppointmentEditorOpeningEventArgs** is a class. Via the **AppointmentEditorOpeningEventArgs** you can access the following properties:
   * **Appointment**- gets the appointment, this argument is of type object.
   * **StartTime**- gets the appointment start time.
   * **Action**- gets the Editor action such as Add or Edit or Delete.
   * **Cancel**- set this Boolean property to **True** to cancelling the event.
 
### AppointmentEditorClosed

Occurs when the appointment editor is closed.

The **AppointmentEditorClosed** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. An **AppointmentEditorClosedEventArgs** a class. Via the **AppointmentEditorClosedEventArgs** you can access the following properties:
   * **OriginalAppointment** **-** gets the Original appointment, this argument is of type object.
   * **EditedAppointment** **-** gets the edited appointment, this argument is of type object.
   * **IsNew** **–** set this Boolean property to **True**, when you Updating or Setting new appointment property.
    * **Action** **–** gets the Editor action such as Add or Edit or Delete.

## Appointment Collection Changed Event

Occurs when the appointment collection will be changed. The **AppointmentCollectionChanged** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. Via the **NotifyCollectionChangedEventArgs** gets the collection are affected by the change.

## Context Menu Events

### ContextMenuOpening

Occurs when opening Context Menu. 

The **ContextMenuOpening** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. A **ContextMenuOpeningEventArgs** is a class. Via the **ContextMenuOpeningEventArgs** you can access the following properties:
    * **Appointment** - gets the appointment, this argument is of type object.
    * **CurrentSelectedDate** **-** gets the appointment current selected Date.
    * **CurrentEventArgs** **–** gets the Editor action such as Add or Edit or Delete.
    * **Cancel****-** set this Boolean property to **True** to disable the context menu.

### ContextMenuClosed

Occurs when the Context Menu closed. 

The **ContextMenuClosedevent** handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. A **ContextMenuClosedEventArgs** is a class. 

## Schedule Tapped Events

### ScheduleTapped

Occurs when tapping the schedule.The **ScheduleTapped** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **ScheduleTappedEventArgs** is a class. Via the **ScheduleTappedEventArgs** you can access the following properties:
    * **Appointment**- gets the appointment, this argument is of type object.
    * **SelectedDate** **-** gets the appointment current selected Date.

### ScheduleDoubleTapped

Occurs when double tapping the schedule.

The **ScheduleDoubleTapped** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **ScheduleTappedEventArgs** is a class. Via the **ScheduleTappedEventArgs** you can access the following properties:
    * **Appointment**- gets the appointment, this argument is of type object.
    * **SelectedDate**- gets the appointment current selected Date.
    
## Appointment Dragging Events

### AppointmentDragging

Occurs when dragging the appointment.

The **AppointmentDragging** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **AppointmentDraggingEventArgs** is a class. Via the **AppointmentDraggingEventArgs** you can access the following properties:
    * Appointment - gets appointment to be dragged, this argument is of type object.
    * From – gets start time of appointment to be dragged, this argument is of type **DateTime**.
    * To - gets end time of appointment to be dropped, this argument is of type DateTime.
    * RefreshAppointment - This argument is of type bool.

### AppointmentStartDragging

Occurs when start to drag selected appointment.

The **AppointmentStartDragging** event handler receives two arguments:
 1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
 2. **AppointmentStartDraggingEventArgs** is a class. Via the **AppointmentStartDraggingEventArgs** you can access the following properties:
* Appointment - gets appointment to be dragged, this argument is of type object.

### AppointmentEndDragging

Occurs when dropped selected the appointment.

The **AppointmentEndDragging** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **AppointmentEndDraggingEventArgs** is a class. Via the **AppointmentEndDraggingEventArgs** you can access the following properties:
    * Appointment - gets appointment to be dragged, this argument is of type object.
    * From – gets start time of appointment to be dragged, this argument is of type **DateTime**.
    * To - gets end time of appointment to be dropped, this argument is of type DateTime.

## ScheduleType Changing Event

Occurs when changing the ScheduleType. 

The **ScheduleTypeChanging** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **ScheduleTypeChangingEventArgs** is a class. Via the **ScheduleTypeChangingEventArgs** you can access the following properties:
    * **OldValue** - gets old value of ScheduleType, this argument is of type ScheduleType.
    * **NewValue** - gets new value of ScheduleType, this argument is of type ScheduleType.
    
## VisibleDates Changing Event

Occurs schedule Visible Dates will be changed.

The **VisibleDatesChanging** event handler receives two arguments:
1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **VisibleDatesChangingEventArgs** is a class. Via the **VisibleDatesChangingEventArgs** you can access the following properties:
    * **OldValue** - gets old value schedule visible dates.
    * **NewValue** - gets new value of Schedule visible dates

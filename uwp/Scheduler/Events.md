---
layout: post
title: Events | SfSchedule | uwp | Syncfusion
description: Events
platform: uwp
control: SfSchedule
documentation: ug
---

# Events

Events can be used to handle various operations such as Appointment Editor Opening and Closed, or while opening or closing the Context Menu. The events ItemsSourceChanged, ScheduleTapped, and ScheduleDoubleTapped are used for customization purposes.

## Appointment Editor Events

### AppointmentEditorOpening

Occurs when the appointment editor is opening. The **AppointmentEditorOpening** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. An **AppointmentEditorOpeningEventArgs** is a class. Via the **AppointmentEditorOpeningEventArgs** you can access the following properties:

   * **Appointment** - gets the appointment, this argument is of type object.
   * **StartTime** - gets the appointment start time.
   * **Action** - gets the Editor action such as Add or Edit or Delete.
   * **Cancel** - set this Boolean property to **True** to cancel the event.
 
### AppointmentEditorClosed

Occurs when the appointment editor is closed. The **AppointmentEditorClosed** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. An **AppointmentEditorClosedEventArgs** is a class. Via the **AppointmentEditorClosedEventArgs** you can access the following properties:

   * **OriginalAppointment** **-** gets the original appointment, this argument is of type object.
   * **EditedAppointment** **-** gets the edited appointment, this argument is of type object.
   * **IsNew** **–** set this Boolean property to **True** when updating or setting a new appointment property.
    * **Action** **–** gets the Editor action such as Add or Edit or Delete.

## Appointment Collection Changed Event

Occurs when the appointment collection is changed. The **AppointmentCollectionChanged** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. Via the **NotifyCollectionChangedEventArgs** gets the collection affected by the change.

## Context Menu Events

### ContextMenuOpening

Occurs when opening the Context Menu. The **ContextMenuOpening** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. A **ContextMenuOpeningEventArgs** is a class. Via the **ContextMenuOpeningEventArgs** you can access the following properties:

    * **Appointment** - gets the appointment, this argument is of type object.
    * **CurrentSelectedDate** **-** gets the appointment's current selected Date.
    * **CurrentEventArgs** **–** gets the Editor action such as Add or Edit or Delete.
    * **Cancel****-** set this Boolean property to **True** to disable the context menu.

### ContextMenuClosed

Occurs when the Context Menu is closed. The **ContextMenuClosedEvent** handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. A **ContextMenuClosedEventArgs** is a class. 

## Schedule Tapped Events

### ScheduleTapped

Occurs when tapping the schedule. The **ScheduleTapped** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **ScheduleTappedEventArgs** is a class. Via the **ScheduleTappedEventArgs** you can access the following properties:

    * **Appointment** - gets the appointment, this argument is of type object.
    * **SelectedDate** **-** gets the appointment's current selected Date.

### ScheduleDoubleTapped

Occurs when double tapping the schedule. The **ScheduleDoubleTapped** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **ScheduleTappedEventArgs** is a class. Via the **ScheduleTappedEventArgs** you can access the following properties:

    * **Appointment** - gets the appointment, this argument is of type object.
    * **SelectedDate** - gets the appointment's current selected Date.
    
## ScheduleType Changing Event

Occurs when changing the ScheduleType. The **ScheduleTypeChanging** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **ScheduleTypeChangingEventArgs** is a class. Via the **ScheduleTypeChangingEventArgs** you can access the following properties:

    * **OldValue** - gets the old value of ScheduleType, this argument is of type ScheduleType.
    * **NewValue** - gets the new value of ScheduleType, this argument is of type ScheduleType.
    
## VisibleDates Changing Event

Occurs when the schedule Visible Dates are changed. The **VisibleDatesChanging** event handler receives two arguments:

1. The **sender** argument contains the **SfSchedule**. This argument is of type object, but can be cast to the **SfSchedule** type.
2. **VisibleDatesChangingEventArgs** is a class. Via the **VisibleDatesChangingEventArgs** you can access the following properties:

    * **OldValue** - gets the old value of schedule visible dates.
    * **NewValue** - gets the new value of schedule visible dates.

---
layout: post
title: Custom Summary | SfPivotClient | UWP | Syncfusion
description: Custom Summary
platform: UWP
control: SfPivotClient
documentation: ug
---

# Custom Summary

SfPivotClient provides support to change the summary type of existing calculation items to 'Custom' at run time using the custom summary dialog.

**Defining a custom summary**

* To change the summary type as custom summary, click *Custom Summary* ![](Custom-Summary_images/Custom-summary-icon.png) in the client toolbar. The custom summary dialog will be opened as follows:

![](Custom-Summary_images/Custom-Summary_image1.png)

* The existing pivot calculation name can be selected from the **Field Name** drop-down list.

* One or more custom summary types can be kept in the **Summary** drop-down list. You can select any one of the CustomSummaryBase from this collection.

* The format for the required field can be defined using the **Format String** field. For example, 'C' for Currency, 'P' for Percentage, and 'N' for Numeric.

![](Custom-Summary_images/Custom-Summary_image2.png)

* Then click **OK** to populate the values in the SfPivotClient.

![](Custom-Summary_images/Custom-Summary_image3.png)
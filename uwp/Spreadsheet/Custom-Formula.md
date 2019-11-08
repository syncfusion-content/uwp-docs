---
layout: post
title: Custom Formula in SfSpreadsheet
description: How to add custom formulas in SfSpreadsheet
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Custom Formula

SfSpreadsheet allows you to add custom formulas into its function library. You can add the custom formula into the SfSpreadsheet by using the `AddFunction` method of `FormulaEngine`,

{% tabs %}
{% highlight c# %}

spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{

  foreach (var grid in args.GridCollection)
    AddCustomFormula(grid); 
  
  //Computing the formula at runtime
   var range = spreadsheetControl.ActiveSheet.Range["B2"];
   spreadsheetControl.ActiveGrid.SetCellValue(range,"=FindLength(Sample)");
}  

private void AddCustomFormula(SpreadsheetGrid grid)
{

  // Add a formula named FindLength to the Library.
   grid.FormulaEngine.AddFunction("FindLength", new FormulaEngine.LibraryFunction(ComputeLength));      
}    

//Implementation of formula
    
public string ComputeLength(string range)
{

  //Used to calculate the length of the string
    return range.Length.ToString();
}

{% endhighlight %}
{% endtabs %}
---
layout: post
title: Context Menu Suggestion in UWP SfSpellChecker | Syncfusion®
description: The Context Menu Suggestion in SfSpellChecker offers Microsoft Office-like context menu to correct spell errors using listed suggestions.
platform: uwp
control: SfSpellChecker
documentation: ug
---

# Context Menu Suggestion in UWP Spell Checker

`UWP Spell Checker` offers Microsoft Office application like context menu suggestions and helps to correct spell errors by choosing correct option from the listed suggestions.

The following steps helps to add context menu suggestion in the TextBox control.

1) Create a UWP project in Visual Studio.

2) Create a class which inherits `IEditorProperties` interface of `UWP Spell Checker` and Initialize all the methods and properties.

{% tabs %}

{% highlight C# %}


public class TextSpellEditor:IEditorProperties

{

TextBox textbox;

public TextSpellEditor(Control control)

{

ControlToCheck = control;

}

public Control ControlToCheck

{

get

{

return textbox;

}

set

{

textbox = value as TextBox;

}

}

public string SelectedText

{

get

{

return textbox.SelectedText;

}

set

{

textbox.SelectedText = value;

}

}

public string Text

{

get

{

return textbox.Text;

}

set

{

textbox.Text = value;

}

}

public void Select(int selectionStart, int selectionLength)

{

textbox.Select(selectionStart, selectionLength);

}

public bool HasMoreTextToCheck()

{

return false;

}

public void Focus()

{

textbox.Focus(Windows.UI.Xaml.FocusState.Pointer);

}

public void UpdateTextField()

{

throw new NotImplementedException();

}

}

}


{% endhighlight %}

{% endtabs %}

3) Initiate `PerformSpellCheckUsingContextMenu` method by passing `IEditorProperties` interface argument.

{% tabs %}

{% highlight C# %}


TextSpellEditor TextEditor = new TextSpellEditor(Textboxx);

SpellEditor = TextEditor;  

SpellChecker.PerformSpellCheckUsingContextMenu(SpellEditor);

{% endhighlight %}

{% endtabs %}

![Suggestion using context menu](context-menu-suggestion-images/context-menu-suggestion.jpeg)



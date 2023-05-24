---
layout: post
title: HubTileBase in UWP Hub Tile control | Syncfusion
description: Learn here all about HubTileBase support in Syncfusion UWP Hub Tile (HubTiles) control and more.
platform: uwp
control: HubTileBase
documentation: ug
---

# HubTileBase in UWP Hub Tile (HubTiles)

`HubTileBase` is the base of all the four tiles under Syncfusion.SfHubTile.UWP assembly. It provides some basic functionalities that are found in the live tiles of windows 8 start screen. The following support are common and applicable to all the tiles such as `SfHubTile`, `SfMosaicTile`,
 `SfSplitMosaicTile` and `SfPulsingTile`.

## Dealing with flip effect

On pressing, the tile is flipped based on the point of press. This behavior can be customized using `RotationDepth`, `TilePressDuration` and `ScaleDepth` properties.

### Rotation Depth

Rotation depth can be used to customize the depth of the flip effect while pressing the edges of the tile.

{% tabs %}

{% highlight XAML %}

<notification:SfHubTile x:Name="hubTile" Foreground="White" 

RotationDepth="40"

Title="This is title area."

Header="HubTile" /> 
   
{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

hubTile.RotationDepth = 40.0;

{% endhighlight %}

{% highlight VB %}

hubTile.RotationDepth = 40.0

{% endhighlight %}

{% endtabs %}

![Hubtile slide at right side](hubtilebase-images/hubtilebase-img1.jpeg)


### Scale Depth

Scale depth can be used to customize the depth of the flip effect while pressing the center of tile.

{% tabs %}

{% highlight XAML %}

<notification:SfHubTile x:Name="hubTile" Foreground="White" 

ScaleDepth="1.2

Title="This is title area."

Header="HubTile" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

hubTile.ScaleDepth = 1.2;

{% endhighlight %}

{% highlight VB %}

hubTile.ScaleDepth = 1.2

{% endhighlight %}

{% endtabs %}

![Hubtile Zoom-out by scaling](hubtilebase-images/hubtilebase-img2.jpeg)

### Tile press duration

Tile press duration is the time taken for the tile press animation to take place. Tile press animation happens separately for pointer down and pointer up. It can be set using `TilePressDuration` property in `HubTileBase`. 

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile x:Name="pulsingTile" TilePressDuration="0:0:5"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

pulsingTile.TilePressDuration = TimeSpan.FromSeconds(5);

{% endhighlight %}

{% highlight VB %}

pulsingTile.TilePressDuration = TimeSpan.FromSeconds(5)

{% endhighlight %}

{% endtabs %}

### Disabling flip effect 

The flip effect can be enabled or disabled using `OverrideDefaultStates` property. To disable this press behavior, set the `OverrideDefaultStates` property to `true`. 

{% tabs %}

{% highlight XAML %}

<notification:SfHubTile x:Name="hubTile" Header="HubTile" OverrideDefaultStates="true"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

hubTile.OverrideDefaultStates = true;

{% endhighlight %}

{% highlight VB %}

hubTile.OverrideDefaultStates = True

{% endhighlight %}

{% endtabs %}

## Pausing and resuming animations 

A tile is said to be frozen when the animation pauses until it is resumed. All the hub tiles can be frozen and unfrozen using `IsFrozen` property from HubTileBase class. 

### IsFrozen 

`IsFrozen` property is used to freeze and unfreeze a single tile i.e., freezing the animation. By default, `IsFrozen` is false and set to true for freezing the tile. Here is an example code for freezing `SfHubTile`.

{% tabs %}

{% highlight XAML %}

<notification:SfHubTile x:Name="hubTile" Interval="0:0:1" IsFrozen="true"

ImageSource="Assets/New Mail.png" 

Title="This is title area."

Header="HubTile">

<notification:SfHubTile.HubTileTransitions>

<transitions:RotateTransition/>

<transitions:SlideTransition/>

<transitions:FadeTransition/>

</notification:SfHubTile.HubTileTransitions>

</notification:SfHubTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

hubTile.IsFrozen = true;

{% endhighlight %}

{% highlight VB %}

hubTile.IsFrozen = True

{% endhighlight %}

{% endtabs %}

### Group name

Several hub tiles can be grouped using the property `GroupName`. A group of tiles can be frozen by a single line of code using the `GroupName`. 

{% tabs %}

{% highlight XAML %}

<notification:SfHubTile x:Name="hubTileOne" GroupName="Applications"

ImageSource="Assets/New Mail.png"

Title="This is title area."

Header="HubTile"/>

<notification:SfHubTile x:Name="hubTileTwo" GroupName="Applications"

ImageSource="Assets/New Mail.png"

Title="This is title area."

Header="HubTile"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

hubTileOne.GroupName="Applications";

hubTileTwo.GroupName="Applications";

{% endhighlight %}

{% highlight VB %}

hubTileOne.GroupName="Applications"

hubTileTwo.GroupName="Applications"

{% endhighlight %}

{% endtabs %}

## HubTileService

The helper class `HubTileService` provides a way to freeze and unfreeze the animation in single or a group of tiles.

### Pausing and resuming transitions 

A tile is said to be frozen when the animation pauses as it is and resumes after unfreezing. All the hub tiles can be frozen and unfrozen using `Freeze` and `Unfreeze` methods in `HubTileService` class. 

**Freezing the tile**

`Freeze` method is used to freeze a single or a group of tiles. There are two definitions for `Freeze` method. They are

* Void Freeze(HubTileBase tile) – used to freeze a tile

{% tabs %}

{% highlight C# %}

HubTileService.Freeze(hubTile);

{% endhighlight %}

{% highlight VB %}

HubTileService.Freeze(hubTile)

{% endhighlight %}

{% endtabs %}

* Void Freeze(string groupname) – used to freeze a group of tile

{% tabs %}

{% highlight C# %}

HubTileService.Freeze("Applications");

{% endhighlight %}

{% highlight VB %}

HubTileService.Freeze("Applications")

{% endhighlight %}

{% endtabs %}

**Unfreezing the tile**

`UnFreeze` method is used to unfreeze a single or a group of tiles. There are two definitions for `UnFreeze` method. They are

* Void UnFreeze(HubTileBase tile) – used to unfreeze a tile

{% tabs %}

{% highlight C# %}

HubTileService.UnFreeze(hubTile);

{% endhighlight %}

{% highlight VB %}

HubTileService.UnFreeze(hubTile)

{% endhighlight %}

{% endtabs %}

* Void UnFreeze(string groupname) – used to unfreeze a group of tile


{% tabs %}

{% highlight C# %}

HubTileService.UnFreeze("Applications");

{% endhighlight %}

{% highlight VB %}

HubTileService.UnFreeze("Applications")

{% endhighlight %}

{% endtabs %}

## Press notification

When tile is pressed, it is notified by `Click` event. It also provides Command and CommandParameter support.

### Click event

When a tile is pressed `Click` event is fired.

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile x:Name="pulsingTile" Click="pulsingTile_Click"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void pulsingTile_Click(object sender, RoutedEventArgs e)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub pulsingTile_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

### Command and CommandParameter

`Command` and `CommandParameter` properties are used instead of `Click` event in MVVM pattern. 

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile Command="{Binding Command}" CommandParameter="Hello"/> 

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

public MainPage()

{

this.InitializeComponent();

command= new Syncfusion.UI.Xaml.Utils.DelegateCommand(MyCommand);

DataContext = this;

}

private ICommand command;

public ICommand Command

{

get { return command; }

set { command = value;}

}

public async void MyCommand(object parameter)

{

MessageDialog dialog = new MessageDialog(parameter.ToString());

await dialog.ShowAsync();

}

{% endhighlight %}

{% highlight VB %}

Public Sub New()


Me.InitializeComponent()

command_Renamed= New Syncfusion.UI.Xaml.Utils.DelegateCommand(AddressOf MyCommand)

DataContext = Me

End Sub


Private command_Renamed As ICommand

Public Property Command() As ICommand


Get
	Return command_Renamed
End Get

Set(ByVal value As ICommand)
	command_Renamed = value
End Set

End Property

Public Async Sub MyCommand(ByVal parameter As Object)


Dim dialog As New MessageDialog(parameter.ToString())

Await dialog.ShowAsync()

End Sub

{% endhighlight %}

{% endtabs %}

## Appearance and Styling

### AccentBrush

`AccentBrush` property is used to decorate the hot spots of control with a solid color.

{% tabs %}

{% highlight XAML %}

<notification:SfHubTile x:Name="hubTile" AccentBrush="CornflowerBlue"

ImageSource="Assets/New Mail.png" 

Title="This is title area."

Header="HubTile">

</notification:SfHubTile>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

hubTile.AccentBrush = new SolidColorBrush(Windows.UI.Colors.CornflowerBlue);

{% endhighlight %}

{% highlight VB %}

hubTile.AccentBrush = New SolidColorBrush(Windows.UI.Colors.CornflowerBlue)

{% endhighlight %}

{% endtabs %}

![Hubtile background customized](hubtilebase-images/hubtilebase-img3.jpeg)


### TitleStyle

Title text is customized with `TitleStyle` property. It can be set as follows:

{% tabs %}

{% highlight XAML %}

<notification:SfPulsingTile Title="Pulsing tile">

<notification:SfPulsingTile.TitleStyle>

<Style TargetType="ContentControl">

<Setter Property="Foreground" Value="White"/>                            

</Style>

</notification:SfPulsingTile.TitleStyle>

</notification:SfPulsingTile>

{% endhighlight %}

{% endtabs %}

![Hubtile title drawn in white color](hubtilebase-images/hubtilebase-img5.jpeg)



---
layout: post
title: Getting Started with UWP Diagram control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Diagram (SfDiagram) control, its elements and more.
platform: uwp
control: SfDiagram
documentation: ug
---

# Getting Started with UWP Diagram (SfDiagram)

The following section helps you to build your application with SfDiagram. 

## Creating the project

Create new UWP project using Visual Studio. For more [details](https://learn.microsoft.com/en-us/windows/uwp/get-started/create-a-hello-world-app-xaml-universal#step-1-create-a-new-project-in-visual-studio).
 
## Assembly Reference

### Adding control via Designer

SfDiagram control can be added to the application by dragging it from Toolbox and dropping it in Designer view. The required assembly references will be added automatically.

![Designer](Getting-Started_images\Diagram.png)

### Adding control manually in XAML

In order to add control manually in XAML, do the below steps:

1. Add the below required assembly reference to the project, Syncfusion.SfDiagram.UWP .
2. Import SfDiagram control namespace  Syncfusion.UI.Xaml.Diagram in XAML page.
3. Declare SfDiagram control in XAML page.

N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your UWP application to use our components.
    
{% tabs %}
{% highlight xaml %}
<Page
    x:Class="Flow_Diagram.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:Flow_Diagram"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncDiagram="using:Syncfusion.UI.Xaml.Diagram"
    mc:Ignorable="d"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    
    <Grid>
        <syncDiagram:SfDiagram x:Name="Diagram"/>
    </Grid>
</Page>
{% endhighlight %}
{% endtabs %}

### Adding control manually in C\#

In order to add control manually in XAML, do the below steps:

1. Add the below required assembly references to the project, Syncfusion.SfDiagram.UWP.
2. Import SfDiagram namespace Syncfusion.UI.Xaml.Diagram.
3. Create SfDiagram control instance and add it to the Grid.

{% tabs %}
{% highlight C# %}
using Syncfusion.UI.Xaml.Diagram;

namespace Flow_Diagram
{   
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            // Initializes the SfDiagram
            SfDiagram diagram=new SfDiagram();
            Root_Grid.Children.Add(diagram);
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Flow Chart
Let us create a simple flow chart using SfDiagram.

#### Initialize the Diagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram in XAML as shown in the following code example.

{% tabs %}
{% highlight xaml %}
  <!--Initializes the SfDiagram in XMAL window-->
  <syncDiagram:SfDiagram x:Name="diagram"/>
{% endhighlight %}
{% highlight c# %}
            // Initializes the SfDiagram in C#
            SfDiagram diagram = new SfDiagram();
{% endhighlight %} 
{% endtabs %}

#### Initialize Nodes and Connectors

To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. 
Connectors property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

{% tabs %}
{% highlight xaml %}
<syncDiagram:SfDiagram.Nodes>
   <!--Observable Collection of NodeViewModel-->
   <syncDiagram:NodeCollection/>
</syncDiagram:SfDiagram.Nodes>
<syncDiagram:SfDiagram.Connectors>
   <!--Observable Collection of ConnectorViewModel-->
   <syncDiagram:ConnectorCollection/>
</syncDiagram:SfDiagram.Connectors>
 {% endhighlight %}
{% highlight c# %}
            //Initialize Nodes with Observable Collection of NodeViewModel.
            diagram.Nodes = new NodeCollection();
            //Initialize Connectors with Observable Collection of ConnectorViewModel
            diagram.Connectors = new ConnectorCollection();
{% endhighlight %}       
{% endtabs %}

### Add Nodes

 Let us create and add a NodeViewModel with height, width, shape, shape style,specific position, size and Annotation.

#### Creating a Node

Creating NodeViewModel with Specified Height and Width.

{% tabs %}
{% highlight xaml %}
<syncDiagram:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120"/> 
{% endhighlight %}
{% highlight c# %}
            NodeViewModel Begin = new NodeViewModel()
            {
                ID = "Begin",
                UnitWidth = 120,
                UnitHeight = 40,
            };  
{% endhighlight %}
{% endtabs %}

#### Adding specific position to Node

{% tabs %}
{% highlight xaml %}
 <syncDiagram:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60"/>  
{% endhighlight %}
{% highlight c# %}
            NodeViewModel Begin = new NodeViewModel()
            {
                ID = "Begin",
                UnitWidth = 120,
                UnitHeight = 40,
                OffsetX = 300,
                OffsetY = 60,
            };
{% endhighlight %}
{% endtabs %}

#### Adding Shape and ShapeStyle to Node

 We have provided set of basic shapes for Diagram as ResourceDictionary. In order to use the built-in shapes, Shapes dictionary should be merged in Application.  
 Please refer to [Shapes](https://help.syncfusion.com/uwp/diagram/shapes) to know about built-in Shapes.
  
{% tabs %}
{% highlight xaml %}  
<ResourceDictionary>
    <ResourceDictionary.MergedDictionaries>
        <!--Initialize Shapes-->
        <ResourceDictionary Source="ms-appx:///Syncfusion.SfDiagram.UWP/Resources/BasicShapes.xaml"/>
    </ResourceDictionary.MergedDictionaries>
            <!--Style for Shape of the Node-->
            <Style TargetType="Path" x:Key="ShapeStyle">
                <Setter Property="Fill" Value="#FF5B9BD5"/>
                <Setter Property="Stretch" Value="Fill"/>
                <Setter Property="Stroke" Value="#FFEDF1F6"/>
            </Style>
</ResourceDictionary>

<syncfusion:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}" ShapeStyle="{StaticResource ShapeStyle}" UnitHeight="40" UnitWidth="120"/>
  {% endhighlight %}

{% highlight c# %} 
            NodeViewModel Begin = new NodeViewModel()
            {
                ID = "Begin",
                UnitWidth = 120,
                UnitHeight = 40,
                OffsetX = 300,
                OffsetY = 60,
                //Specify shape to the Node from built-in Shape Dictionary
                Shape = this.Resources["Ellipse"],
                //Apply style to Shape
                ShapeStyle = this.Resources["ShapeStyle"] as Style,
            };
{% endhighlight %}
{% endtabs %}

 Now Node will be looks like,
   
![AddNode](Getting-Started_images\addNode.png)
   
N> ID sets for each node to identify nodes easily while setting connectors.
   
#### Adding Annotation to node
   
 To initialize the Annotation property of the Node and Connector, it is assigned with the annotation collection, that is, ObservableCollection of the IAnnotation.
 
 {% highlight xaml %}
  <!--To apply Style for AnnotationEditorViewModel-->
 <Style TargetType="syncfusion:AnnotationEditor">
 </Style>
 {% endhighlight %} 
    
N> `Annotations` property is a collection, which indicates that more than one Annotation can be added to a Node and Connector.
    By default, `Annotations` property of Node and Connector is null.

 Now add the Annotation content to Node.

{% tabs %}
{% highlight xaml %}
<syncDiagram:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}" ShapeStyle="{StaticResource ShapeStyle}" UnitHeight="40" UnitWidth="120">
   <syncDiagram:NodeViewModel.Annotations>
     <!--Observable Collection of AnnotationEditorViewModel-->
     <syncDiagram:AnnotationCollection>
         <syncDiagram:AnnotationEditorViewModel Content="Begin"/>
     </syncDiagram:AnnotationCollection>
   </syncDiagram:NodeViewModel.Annotations>
</syncDiagram:NodeViewModel>       
{% endhighlight %}
{% highlight c# %}
            // Creating the NodeViewModel  
            NodeViewModel Begin = new NodeViewModel()
            {
                ID = "Begin",
                UnitWidth = 120,
                UnitHeight = 40,
                OffsetX = 300,
                OffsetY = 60,
                //Specify shape to the Node from built-in Shape Dictionary
                Shape = this.Resources["Ellipse"],
                //Apply style to Shape
                ShapeStyle = this.Resources["ShapeStyle"] as Style,
                Annotations = new AnnotationCollection()
                {
                    new AnnotationEditorViewModel()
                    {
                        Content="Begin",
                    }
                }
            };
            // Add Node to Nodes property of the Diagram
            (diagram.Nodes as NodeCollection).Add(Begin);      
{% endhighlight %}
{% endtabs %}

Now Node will be looks like,
 
![NodeAnnotation](Getting-Started_images\nodeAnnotation.PNG)
 
### Nodes for Flow Diagram

 We can add multiple Nodes with different shapes into diagram as NodeViewModel.

{% tabs %}
{% highlight xaml %}
<syncDiagram:NodeCollection>
   <!--Begin-->
  <syncDiagram:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}" ShapeStyle="{StaticResource ShapeStyle}" UnitHeight="40" UnitWidth="120">
     <syncDiagram:NodeViewModel.Annotations>
        <!--Observable Collection of AnnotationEditorViewModel-->
        <syncDiagram:AnnotationCollection>
           <syncDiagram:AnnotationEditorViewModel Content="Begin"/>
        </syncDiagram:AnnotationCollection>
     </syncDiagram:NodeViewModel.Annotations>
  </syncDiagram:NodeViewModel>
   <!--Process-->
  <syncDiagram:NodeViewModel ID="Process" UnitHeight="60" UnitWidth="120" OffsetX="300" OffsetY="140"  Shape="{StaticResource PredefinedProcess}" ShapeStyle="{StaticResource ShapeStyle}">
     <syncDiagram:NodeViewModel.Annotations>
        <syncDiagram:AnnotationCollection>
           <syncDiagram:AnnotationEditorViewModel Content="Process"/>
        </syncDiagram:AnnotationCollection>
     </syncDiagram:NodeViewModel.Annotations>
  </syncDiagram:NodeViewModel>
   <!--End-->
  <syncDiagram:NodeViewModel ID="End" UnitHeight="40" UnitWidth="40" OffsetX="300" OffsetY="225" Shape="{StaticResource Ellipse}" ShapeStyle="{StaticResource ShapeStyle}"> 
     <syncDiagram:NodeViewModel.Annotations>
         <syncDiagram:AnnotationCollection>
             <syncDiagram:AnnotationEditorViewModel Content="End"/>
         </syncDiagram:AnnotationCollection>
     </syncDiagram:NodeViewModel.Annotations>
   </syncDiagram:NodeViewModel>
</syncDiagram:NodeCollection>
{% endhighlight %}
{% highlight c# %}
            //Begin
            NodeViewModel Begin = AddNode(300, 60, 120, 40, "Begin", "Ellipse");
            //Process
            NodeViewModel Process = AddNode(300, 140, 120, 60, "Process", "PredefinedProcess");
            //End
            NodeViewModel End = AddNode(300, 225, 40, 40, "End", "Ellipse");

            // Add Node to Nodes property of the Diagram
            (diagram.Nodes as NodeCollection).Add(Begin);
            (diagram.Nodes as NodeCollection).Add(Process);
            (diagram.Nodes as NodeCollection).Add(End);


            //Creating NodeViewModel
            public NodeViewModel AddNode(double offsetX, double offsetY, double width, double height, string text, string shape)
            {
                NodeViewModel node = new NodeViewModel();
                node.ID = text;
                node.OffsetX = offsetX;
                node.OffsetY = offsetY;
                node.UnitHeight = height;
                node.UnitWidth = width;
                //Specify shape to the Node from built-in Shape Dictionary
                node.Shape = this.Resources[shape];
                //Apply style to Shape
                node.ShapeStyle = this.Resources["ShapeStyle"] as Style;
                node.Annotations = new AnnotationCollection()
                {
                    new AnnotationEditorViewModel()
                    {
                        Content=text,
                    },
                };
                return node;
            }
{% endhighlight %}
{% endtabs %}

 Finally all Nodes added to diagram and it will be looks like

![CompleteDiagram](Getting-Started_images\completeNodes.png)

### Add Connectors

 Connector is to make connection or link between two Nodes, Ports and Points.

#### Create Connector With Source Node and Target Node 

 Here, we have used `SourceNodeID` and `TargetNodeID` property of the Connector.These properties will be assigned with `ID` property of the Node.

{% tabs %}
{% highlight xaml %}
 <syncDiagram:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Process"/>
{% endhighlight %}
{% highlight c# %}
            ConnectorViewModel connector1 = new ConnectorViewModel()
            {
                SourceNodeID = "Begin",
                TargetNodeID = "Process",
            };
{% endhighlight %}
{% endtabs %}

#### Adding Connector geometry style

{% tabs %}
{% highlight xaml %}
 <!--Style for TargetDecorator of the Connector-->
<Style TargetType="Path" x:Key="TargetDecoratorStyle">
   <Setter Property="Stroke" Value="Black"/>
   <Setter Property="Stretch" Value="Fill"/>
   <Setter Property="Fill" Value="Black"/>
   <Setter Property="Height" Value="10"/>
   <Setter Property="Width" Value="10"/>
</Style>

<!--Style for Geometry of the Connector-->
<Style TargetType="Path" x:Key="ConnectorGeometryStyle">
    <Setter Property="Stroke" Value="Black" />
    <Setter Property="StrokeThickness" Value="1" />
</Style>
      
{% endhighlight %} 
{% highlight c# %}
            ConnectorViewModel connector1 = new ConnectorViewModel()
            {
                SourceNodeID = "Begin",
                TargetNodeID = "Process",
                //Apply Style to TargetDecorator
                TargetDecoratorStyle = this.Resources["TargetDecoratorStyle"] as Style,
                //Apply Style to Geometry of the Connector.
                ConnectorGeometryStyle = this.Resources["ConnectorGeometryStyle"] as Style
            };

            //Add Connector to Connectors property of the Diagram
            (diagram.Connectors as ConnectorCollection).Add(connector1);
{% endhighlight %}
{% endtabs %}

Now output will be,

 ![NodeWithConnector](Getting-Started_images\nodewithConnector.png)
 
#### Connectors for Flow diagram

Now we can connect all nodes using ConnectorViewModel.

{% tabs %}
{% highlight xaml %}
<syncDiagram:ConnectorCollection>
    <syncDiagram:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Process" ConnectorGeometryStyle="{StaticResource ConnectorGeometryStyle}" TargetDecoratorStyle="{StaticResource TargetDecoratorStyle}"/>
    <syncDiagram:ConnectorViewModel SourceNodeID="Process" TargetNodeID="End" ConnectorGeometryStyle="{StaticResource ConnectorGeometryStyle}" TargetDecoratorStyle="{StaticResource TargetDecoratorStyle}"/>
</syncDiagram:ConnectorCollection>
{% endhighlight %} 
{% highlight c# %}
            //Creating ConnectorViewModel
            ConnectorViewModel connector1 = CreateConnector("Begin", "Process");
            ConnectorViewModel connector2 = CreateConnector("Process", "End");

            //Add Connector to Connectors property of the Diagram
            (diagram.Connectors as ConnectorCollection).Add(connector1);
            (diagram.Connectors as ConnectorCollection).Add(connector2);

            //Creating ConnectorViewModel
            private ConnectorViewModel CreateConnector(string source, string target)
            {
                ConnectorViewModel connector = new ConnectorViewModel()
                {
                    SourceNodeID = source,
                    TargetNodeID = target,
                    //Apply Style to TargetDecorator
                    TargetDecoratorStyle = this.Resources["TargetDecoratorStyle"] as Style,
                    //Apply Style to Geometry of the Connector.
                    ConnectorGeometryStyle = this.Resources["ConnectorGeometryStyle"] as Style
                };

                return connector;
            }
{% endhighlight %} 
{% endtabs %}

Now output will be looks like,

![FlowDiagram](Getting-Started_images\completeDiagram.png)
    
[View Sample in GitHub](https://github.com/SyncfusionExamples/UWP-Diagram-Examples/tree/main/Samples/GettingStarted/Flowchartsample).
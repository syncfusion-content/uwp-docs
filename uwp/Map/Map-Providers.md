---
layout: post
title: Map Providers in SfMap control
description: Learn how to work with online maps
platform: UWP
control: SfMap
documentation: ug
---

# Map Providers

SfMap control supports map providers such as `OpenStreetMap` and `Bing Map` that can be added to any layers in maps.

## Open Street Map

`OpenStreetMap` is a map of the entire world. The OpenStreetMap allows you to view, edit and use geographical data in a collaborative way from any place on the Earth.

### Enable OSM

You can enable this feature by setting the `LayerType` property value as `OSM`.

{% highlight xml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ImageryLayer LayerType="OSM" />
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >
        
{% endhighlight %}
![](Map-Providers_images/Map-Providers_img1.png)



## Bing Map

`Bing Map` is a key feature in accessing the external geospatial imagery services for deep-zoom satellite view.

### Enable Bing Map 

You can enable this feature by defining the LayerType as `Bing`. 

### Bing Map Key

The bing Map key is provided as input to this key property. The Bing Map key can be obtained from 

[http://www.microsoft.com/maps/create-a-bing-maps-key.aspx](http://www.microsoft.com/maps/create-a-bing-maps-key.aspx).

### Aerial View


{% highlight xml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ImageryLayer LayerType="Bing" BingMapKey="Bing Map Key" BingMapStyle="Aerial" />     
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >

{% endhighlight %}


![](Map-Providers_images/Map-Providers_img2.png)


### Road View


{% highlight xml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ImageryLayer LayerType="Bing" BingMapKey="Bing Map Key" BingMapStyle="Road" />     
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >

{% endhighlight %}

![](Map-Providers_images/Map-Providers_img3.png)



### AerialWithLabelView


{% highlight xml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ImageryLayer LayerType="Bing" BingMapKey="Bing Map Key" BingMapStyle="AerialWithLabels" />     
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >

{% endhighlight %}

![](Map-Providers_images/Map-Providers_img4.png)

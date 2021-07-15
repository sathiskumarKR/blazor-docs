---
layout: post
title: Range Band in Blazor Sparkline component | Syncfusion
description: Learn here all about Range Band of Syncfusion Sparkline (SfSparkline) component and more.
platform: Blazor
control: Sparkline Charts
documentation: ug
---

# Range Band in Blazor Sparkline (SfSparkline)

Range band represents the quality or improves the readability of a specific range for the Sparkline y-axis by specifying the [`StartRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_StartRange) and the [`EndRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_EndRange) properties in the [`SparklineRangeBand`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html) in the [`SparklineRangeBandSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBandSettings.html).

The following properties are used for the customization of the range band:

* [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_Color) - Specifies the color of the range band.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_Opacity) - Specifies the opacity of [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_Color) in the range band.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }" Height="150px" Width="150px" LineWidth="2" Fill="#0d3c9b">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="7" MinY="-1">
    </SparklineAxisSettings>
    <SparklineRangeBandSettings>
        <SparklineRangeBand StartRange="1" EndRange="2" Color="#bfd4fc" Opacity="0.4">
        </SparklineRangeBand>
        <SparklineRangeBand StartRange="4" EndRange="5" Color="red" Opacity="0.4">
        </SparklineRangeBand>
    </SparklineRangeBandSettings>
</SfSparkline>
```

![Sparkline Charts with multiple range band](./images/rangeband/MultipleRangeBand.png)
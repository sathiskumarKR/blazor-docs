---
layout: post
title: Lightweight Range Selector in the Blazor Range Selector component | Syncfusion 
description: Learn here all about Lightweight Range Selector of Syncfusion Blazor Range Selector (SfRangeNavigator) component and more.
platform: Blazor
control: Range Selector
documentation: ug
---

# Lightweight Range Selector in the Blazor Range Selector (SfRangeNavigator)

By default, when the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfRangeNavigator.html#Syncfusion_Blazor_Charts_SfRangeNavigator_DataSource) for [`RangeNavigatorSeries`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorSeries.html) is empty, a lightweight Range Selector will be shown without Chart. The following code example shows the lightweight Range Selector.

```csharp

@using Syncfusion.Blazor.Charts

<SfRangeNavigator Value="@Value" ValueType="RangeValueType.DateTime" DataSource="@DataSource" XName="X"
                  YName="Y" IntervalType="@RangeIntervalType.Years" LabelIntersectAction="RangeLabelIntersectAction.Hide">
    <RangeNavigatorRangeTooltipSettings Enable="true"></RangeNavigatorRangeTooltipSettings>
</SfRangeNavigator>

@code {

    public class SampleData
    {
        public DateTime X { get; set; }
        public double Y { get; set; }
    }

    public DateTime[] Value = new DateTime[] { new DateTime(2007, 01, 01), new DateTime(2009, 01, 01) };

    public List<SampleData> DataSource = new List<SampleData>
    {
        new SampleData { X = new DateTime(2005, 01, 01), Y = 21 },
        new SampleData { X = new DateTime(2006, 01, 01), Y = 24 },
        new SampleData { X = new DateTime(2007, 01, 01), Y = 36 },
        new SampleData { X = new DateTime(2008, 01, 01), Y = 38 },
        new SampleData { X = new DateTime(2009, 01, 01), Y = 54 },
        new SampleData { X = new DateTime(2010, 01, 01), Y = 57 },
        new SampleData { X = new DateTime(2011, 01, 01), Y = 70 }
    };
}

```

![Lightweight Range Selector](images/common/light-weight.png)

## See Also

* [Period Selector](./period-selector/)
---
layout: post
title: Two Way Binding in Blazor Splitter Component | Syncfusion 
description: Learn about Two Way Binding in Blazor Splitter component of Syncfusion, and more details.
platform: Blazor
control: Splitter
documentation: ug
---

# Two way Binding

The splitter `SplitterPane` `Collapsed` property supports the two-way binding and it can be achieved by using the `bind-Collapsed` attribute. If the component value has been changed, it will affect all the places where we bind the variable for the bind-value attribute.

In the following example, if either the value is changed in checkbox or splitter first pane collpased state, it will reflect in both the checkbox and splitter pane.

```csharp

@using Syncfusion.Blazor.Layouts
@using Syncfusion.Blazor.Buttons

<div>
    <div class="row">
        <SfCheckBox @bind-Checked="@collapsed" Label="CheckBox"></SfCheckBox>
    </div>
    <SfSplitter Height="300px" Width="100%">
        <SplitterPanes>
            <SplitterPane Size="25%" Min="60px" Collapsible="true" @bind-Collapsed="@collapsed">
                <div>
                    <div class="contents">
                        <div>Left pane</div>
                    </div>
                </div>
            </SplitterPane>
            <SplitterPane Size="50%" Min="60px" Collapsible="true">
                <div>
                    <div class='contents'>
                        <div>Right pane</div>
                    </div>
                </div>
            </SplitterPane>
        </SplitterPanes>
    </SfSplitter>
</div>

@code {
    public bool collapsed { get; set; } = false;
}

```

The output will be as follows.

![Expand and Collapse](./images/two-way-binding.png)

## See Also

* [Resizable split panes](./resizing/)
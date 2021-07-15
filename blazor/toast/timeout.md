---
layout: post
title: Timeout in Blazor Toast Component | Syncfusion 
description: Learn about Timeout in Blazor Toast component of Syncfusion, and more details.
platform: Blazor
control: Toast
documentation: ug
---

# Time out

The toast can be expired based on the `Timeout` property. The toast can live till the time out reaches without user interaction, a time out value is considered as a millisecond.

* The `Timeout` delay can be visually represented using [Progress Bar](./config/#progress-bar).

* The `ExtendedTimeOut` property determines how long the toast should be displayed after a user hovers over it.

> You can terminate the process by using the `ShowCloseButton` property for destroying the toast at any time.

```csharp

@using Syncfusion.Blazor.Inputs
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<div class="control-section toast-default-section">
    <SfToast @ref="ToastObj" Title="Anjolie Stokes" Width="230" Height="250" Content="@ToastContent" Timeout="@ToastTimeOut">
        <ToastPosition X="Right" Y="Bottom"></ToastPosition>
        <ToastButtons>
            <ToastButton  Content = "Ignore" OnClick="@HideToast"></ToastButton>
            <ToastButton  Content = "reply"></ToastButton>
        </ToastButtons>
    </SfToast>

    <div class="col-lg-12 col-sm-12 col-md-12 center">
        <div id="toastBtnDefault" style="margin: auto; text-align: center">
            <div id="textbox-contain" style="text-align: initial; display: inline-block;">
                <SfTextBox @ref="TextBoxObj" FloatLabelType="FloatLabelType.Auto" Placeholder="Enter timeOut" Value="@TextBoxVal" ValueChange="@OnValChange"></SfTextBox>
            </div>
            <SfButton @onclick="@ShowToast"> Show Toast </SfButton>
        </div>
    </div>
    <br /><br />
    <div id='result'></div>
</div>

<style>
    #elementToastTime .e-toast-message {
        padding: 10px;
        text-align: center;
    }

    #textbox-contain {
        text-align: initial;
        display: inline-block
    }
</style>

@code {
    SfToast ToastObj;
    SfTextBox TextBoxObj;

    private int ToastTimeOut { get; set; } = 0;
    private string TextBoxVal { get; set; } = "0";
    private string ToastContent { get; set; } = "<p><img src='https://blazor.syncfusion.com/demos/images/toast/laura.png'></p>";

    private async Task ShowToast()
    {
       await this.ToastObj.ShowAsync();
    }

    private void OnValChange()
    {
        this.ToastTimeOut = int.Parse(this.TextBoxObj.Value);
        this.TextBoxVal = this.TextBoxObj.Value;
        this.StateHasChanged();
    }

    private async Task HideToast()
    {
       await this.ToastObj.HideAsync();
    }
}

```

The above code will give following output.

![TimeOut](./images/timeout.png)

## Static toast

You can prevent auto hiding in a toast as visible like static by setting zero (`0`) value in the `Timeout` Property.

```csharp

@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<SfToast @ref="ToastObj" Timeout=0 Title="Matt sent you a friend request" Content="@ToastContent">
    <ToastPosition X="Right"></ToastPosition>
</SfToast>

<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div id="toastBtnDefault" style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowToast"> Show Toast </SfButton>
    </div>
</div>

<style>
    #elementToastTime .e-toast-message {
        padding: 10px;
        text-align: center;
    }
</style>

@code {
    SfToast ToastObj;

    private string ToastContent = "You have a new friend request yet to accept";

    private async Task ShowToast()
    {
       await this.ToastObj.ShowAsync();
    }
}

```

The output will be as follows.

![TimeOut](./images/timeout-static.png)
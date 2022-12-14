# How to create a dotted line in WinUI Chart (SfCartesianChart)

WinUI line chart is a visual representation of the data trends at equal intervals by connecting a set of points on a plot with straight lines. 

This section explains how to create dotted line charts in WinUI cartesian charts.

WinUI cartesian chart allows you to create a line chart with dashes by using the [StrokeDashArray](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.LineSeries.html#Syncfusion_UI_Xaml_Charts_LineSeries_StrokeDashArray) property of [LineSeries](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.LineSeries.html), as shown in the following code example.

If you are new to our control, refer to this [KB documentation](https://www.syncfusion.com/kb/13540/how-to-create-a-winui-line-chart-sfcartesianchart) which helps you to create a WinUI line chart.


**[XAML]**
```
<chart:SfCartesianChart>
    <chart:SfCartesianChart.DataContext>
            <local:ViewModel />
    </chart:SfCartesianChart.DataContext>

    <chart:SfCartesianChart.XAxes>
            <chart:CategoryAxis  />
    </chart:SfCartesianChart.XAxes>

    <chart:SfCartesianChart.YAxes>
           <chart:NumericalAxis />
    </chart:SfCartesianChart.YAxes>

    <chart:LineSeries XBindingPath="Year"
                      YBindingPath="Counts"
                      ItemsSource="{Binding Data}"
                      ShowDataLabels="True">
      <chart:LineSeries.StrokeDashArray>
                    <DoubleCollection>
                        <x:Double>3</x:Double>
                        <x:Double>3</x:Double>
                    </DoubleCollection>
      </chart:LineSeries.StrokeDashArray>

</chart:SfCartesianChart>

```
**[C#]**
```
var chart = new SfCartesianChart();
ViewModel viewModel = new ViewModel();

// Initializing XAxes
var xAxis = new CategoryAxis();
chart.XAxes.Add(xAxis);

// Initializing YAxes
var yAxis = new NumericalAxis();
chart.YAxes.Add(yAxis);

// Initializing stroke dash array for line series
var strokeDashArray = new DoubleCollection() { 3, 3 };

var series = new LineSeries()
{
        ItemsSource = viewModel.Data,
        XBindingPath = "Year",
        YBindingPath = "Counts",
        ShowDataLabels = true,
        StrokeDashArray = strokeDashArray,
};

chart.Series.Add(series);

```
## Output:
![Dotted line chart](https://user-images.githubusercontent.com/61832185/202086362-e424eee5-eaa0-4cd6-b5b4-d8361378833b.png)

This user guide [Documentation](https://help.syncfusion.com/winui/cartesian-charts/getting-started) helps you to acquire more knowledge on the WinUI cartesian charts and their features. You can also refer to the [Feature Tour](https://www.syncfusion.com/winui-controls/charts) site to get an overview of all the features in the chart.

## <a name="requirements-to-run-the-demo"></a>Requirements to run the demo ##

* [Visual Studio 2022](https://visualstudio.microsoft.com/downloads/)
* [Windows App SDK 1.1 extension](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/stable-channel#version-11)
* .NET 6.0

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

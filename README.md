# How to create a dotted line in WinUI Chart (SfCartesianChart)

WinUI line chart is a visual representation of the data trends at equal intervals by connecting a set of points on a plot with straight lines. This section explains how to create dotted line charts in WinUI cartesian chart.
If you are new to our control refer to this [KB documentation](https://www.syncfusion.com/kb/13540/how-to-create-a-winui-line-chart-sfcartesianchart), Which helps you to get more knowledge on the WinUI line chart and its features.
WinUI cartesian chart allows you to create a line chart with dashes by using [StrokeDashArray](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.LineSeries.html#Syncfusion_UI_Xaml_Charts_LineSeries_StrokeDashArray) property of [LineSeries](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Charts.LineSeries.html) as shown in the following code example.

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

![Dotted line chart](https://user-images.githubusercontent.com/61832185/200857633-73818d14-6e82-465b-8de6-a728cb90278f.png)

This user guide [Documentation](https://help.syncfusion.com/winui/cartesian-charts/getting-started) helps you to acquire more knowledge on the WinUI cartesian charts and their features. You can also refer to the [Feature Tour](https://www.syncfusion.com/winui-controls/charts) site to get an overview of all the features in the   chart.

KB article - [How to create a dotted line chart in WinUI Chart (SfCartesianChart)?]( )

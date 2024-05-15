# **Fun with Tables**

- The passage highlights the idea that Markdown tables can serve not only as structural elements but also as datasets for visual representation.

- It introduces the concept of using tables to automatically generate visualizations, thereby eliminating the need for external tools.

- It suggests that Markdown users are already engaging in data configuration and proposes leveraging the structural settings of tables to automatically visualize data.

**`Example:`**

- The example demonstrates a simple dataset represented both graphically and in tabular form. It consists of two columns: "x" and "dots", where "x" represents values on the x-axis and "dots" represents corresponding data points.

- The dataset is shown as a graphical plot and as a Markdown table

```
|   x | dots |
| ---:| ----:|
|   0 |    0 |
|  10 |    2 |
|  20 |    4 |
|  30 |    6 |
```

**`Interpretation:`**

- Markdown's simplicity and flexibility allow for the integration of data visualization directly within documents.

- By treating Markdown tables as datasets, users can automate the process of generating visualizations, making data exploration more accessible and efficient.

- This approach promotes reproducibility and transparency by embedding data alongside its visual representation, facilitating easier sharing and interpretation by others.

|   x | dots |
| ---:| ----:|
|   0 |    0 |
|  10 |    2 |
|  20 |    4 |
|  30 |    6 |

## **LinePlot**

- This text showcases how Markdown tables can be utilized as datasets for generating visual representations directly within a document.

- It introduces the concept of incorporating additional settings through HTML comments at the beginning of the table to customize the graphical representation.

- Different types of visualizations can be automatically determined based on the table structure, with attributes such as `data-title`, `data-xlabel`, and `data-ylabel` used to adjust the graphical representation.

**`Example:`**

1. The first dataset represents government expenditure on education as a percentage of GDP for different countries over several years. The table includes attributes such as `data-title`, `data-xlabel`, and `data-ylabel` to customize the graphical representation.

2. The second dataset demonstrates the same functionality, but with additional attributes provided through an HTML comment at the beginning of the table.

3. The third dataset showcases a different type of presentation - a bar chart. Attributes such as `Animal`, `weight in kg`, `Lifespan years`, and `Mitogen` define different categories, with each row representing a distinct data point.


```
<!--
data-title="Government expenditure on education"
data-xlabel="year"
data-ylabel="% of GDP"
-->
| Year | Finland | USA | Germany |   China |
| ---- | -------:| ---:| -------:| -------:|
| 1995 | 6.80942 |     | 4.42079 | 1.84192 |
| 1996 | 6.86052 |     | 4.48319 | 1.85338 |
| ...  |     ... | ... |     ... |     ... |

| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |              2 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |
```

**`output`**


| Year | Finland | USA | Germany |   China |
| ---- | -------:| ---:| -------:| -------:|
| 1995 | 6.80942 |     | 4.42079 | 1.84192 |
| 1996 | 6.86052 |     | 4.48319 | 1.85338 |
| ...  |     ... | ... |     ... |     ... |


| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |              2 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |

- The code provided consists of Markdown tables with accompanying HTML comments defining attributes for graphical representation.

- Upon rendering, the Markdown interpreter would generate visualizations based on the table structure and attributes provided, resulting in graphical representations of the datasets.

## **ScatterPlot**

- This section explains that if the table resembles that of a LinePlot but contains duplicate x-values, the data cannot be interpreted as a mathematical function.

- In such cases, the data is visualized as a ScatterPlot, where only the data points are displayed without connecting lines.

**`Example:`**

- Two sets of tables are provided. The first table represents data with duplicate x-values (5.0 appearing multiple times in the first column), making it unsuitable for interpretation as a mathematical function.

- The second table represents similar data but with distinct x-values, enabling it to be interpreted as a mathematical function.

```
| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    ... |      |     |
|    5.0 | 10.0 |   7 |
|    ... |      |     |

| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    6.0 |  1.0 |   4 |
|    7.0 |  1.0 |   5 |
|    8.0 |  1.0 |   5 |
|    9.0 |  1.0 |   4 |
|   10.0 |  1.0 |   5 |
|    5.0 | 10.0 |   7 |
|    6.0 | 10.0 |   8 |
|    7.0 | 10.0 |   7 |
|    8.0 | 10.0 |   7 |
|    9.0 | 10.0 |   8 |
|   10.0 | 10.0 |   7 |
```

**`OUTPUT`**

| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    ... |      |     |
|    5.0 | 10.0 |   7 |
|    ... |      |     |

| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    6.0 |  1.0 |   4 |
|    7.0 |  1.0 |   5 |
|    8.0 |  1.0 |   5 |
|    9.0 |  1.0 |   4 |
|   10.0 |  1.0 |   5 |
|    5.0 | 10.0 |   7 |
|    6.0 | 10.0 |   8 |
|    7.0 | 10.0 |   7 |
|    8.0 | 10.0 |   7 |
|    9.0 | 10.0 |   8 |
|   10.0 | 10.0 |   7 |

- The first table, containing duplicate x-values, would be visualized as a ScatterPlot.

- The second table, with distinct x-values, could be interpreted as a LinePlot if desired, as it represents a mathematical function without duplicate x-values.


## **BoxPlot **

- In cases where you have a dataset presented in a ScatterPlot-like format but want to visualize it as a BoxPlot, you can manually change the visualization type by adding the `data-type="boxplot"` attribute to the beginning of your table.

- Each column in the table is then treated as a separate dataset, and the data is visualized accordingly in a BoxPlot format.

**`Example:`**

- Two sets of tables are provided. The first table demonstrates how to convert a ScatterPlot-like dataset to a BoxPlot by adding the data-type="boxplot" attribute at the beginning.

- The second table represents the same data but with additional entries for demonstration purposes.

```
<!-- data-type="boxplot" -->
| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    ... |  ... |  .. |

<!-- data-type="boxplot" -->
| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    6.0 |  1.0 |   4 |
|    7.0 |  1.0 |   5 |
|    8.0 |  1.0 |   5 |
|    9.0 |  1.0 |   4 |
|   10.0 |  1.0 |   5 |
|    5.0 | 10.0 |   7 |
|    6.0 | 10.0 |   8 |
|    7.0 | 10.0 |   7 |
|    8.0 | 10.0 |   7 |
|    9.0 | 10.0 |   8 |
|   10.0 | 10.0 |   7 |
|        |      |   1 |
```

**`OUTPUT`**


| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    ... |  ... |  .. |


| Random |    I |  II |
| ------:| ----:| ---:|
|    5.0 |  1.0 |   5 |
|    6.0 |  1.0 |   4 |
|    7.0 |  1.0 |   5 |
|    8.0 |  1.0 |   5 |
|    9.0 |  1.0 |   4 |
|   10.0 |  1.0 |   5 |
|    5.0 | 10.0 |   7 |
|    6.0 | 10.0 |   8 |
|    7.0 | 10.0 |   7 |
|    8.0 | 10.0 |   7 |
|    9.0 | 10.0 |   8 |
|   10.0 | 10.0 |   7 |
|        |      |   1 |

- Both tables would be visualized as BoxPlots, with each column treated as a separate dataset.

## **BarChart**

- When the first column of a dataset contains at least one entry that cannot be parsed as a number, the dataset might be represented as a BarChart.

- The choice of visualization depends on factors such as the maximum values of the columns; if the maximum values do not differ significantly, a BarChart is chosen.

- However, if the maximum values vary significantly, alternative visualizations may be chosen to ensure clarity and readability.

**`Example:`**

- The provided dataset consists of animal data, including columns for weight, lifespan, and mitogen.

- Since the first column contains animal names (strings), it cannot be parsed as a number, making it suitable for representation as a BarChart.

```
| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |              2 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |
```

**`OUTPUT`**

| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |              2 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |

- The table would be visualized as a BarChart, with each row representing a distinct bar in the chart, and the animal names as labels on the x-axis.


## **Radar** 

- When certain data points are removed from a dataset, resulting in incomplete information for certain variables, alternative visualizations may be chosen to accommodate the remaining data effectively.

- In the provided example, if humans and sheep are removed from the dataset, resulting in weight in kilograms not being visible for certain animals, a RadarChart is selected.

- RadarCharts allow for the visualization of data with different "y"-axes, making them suitable for datasets with diverse characteristics.

**`Example:`**

- The provided dataset consists of animal data, including columns for weight, lifespan, and mitogen.

- If humans and sheep are removed from the dataset, resulting in weight in kilograms not being visible for certain animals, a RadarChart would be selected for visualization.

```
| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |             02 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
```

**`OUTPUT`**

| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |             02 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |

- The table would be visualized as a RadarChart, with each animal represented by a point on the chart, and the variables (weight in kg, lifespan years, mitogen) forming the axes.

## **PieChart** 

- The provided dataset consists of music-style categories and corresponding quantities or ratings for each category.

- When a table contains only one row filled with numbers, it is automatically presented as a pie chart, with the header representing the categories and the body denoting the quantities associated with each category.

- Additionally, if the first element of the list body contains text that cannot be directly interpreted as a number, it is used to define the main title of the chart, while the second text snippet is used as a subtitle.

**`Example:`**

- The first table represents music-style categories and quantities. Since it contains only one row filled with numbers, it would be automatically presented as a pie chart.

- The second table includes additional information in the first column, such as "Music-Style 1994" and "Student rating". This information is used to define the main title and subtitle of the chart.

```
| Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
| -------:| -------:| ------:| -------:| ---------:| -----:|
|      50 |      50 |    100 |     200 |       350 |   250 |

| Music-Style 1994 | Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
|:---------------- | -------:| -------:| ------:| -------:| ---------:| -----:|
| Student rating   |      50 |      50 |    100 |     200 |       350 |   250 |
```

**`OUTPUT`**

| Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
| -------:| -------:| ------:| -------:| ---------:| -----:|
|      50 |      50 |    100 |     200 |       350 |   250 |

| Music-Style 1994 | Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
|:---------------- | -------:| -------:| ------:| -------:| ---------:| -----:|
| Student rating   |      50 |      50 |    100 |     200 |       350 |   250 |

- The first table would be automatically presented as a pie chart, with each category represented by a segment of the pie chart proportional to its quantity.

- The second table would also be presented as a pie chart, but with "Music-Style 1994" as the main title and "Student rating" as the subtitle.


### **PieChart(s)** 

- By default, the provided table would be represented as a barchart.

- However, you can enforce the usage of pie charts by adding the data-type="PieChart" attribute into an HTML comment directly above the table.

- This instruction overrides the default behavior and ensures that the data is visualized as a pie chart.

**`Example:`**

- The instruction to enforce the usage of pie charts is added as an HTML comment above the table.

- This results in the data being visualized as a pie chart instead of a bar chart.

```
| Music-Style | Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
|:----------- | -------:| -------:| ------:| -------:| ---------:| -----:|
| 1994        |      50 |      50 |    100 |     200 |       350 |   250 |
| ...         |     ... |     ... |    ... |     ... |       ... |   ... |
```

**`OUTPUT`**

| Music-Style | Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
|:----------- | -------:| -------:| ------:| -------:| ---------:| -----:|
| 1994        |      50 |      50 |    100 |     200 |       350 |   250 |
| ...         |     ... |     ... |    ... |     ... |       ... |   ... |

- The table data would be visualized as a pie chart instead of a bar chart, with each category represented by a segment of the pie chart proportional to its value.

### **Animating Charts **

- In this example, animations are incorporated to dynamically change the values of the chart as you progress through slides or navigate backward.

- The {} syntax is used to specify which parts of the table should be animated.

- This approach adds a dynamic element to the presentation, but it may not be suitable for all audiences, particularly those who prefer a more traditional textbook-style format.

**`Example:`**

- The table represents music-style ratings over two different years, 1994 and 2014.

- Animations are incorporated to dynamically change the values of the chart as the presentation progresses.

```
{{1}}
| Music-Style {1-2}{1994} {2}{2014} |           Classic |           Country | Reggae |             Hip-Hop |           Hard-Rock |               Samba |
|:--------------------------------- | -----------------:| -----------------:| ------:| -------------------:| -------------------:| -------------------:|
| Student rating                    | {1-2}{50} {2}{20} | {1-2}{50} {2}{30} |    100 | {1-2}{200} {2}{220} | {1-2}{350} {2}{400} | {1-2}{250} {2}{230} |
```

**`OUTPUT`**

| Music-Style {1-2}{1994} {2}{2014} |           Classic |           Country | Reggae |             Hip-Hop |           Hard-Rock |               Samba |
|:--------------------------------- | -----------------:| -----------------:| ------:| -------------------:| -------------------:| -------------------:|
| Student rating                    | {1-2}{50} {2}{20} | {1-2}{50} {2}{30} |    100 | {1-2}{200} {2}{220} | {1-2}{350} {2}{400} | {1-2}{250} {2}{230} |

- The `{}` syntax is used to specify which parts of the table should be animated. For example, `{1-2}` indicates that the animation should transition between the values for 1994 and 2014, while `{1994} `and `{2014}` specify the years explicitly.

- As the presentation progresses, the values in the table will dynamically change to reflect the specified animations.

### **Transposing Data**

- The `data-transpose` attribute is used to mirror the data along an imaginary vertical axis, condensing the table into two columns and growing the data vertically.

- This allows for presenting the data in a more compact format, which might be preferable for long tables.

**`Example:`**

- The previous table, which represented music-style ratings over two different years, is transposed using the `data-transpose` attribute.

- This results in a more condensed format with two columns: "Music-Style" and "Student rating", where each row represents a specific music style and its corresponding rating for the years 1994 and 2014.

```

| Music-Style {1-2}{1994} {2}{2014} |      Student rating |
|:--------------------------------- | -------------------:|
| Classic                           |   {1-2}{50} {2}{20} |
| Country                           |   {1-2}{50} {2}{30} |
| Reggae                            |                 100 |
| Hip-Hop                           | {1-2}{200} {2}{220} |
| Hard-Rock                         | {1-2}{350} {2}{400} |
| Samba                             | {1-2}{250} {2}{230} |
```

- The transposed table presents the same information but in a more compact format.

- Each row now represents a specific music style, and the columns contain ratings for the years 1994 and 2014.

| Music-Style {1-2}{1994} {2}{2014} |      Student rating |
|:--------------------------------- | -------------------:|
| Classic                           |   {1-2}{50} {2}{20} |
| Country                           |   {1-2}{50} {2}{30} |
| Reggae                            |                 100 |
| Hip-Hop                           | {1-2}{200} {2}{220} |
| Hard-Rock                         | {1-2}{350} {2}{400} |
| Samba                             | {1-2}{250} {2}{230} |

- The data is now organized in a transposed format, which may make it easier to handle and interpret, especially for long tables.

## **Funnel** 

- The Funnel is a visualization similar to the PieChart, but it is not selected automatically. You need to set the data-type parameter to "funnel" if you wish to use the funnel visualization.

- The process for using effects to generate animated diagrams, such as funnel charts, remains the same as for pie charts.

**`Example:`**

1. The first table demonstrates how to specify the data-type parameter as "funnel" to generate a funnel chart.

```

| Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
| -------:| -------:| ------:| -------:| ---------:| -----:|
|      50 |      50 |    100 |     200 |       350 |   250 |
```

| Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
| -------:| -------:| ------:| -------:| ---------:| -----:|
|      50 |      50 |    100 |     200 |       350 |   250 |

2. The second table also utilizes the funnel visualization by setting the data-type parameter to "funnel".

```
| Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
| -------:| -------:| ------:| -------:| ---------:| -----:|
|      50 |      50 |    100 |     200 |       350 |   250 |
```

| Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
| -------:| -------:| ------:| -------:| ---------:| -----:|
|      50 |      50 |    100 |     200 |       350 |   250 |


3. The third table shows how to use effects, such as animation, to generate an animated funnel chart. The data-transpose attribute is also used to transpose the data, similar to the previous examples.

```
| Music-Style {1-2}{1994} {2}{2014} |      Student rating |
|:--------------------------------- | -------------------:|
| Classic                           |   {1-2}{50} {2}{20} |
| Country                           |   {1-2}{50} {2}{30} |
| Reggae                            |                 100 |
| Hip-Hop                           | {1-2}{200} {2}{220} |
| Hard-Rock                         | {1-2}{350} {2}{400} |
| Samba                             | {1-2}{250} {2}{230} |
```


| Music-Style {1-2}{1994} {2}{2014} |      Student rating |
|:--------------------------------- | -------------------:|
| Classic                           |   {1-2}{50} {2}{20} |
| Country                           |   {1-2}{50} {2}{30} |
| Reggae                            |                 100 |
| Hip-Hop                           | {1-2}{200} {2}{220} |
| Hard-Rock                         | {1-2}{350} {2}{400} |
| Samba                             | {1-2}{250} {2}{230} |


- The data is organized to represent music-style ratings for the years 1994 and 2014, and it is visualized as a funnel chart.

- In the third table, animations can be applied to create dynamic effects similar to those seen in pie charts.

## **Map**

- A map visualization is used to depict data on an actual map.

- To create a map visualization, you need to include a GeoJSON file containing relevant geographic information about the shapes of countries, states, cities, etc.

- The first column of your table must match the names of the objects in your GeoJSON data.

- You can specify the GeoJSON data file using the `data-src` attribute, and set the `data-type` parameter to "map" to indicate that you want to create a map visualization.

**`Example:`**

1. The first table demonstrates how to specify the GeoJSON data file and create a basic map visualization showing the percentage data for different countries.

```
| Country                | percent |
| ---------------------- | ------- |
| Albania                | 73.5    |
| Andorra                | 98.9    |
```

| Country                | percent |
| ---------------------- | ------- |
| Albania                | 73.5    |
| Andorra                | 98.9    |

2. The second table includes more data and specifies the GeoJSON data file for Europe.

```
| Country                | percent |
| ---------------------- | ------- |
| Albania                | 73.5    |
| Andorra                | 98.9    |
| Armenia                | 72.4    |
| Austria                | 87.9    |
| Azerbaijan             | 79.8    |
| ...                    | ...     |
```

| Country                | percent |
| ---------------------- | ------- |
| Albania                | 73.5    |
| Andorra                | 98.9    |
| Armenia                | 72.4    |
| Austria                | 87.9    |
| Azerbaijan             | 79.8    |
| ...                    | ...     |

- The `data-src` attribute specifies the URL of the GeoJSON file containing the geographic information.

- Each row in the table represents a country, and the "percent" column contains the data values to be visualized on the map.

- The map visualization will render each country with a color intensity corresponding to its data value


## **HeatMap **

- A HeatMap is a type of visualization used to represent data in a tabular format where values are represented as colors.

- HeatMaps are suitable for visualizing data where the table header and the first column exclusively contain numerical values, essentially representing coordinates.

- You can enforce the usage of a HeatMap by adding the data-type="heatmap" attribute to the HTML comment above the table.

- The data-title attribute can be used to provide a title for the HeatMap.

- Adding data-show will automatically display the HeatMap without the need to toggle visibility manually.

**`Example:`**

1. The table below demonstrates how to create a HeatMap for Seattle mean temperature data.

```
| Seattle |  Jan |  Feb |  Mar |  Apr |  May |  ... |
| -------:| ----:| ----:| ----:| ----:| ----:| ----:|
|       0 | 40.7 | 41.5 | 43.6 | 46.6 | 51.4 |  ... |
|       2 |  ... |  ... |  ... |  ... |  ... |  ... |
```

| Seattle |  Jan |  Feb |  Mar |  Apr |  May |  ... |
| -------:| ----:| ----:| ----:| ----:| ----:| ----:|
|       0 | 40.7 | 41.5 | 43.6 | 46.6 | 51.4 |  ... |
|       2 |  ... |  ... |  ... |  ... |  ... |  ... |

2. The second example contains more detailed temperature data for different times of the day and months.

```
| Seattle |  Jan |  Feb |  Mar |  Apr |  May |  Jun |  Jul |   Aug |  Sep |  Oct |  Nov |  Dec |
| -------:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| -----:| ----:| ----:| ----:| ----:|
|       0 | 40.7 | 41.5 | 43.6 | 46.6 | 51.4 | 56.0 | 60.5 |  61.2 | 57.0 | 50.1 | 44.1 | 39.6 |
|       2 | 40.2 | 40.7 | 42.7 | 45.3 | 50.0 | 54.4 | 58.5 |  59.2 | 55.4 | 49.2 | 43.5 | 39.3 |
|       ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |
```


| Seattle |  Jan |  Feb |  Mar |  Apr |  May |  Jun |  Jul |   Aug |  Sep |  Oct |  Nov |  Dec |
| -------:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| -----:| ----:| ----:| ----:| ----:|
|       0 | 40.7 | 41.5 | 43.6 | 46.6 | 51.4 | 56.0 | 60.5 |  61.2 | 57.0 | 50.1 | 44.1 | 39.6 |
|       2 | 40.2 | 40.7 | 42.7 | 45.3 | 50.0 | 54.4 | 58.5 |  59.2 | 55.4 | 49.2 | 43.5 | 39.3 |
|       ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

- The HeatMap represents the temperature data for Seattle, where the x-axis represents the months, and the y-axis represents different times of the day.

- The color intensity indicates the temperature values, with higher values represented by warmer colors and lower values by cooler colors.

- By using the `data-show attribute`, the HeatMap is displayed automatically without the need for manual interaction.

## **Parallel** 

- A Parallel representation, also known as a Parallel Coordinates Plot, is employed when there are too many categories to visualize effectively using a traditional BarChart.

- In a Parallel Coordinates Plot, each category is represented by a vertical axis, and data points are connected by lines to represent their values across these axes.

- This visualization method is particularly useful for comparing multiple variables simultaneously.

**`Example`**

- The table provided contains data on various metrics for different countries, such as GDP growth, births per woman, life expectancy, and population demographics.

- Each country is represented as a row, and the metrics are represented as columns.

- To generate a Parallel Coordinates Plot from this data, you would use the data-show attribute in the HTML comment above the table to automatically display the visualization.

```
| Country                |    GDP growth (%) | Births per woman | Life expectancy at birth (years) | Population ages >= 65 (%) | Pop. ages 15-64 (%) | Pop ages 0-14 (%) | Pop (total) |
| ---------------------- | -----------------:| ----------------:| --------------------------------:| --------------------------:| -------------------:| -----------------:| -----------:|
| Albania                |               7.5 |            1.858 |                 76.6337073170732 |            9.3330694913874 |    66.4522208535245 |  24.2147096550882 |     3143291 |
| Andorra                |  3.57073718591123 |            1.260 |                              NaN |                        NaN |                 NaN |               NaN |     83810.5 |
| Austria                |  2.17880778069679 |            1.414 |                 80.4475609756098 |           17.0078802490015 |    67.7942859199021 |  15.1978338310964 |     8336926 |
| Byelarus               | 11.29603925282670 |            1.420 |                 70.6328780487805 |           13.8161084682917 |    71.3440867491758 |  14.8398047825325 |     9680850 |
| Belgium                |  1.00416891576425 |            1.820 |                 80.1095609756098 |           17.2425951179457 |    65.9073170003941 |  16.8500878816601 |    10708433 |
| Bosnia and Herzegovina |  5.41999999999929 |            1.209 |                 75.1063170731708 |           13.7875788575916 |    70.5586044787057 |  15.6538166637027 |     3773100 |
| Bulgaria               |  6.21712220063873 |            1.478 |                 73.3165853658537 |           17.3328904412356 |    69.2610054713067 |  13.4061040874577 |     7623395 |
| Channel Islands        |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Croatia                |  2.35925308110710 |            1.470 |                 75.9121951219512 |           17.1754953634927 |    67.5174504975681 |  15.3070541389392 |     4434000 |
| Czech Republic         |  2.46366103329814 |            1.497 |                 77.2112195121951 |           14.6644147081870 |    71.1889763214880 |  14.1466089703250 |    10424336 |
| Denmark                | -0.86969912719333 |            1.892 |                 78.7004878048781 |           15.9364325701275 |    65.6692750948847 |  18.3942923349878 |     5493621 |
| Estonia                | -5.12891873578752 |            1.661 |                 73.9731707317073 |           16.9573479430650 |    68.0747344729978 |  14.9679175839372 |     1340675 |
| Faroe Islands          |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |       48511 |
| Finland                |  0.92209645431238 |            1.846 |                 79.7919512195122 |           16.5283868561977 |    66.6427434111131 |  16.8288697326892 |     5313399 |
| France                 |  0.21695181782435 |            1.998 |                 81.5204878048781 |           16.6134150592142 |    64.9880225189894 |  18.3985624217964 |    62277432 |
| Germany                |  0.98801573506542 |            1.376 |                 80.0885365853659 |           19.9652972040776 |    66.3351760329956 |  13.6995267629268 |    82110097 |
| Greece                 |  2.01498162894308 |            1.506 |                 79.9631707317073 |           18.1870521529388 |    67.5883962990861 |  14.2245515479751 |    11237094 |
| Hungary                |  0.59999999999994 |            1.352 |                 74.0090243902439 |           16.0592099507043 |    68.9813743902960 |  14.9594156589996 |    10038188 |
| Iceland                |  0.95512219949856 |            2.140 |                 81.5751219512195 |           11.6851788453979 |    67.3938402627208 |  20.9209808918813 |      317414 |
| Ireland                | -3.03575424255612 |            2.100 |                 79.8568292682927 |           11.1093456408398 |    68.3358023622894 |  20.5548519968708 |     4425675 |
| Isle of Man            |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Italy                  | -1.31844836660481 |            1.414 |                 81.9452097560976 |           20.0909973618083 |    65.7289363852644 |  14.1800662529273 |    59832179 |
| Kosovo                 |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Latvia                 | -4.55213597961080 |            1.453 |                 72.2382926829268 |           17.1863911389844 |    69.0425815911418 |  13.7710272698738 |     2266094 |
| Liechtenstein          |  1.79808929851180 |            1.400 |                 82.6341463414634 |                        NaN |                 NaN |               NaN |       35629 |
| Lithuania              |  2.76144078921502 |            1.470 |                 71.8217073170732 |           15.9677094440150 |    68.7509466357882 |  15.2813439201968 |     3358115 |
| Luxembourg             |  0.03220273485962 |            1.605 |                 80.5246341463415 |           14.0365040657173 |    67.9773784654310 |  17.9861174688517 |      488650 |
| Macedonia              |  4.80000000000011 |            1.438 |                 74.2113170731707 |           11.5845850425847 |    69.9825898844976 |  18.4328250729177 |     2041342 |
| Malta                  |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Moldova                |  7.76484641287229 |            1.495 |                 68.4371463414634 |           11.1369548727738 |    71.6754849214449 |  17.1875602057813 |     3633369 |
| Monaco                 |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Republic of Montenegro |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Netherlands            |  1.99580842581707 |            1.775 |                 80.4007317073171 |           14.7235949405444 |    67.3305328508120 |  17.9458722086436 |    16445593 |
| Norway                 |  1.81507058553292 |            1.960 |                 80.7414634146342 |           14.6455888097593 |    66.2064766744808 |  19.1479345157599 |     4768212 |
| Poland                 |  5.00408460108383 |            1.390 |                 75.5331707317073 |           13.3256480555872 |    71.4634305149354 |  15.2109214294774 |    38125759 |
| Portugal               | -0.03467455605676 |            1.374 |                 79.2497560975610 |           17.5012814880078 |    67.1365409199047 |  15.3621775920875 |    10622413 |
| San Marino             |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Serbia                 |  5.51795169957776 |            1.400 |                 73.6365853658537 |           14.5167655385706 |    67.6335858157006 |  17.8496486457288 |     7350221 |
| Slovakia               |  6.17046824289093 |            1.320 |                 74.8107317073171 |           11.9677699353106 |    72.3868259638361 |  15.6454041008533 |     5406626 |
| Slovenia               |  3.49251997044142 |            1.528 |                 78.9739024390244 |           16.0267556735963 |    70.1117152095851 |  13.8615291168186 |     2021316 |
| Spain                  |  0.85776978982683 |            1.461 |                 81.0880487804878 |           16.9394050582152 |    68.3398363315641 |  14.7207586102207 |    45555716 |
| Sweden                 | -0.40879886604371 |            1.910 |                 81.2371707317073 |           17.7223651519496 |    65.5617228818501 |  16.7159119662004 |     9219637 |
| Switzerland            |  1.89715399119828 |            1.480 |                 82.1617073170732 |           16.6721873799941 |    67.8197089730996 |  15.5081036469063 |     7647675 |
| Ukraine                |  2.09999999999999 |            1.390 |                 68.2514634146342 |           15.9037623084261 |    70.1546462864768 |  13.9415914050970 |    46258200 |
| United Kingdom         |  0.54791121956627 |            1.940 |                 79.9033658536585 |           16.3019124620612 |    66.1561282590033 |  17.5419592789355 |    61406928 |
| Montenegro             |  6.89999999999999 |            1.642 |                 74.0975365853659 |           12.8497239486590 |    67.5957824239814 |  19.5544936273596 |      622344 |
| Isle of Man            |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |       80543 |
| Romania                |  9.42580218461200 |            1.350 |                 73.3734146341464 |           14.8579664297396 |    69.8993946432444 |  15.2426389270160 |    21513622 |
```

**`OUTPUT`**

| Country                |    GDP growth (%) | Births per woman | Life expectancy at birth (years) | Population ages >= 65 (%) | Pop. ages 15-64 (%) | Pop ages 0-14 (%) | Pop (total) |
| ---------------------- | -----------------:| ----------------:| --------------------------------:| --------------------------:| -------------------:| -----------------:| -----------:|
| Albania                |               7.5 |            1.858 |                 76.6337073170732 |            9.3330694913874 |    66.4522208535245 |  24.2147096550882 |     3143291 |
| Andorra                |  3.57073718591123 |            1.260 |                              NaN |                        NaN |                 NaN |               NaN |     83810.5 |
| Austria                |  2.17880778069679 |            1.414 |                 80.4475609756098 |           17.0078802490015 |    67.7942859199021 |  15.1978338310964 |     8336926 |
| Byelarus               | 11.29603925282670 |            1.420 |                 70.6328780487805 |           13.8161084682917 |    71.3440867491758 |  14.8398047825325 |     9680850 |
| Belgium                |  1.00416891576425 |            1.820 |                 80.1095609756098 |           17.2425951179457 |    65.9073170003941 |  16.8500878816601 |    10708433 |
| Bosnia and Herzegovina |  5.41999999999929 |            1.209 |                 75.1063170731708 |           13.7875788575916 |    70.5586044787057 |  15.6538166637027 |     3773100 |
| Bulgaria               |  6.21712220063873 |            1.478 |                 73.3165853658537 |           17.3328904412356 |    69.2610054713067 |  13.4061040874577 |     7623395 |
| Channel Islands        |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Croatia                |  2.35925308110710 |            1.470 |                 75.9121951219512 |           17.1754953634927 |    67.5174504975681 |  15.3070541389392 |     4434000 |
| Czech Republic         |  2.46366103329814 |            1.497 |                 77.2112195121951 |           14.6644147081870 |    71.1889763214880 |  14.1466089703250 |    10424336 |
| Denmark                | -0.86969912719333 |            1.892 |                 78.7004878048781 |           15.9364325701275 |    65.6692750948847 |  18.3942923349878 |     5493621 |
| Estonia                | -5.12891873578752 |            1.661 |                 73.9731707317073 |           16.9573479430650 |    68.0747344729978 |  14.9679175839372 |     1340675 |
| Faroe Islands          |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |       48511 |
| Finland                |  0.92209645431238 |            1.846 |                 79.7919512195122 |           16.5283868561977 |    66.6427434111131 |  16.8288697326892 |     5313399 |
| France                 |  0.21695181782435 |            1.998 |                 81.5204878048781 |           16.6134150592142 |    64.9880225189894 |  18.3985624217964 |    62277432 |
| Germany                |  0.98801573506542 |            1.376 |                 80.0885365853659 |           19.9652972040776 |    66.3351760329956 |  13.6995267629268 |    82110097 |
| Greece                 |  2.01498162894308 |            1.506 |                 79.9631707317073 |           18.1870521529388 |    67.5883962990861 |  14.2245515479751 |    11237094 |
| Hungary                |  0.59999999999994 |            1.352 |                 74.0090243902439 |           16.0592099507043 |    68.9813743902960 |  14.9594156589996 |    10038188 |
| Iceland                |  0.95512219949856 |            2.140 |                 81.5751219512195 |           11.6851788453979 |    67.3938402627208 |  20.9209808918813 |      317414 |
| Ireland                | -3.03575424255612 |            2.100 |                 79.8568292682927 |           11.1093456408398 |    68.3358023622894 |  20.5548519968708 |     4425675 |
| Isle of Man            |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Italy                  | -1.31844836660481 |            1.414 |                 81.9452097560976 |           20.0909973618083 |    65.7289363852644 |  14.1800662529273 |    59832179 |
| Kosovo                 |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Latvia                 | -4.55213597961080 |            1.453 |                 72.2382926829268 |           17.1863911389844 |    69.0425815911418 |  13.7710272698738 |     2266094 |
| Liechtenstein          |  1.79808929851180 |            1.400 |                 82.6341463414634 |                        NaN |                 NaN |               NaN |       35629 |
| Lithuania              |  2.76144078921502 |            1.470 |                 71.8217073170732 |           15.9677094440150 |    68.7509466357882 |  15.2813439201968 |     3358115 |
| Luxembourg             |  0.03220273485962 |            1.605 |                 80.5246341463415 |           14.0365040657173 |    67.9773784654310 |  17.9861174688517 |      488650 |
| Macedonia              |  4.80000000000011 |            1.438 |                 74.2113170731707 |           11.5845850425847 |    69.9825898844976 |  18.4328250729177 |     2041342 |
| Malta                  |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Moldova                |  7.76484641287229 |            1.495 |                 68.4371463414634 |           11.1369548727738 |    71.6754849214449 |  17.1875602057813 |     3633369 |
| Monaco                 |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Republic of Montenegro |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Netherlands            |  1.99580842581707 |            1.775 |                 80.4007317073171 |           14.7235949405444 |    67.3305328508120 |  17.9458722086436 |    16445593 |
| Norway                 |  1.81507058553292 |            1.960 |                 80.7414634146342 |           14.6455888097593 |    66.2064766744808 |  19.1479345157599 |     4768212 |
| Poland                 |  5.00408460108383 |            1.390 |                 75.5331707317073 |           13.3256480555872 |    71.4634305149354 |  15.2109214294774 |    38125759 |
| Portugal               | -0.03467455605676 |            1.374 |                 79.2497560975610 |           17.5012814880078 |    67.1365409199047 |  15.3621775920875 |    10622413 |
| San Marino             |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |         NaN |
| Serbia                 |  5.51795169957776 |            1.400 |                 73.6365853658537 |           14.5167655385706 |    67.6335858157006 |  17.8496486457288 |     7350221 |
| Slovakia               |  6.17046824289093 |            1.320 |                 74.8107317073171 |           11.9677699353106 |    72.3868259638361 |  15.6454041008533 |     5406626 |
| Slovenia               |  3.49251997044142 |            1.528 |                 78.9739024390244 |           16.0267556735963 |    70.1117152095851 |  13.8615291168186 |     2021316 |
| Spain                  |  0.85776978982683 |            1.461 |                 81.0880487804878 |           16.9394050582152 |    68.3398363315641 |  14.7207586102207 |    45555716 |
| Sweden                 | -0.40879886604371 |            1.910 |                 81.2371707317073 |           17.7223651519496 |    65.5617228818501 |  16.7159119662004 |     9219637 |
| Switzerland            |  1.89715399119828 |            1.480 |                 82.1617073170732 |           16.6721873799941 |    67.8197089730996 |  15.5081036469063 |     7647675 |
| Ukraine                |  2.09999999999999 |            1.390 |                 68.2514634146342 |           15.9037623084261 |    70.1546462864768 |  13.9415914050970 |    46258200 |
| United Kingdom         |  0.54791121956627 |            1.940 |                 79.9033658536585 |           16.3019124620612 |    66.1561282590033 |  17.5419592789355 |    61406928 |
| Montenegro             |  6.89999999999999 |            1.642 |                 74.0975365853659 |           12.8497239486590 |    67.5957824239814 |  19.5544936273596 |      622344 |
| Isle of Man            |               NaN |              NaN |                              NaN |                        NaN |                 NaN |               NaN |       80543 |
| Romania                |  9.42580218461200 |            1.350 |                 73.3734146341464 |           14.8579664297396 |    69.8993946432444 |  15.2426389270160 |    21513622 |

## **Graph** 

- When the values in the first column and the header of the table are equal, the interpreter treats the table as an adjacency matrix, which defines the connections between nodes in a graph.

- If the values are symmetrical across the diagonal, it indicates an undirected graph, where the connections between nodes are bidirectional and have no inherent direction.

- If the values differ, it represents a directed graph, where the connections between nodes have a specific direction, and the values may indicate the strength or weight of these connections.

**`Example:`**

- The provided tables represent both undirected and directed graphs.

- In the undirected graph, the connections between nodes are symmetrical, indicating that the graph is bidirectional.

- In the directed graph, the connections between nodes may have different values, indicating the strength or weight of the connections, and the graph has a specific direction for each connection.

**`undirected`**

```
| Graph |  A  |  B  |  C  |  D  |  E  |
|:----- |:---:|:---:|:---:|:---:|:---:|
| A     |  0  |  1  |  0  |  1  |  0  |
| B     |  1  |  0  |  0  |  1  |  0  |
| C     |  0  |  0  |  0  |  0  |  0  |
| D     |  1  |  1  |  0  |  0  |  1  |
| E     |  0  |  0  |  0  |  1  |  0  |
```

**`directed`**


```
| Graph |  A  |  B  |  C  |  D  |  E  |
|:----- |:---:|:---:|:---:|:---:|:---:|
| A     |  0  | 12  |  0  |  1  |  0  |
| B     | -22 |  0  |  0  | 0.4 |  0  |
| C     |  0  |  0  |  0  |  0  |  0  |
| D     |  2  | 12  |  0  |  0  |  1  |
| E     |  0  |  0  |  0  |  2  |  0  |
```

**`OUTPUT`**

**`undirected`**


| Graph |  A  |  B  |  C  |  D  |  E  |
|:----- |:---:|:---:|:---:|:---:|:---:|
| A     |  0  |  1  |  0  |  1  |  0  |
| B     |  1  |  0  |  0  |  1  |  0  |
| C     |  0  |  0  |  0  |  0  |  0  |
| D     |  1  |  1  |  0  |  0  |  1  |
| E     |  0  |  0  |  0  |  1  |  0  |


**`directed`**


| Graph |  A  |  B  |  C  |  D  |  E  |
|:----- |:---:|:---:|:---:|:---:|:---:|
| A     |  0  | 12  |  0  |  1  |  0  |
| B     | -22 |  0  |  0  | 0.4 |  0  |
| C     |  0  |  0  |  0  |  0  |  0  |
| D     |  2  | 12  |  0  |  0  |  1  |
| E     |  0  |  0  |  0  |  2  |  0  |



### **Sankey** 

- A Sankey diagram is a visualization technique used to depict the flow of something, such as energy, money, or resources, between different entities or processes.

- It consists of nodes, which represent the entities or processes, and flows, which represent the flow of the substance or quantity between these nodes.

- The width of the flows typically represents the quantity or magnitude of the flow.

**`Example:`**

- In the provided Sankey diagram table:

1. Nodes A, B, C, D, and E represent different entities or processes.

2. The numbers in the table represent the flow of something between these entities or processes.

```
| Sankey |  A  |  B  |  C  |  D  |  E  |
|:------ |:---:|:---:|:---:|:---:|:---:|
| A      |     |  2  |     |     |     |
| B      |  3  |     |     |     |     |
| C      |  1  |  1  |     |     |     |
| D      |     |  1  |  1  |     |     |
| E      |  2  |  1  |  1  |  1  |     |
```

**`OUTPUT`**

| Sankey |  A  |  B  |  C  |  D  |  E  |
|:------ |:---:|:---:|:---:|:---:|:---:|
| A      |     |  2  |     |     |     |
| B      |  3  |     |     |     |     |
| C      |  1  |  1  |     |     |     |
| D      |     |  1  |  1  |     |     |
| E      |  2  |  1  |  1  |  1  |     |


## **None **

This table won't be interpreted as any specific visualization type, as it's marked with data-type="none". Therefore, it won't produce any visualization output.

```

| Sankey |  A  |  B  |  C  |  D  |  E  |
|:------ |:---:|:---:|:---:|:---:|:---:|
| A      |     |  2  |     |     |     |
| B      |  3  |     |     |     |     |
| C      |  1  |  1  |     |     |     |
| D      |     |  1  |  1  |     |     |
| E      |  2  |  1  |  1  |  1  |     |
```

**`OUTPUT`**


| Sankey |  A  |  B  |  C  |  D  |  E  |
|:------ |:---:|:---:|:---:|:---:|:---:|
| A      |     |  2  |     |     |     |
| B      |  3  |     |     |     |     |
| C      |  1  |  1  |     |     |     |
| D      |     |  1  |  1  |     |     |
| E      |  2  |  1  |  1  |  1  |     |


## **Attributes** 

- `data-type` You can use the attribute `data-type` to overwrite the automatically identified representation with your desired one. The names can be taken from the presented list, and it is not relevant whether you use lower or upper case. This approach also enables the use of types that cannot be automatically inferred at the moment, such as Sankey or BoxPlot. If you do not want to show tables as diagrams, you can also use `none`, and only the table will be visible.

`data-type="bar|barchart"`

`data-type="boxplot"`

`data-type="funnel"`

`data-type="graph"`

`data-type="heatmap"`

`data-type="line|lineplot"`

`data-type="map"`

`data-type="none"`

`data-type="parallel"`

`data-type="pie|piechart"`

`data-type="radar"`

`data-type="sankey"`

`data-type="scatter|scatterplot"`

- `data-show` Simply add this attribute or set it to true, if you want to visualize your data immediately, without the need to click on the switch button. However, users still retain the ability to switch to the table representation if desired. 

`<!-- data-show -->`

 or 

`<!-- data-show="true" -->`

- `data-transpose:` Similar to the mathematical sense, set this attribute or set it to true if you want to transpose rows and columns. One benefit is that you can, for example, use a PieChart and let your table grow vertically instead of using a horizontal layout.

`<!-- data-transpose --> `

or 

`<!-- data-transpose="true" -->`

`data-title:` By default, the first cell defines the title of your diagram. However, if you prefer larger titles and want to avoid writing gigantic table headers, you can apply this attribute.

`<!-- data-title="Use whatever title you want to ..." -->`

`data-xlabel:` Similarly, as described above, you can also define the strings for the labels, in this case, for the label for the x-axis.

`<!-- data-xlabel="Time in minutes" -->`

`data-ylabel:` Or, in this case label for the y-axis.

`<!-- data-ylabel="Distance in meters" -->`

`data-src:` Currently, this attribute is used to refer to your GeoJSON data if you use the map representation. However, this functionality might change in the future to allow for the loading and visualization of data directly, such as CSV files. See sections Fun with Tables - Map.

`<!-- data-type="map" data-src="https://..." -->`

Be careful when utilizing GeoJSON files from external websites, as this may result in CORS (Cross-Origin Resource Sharing) problems. It's better to store these files in your own projects and refer to them directly to avoid such issues.Here is an example of a source for GeoJSON files.

## **Custom Diagrams with ECharts**

Using LiaScript's `lia-chart` tag, you can create custom diagrams with ECharts directly within your LiaScript document. Here's an example of how to use it:

```
<lia-chart option="{
  title: { text: 'Two Value-Axes in Polar' },
  polar: { center: ['50%', '54%'] },
  tooltip: { trigger: 'axis',
    axisPointer: { type: 'cross' }
  },
  angleAxis: { type: 'value', startAngle: 0 },
  radiusAxis: { min: 0 },
  series: [{ coordinateSystem: 'polar',
    name: 'line',
    type: 'line',
    showSymbol: false,
    data: (function() {
      const data = [];
      for (let i = 0; i <= 360; i++) {
        let t = (i / 180) * Math.PI;
        let r = Math.sin(2 * t) * Math.cos(2 * t);
        data.push([r, i]);
      }
      return data
    })()
  }],
  animationDuration: 2000
}"></lia-chart>
```
- This approach allows you to rebuild nearly every example directly, providing flexibility and ease of customization.

- Additionally, if you need to execute JavaScript or require more interaction with the diagram, you can also use script tags. 

```
$a =$ <script input="range" step="1" min="-1" max="6" value="2"  output="a">@input</script>,
$b =$ <script input="range" step="0.1" min="-10" max="10" value="0"  output="b">@input</script>,
$c =$ <script modify="false" input="range" step="0.1" min="-10" max="10" value="0"  output="c">@input</script>

<script modify="false" run-once style="display: inline-block; width: 100%">
"LIASCRIPT: ### $$f(x) = x^{@input(`a`)} + x * @input(`b`) + @input(`c`)$$"
</script>

<script run-once style="display: inline-block; width: 100%">
function func(x) {
    return Math.pow(x,  @input(`a`)) + @input(`b`) * x + @input(`c`);
}

function generateData() {
    let data = [];
    for (let i = -15; i <= 15; i += 0.01) {
        data.push([i, func(i)]);
    }
    return data;
}

let option = {
    animation: false,
    grid: { top: 40, left: 50, right: 40, bottom: 50 },
    xAxis: {
        name: 'x',
        minorTick: {
            show: true
        },
        splitLine: {
            lineStyle: {
                color: '#999'
            }
        },
        minorSplitLine: {
            show: true,
            lineStyle: {
                color: '#ddd'
            }
        }
    },
    yAxis: {
        name: 'y', min: -10, max: 10,
        minorTick: {
            show: true
        },
        splitLine: {
            lineStyle: {
                color: '#999'
            }
        },
        minorSplitLine: {
            show: true,
            lineStyle: {
                color: '#ddd'
            }
        }
    },
    dataZoom: [{
        show: true,
        type: 'inside',
        filterMode: 'none',
        xAxisIndex: [0],
        startValue: -20,
        endValue: 20
    }, {
        show: true,
        type: 'inside',
        filterMode: 'none',
        yAxisIndex: [0],
        startValue: -20,
        endValue: 20
    }],
    series: [
        {
            type: 'line',
            showSymbol: false,
            clip: true,
            data: generateData()
        }
    ]
}
"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"
</script>
```

- In this example, we define a mathematical function func(x) and use it to generate data for a line series in the chart. We then create an ECharts option object and pass it to the lia-chart tag to visualize the data.

**`OUTPUT`**

<lia-chart option="{
  title: { text: 'Two Value-Axes in Polar' },
  polar: { center: ['50%', '54%'] },
  tooltip: { trigger: 'axis',
    axisPointer: { type: 'cross' }
  },
  angleAxis: { type: 'value', startAngle: 0 },
  radiusAxis: { min: 0 },
  series: [{ coordinateSystem: 'polar',
    name: 'line',
    type: 'line',
    showSymbol: false,
    data: (function() {
      const data = [];
      for (let i = 0; i <= 360; i++) {
        let t = (i / 180) * Math.PI;
        let r = Math.sin(2 * t) * Math.cos(2 * t);
        data.push([r, i]);
      }
      return data
    })()
  }],
  animationDuration: 2000 
  }"></lia-chart>





$a =$ <script input="range" step="1" min="-1" max="6" value="2"  output="a">@input</script>,
$b =$ <script input="range" step="0.1" min="-10" max="10" value="0"  output="b">@input</script>,
$c =$ <script modify="false" input="range" step="0.1" min="-10" max="10" value="0"  output="c">@input</script>

<script modify="false" run-once style="display: inline-block; width: 100%">
"LIASCRIPT: ### $$f(x) = x^{@input(`a`)} + x * @input(`b`) + @input(`c`)$$"
</script>

<script run-once style="display: inline-block; width: 100%">
function func(x) {
    return Math.pow(x,  @input(`a`)) + @input(`b`) * x + @input(`c`);
}

function generateData() {
    let data = [];
    for (let i = -15; i <= 15; i += 0.01) {
        data.push([i, func(i)]);
    }
    return data;
}

let option = {
    animation: false,
    grid: { top: 40, left: 50, right: 40, bottom: 50 },
    xAxis: {
        name: 'x',
        minorTick: {
            show: true
        },
        splitLine: {
            lineStyle: {
                color: '#999'
            }
        },
        minorSplitLine: {
            show: true,
            lineStyle: {
                color: '#ddd'
            }
        }
    },
    yAxis: {
        name: 'y', min: -10, max: 10,
        minorTick: {
            show: true
        },
        splitLine: {
            lineStyle: {
                color: '#999'
            }
        },
        minorSplitLine: {
            show: true,
            lineStyle: {
                color: '#ddd'
            }
        }
    },
    dataZoom: [{
        show: true,
        type: 'inside',
        filterMode: 'none',
        xAxisIndex: [0],
        startValue: -20,
        endValue: 20
    }, {
        show: true,
        type: 'inside',
        filterMode: 'none',
        yAxisIndex: [0],
        startValue: -20,
        endValue: 20
    }],
    series: [
        {
            type: 'line',
            showSymbol: false,
            clip: true,
            data: generateData()
        }
    ]
}
"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"
</script>

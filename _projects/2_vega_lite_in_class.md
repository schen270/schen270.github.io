---
name: Homework 6
tools: [Python, HTML, vega-lite, Altair]
image: assets/pngs/cars.png
description: This project demonstrates the creation of two visualizations using Python, Altair, and Vega-Lit, showcasing licensing data. 
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Interactive Visualization: License Status by State

<vegachart schema-url="{{ site.baseurl }}/assets/json/license_map.json" style="width: 100%"></vegachart>

<p>
<br>
For this visualization, I'm trying to do the analysis of license type and license status in relation to the number of licenses in various states. This visualization contains interactive elements: a user can select a range in the first plot, a heatmap, that will dynamically filter and update the second plot, a bar chart, with the license status and number of each state selected in the first plot.
<br>
<br>
License Type is discrete categories, so I have used encoding as an ordinal scale. License Type has also been binned to decrease the number of categories. This helps for clarity. The State variable is encoded as an ordinal scale, too, because it needs to represent each state as an entity. Color encoding has been done on a quantitative scale representing counts of licenses in each state. The intensity will show the relative number of licenses in each state, a darker will mean higher counts. I employed the brush selection to enhance plot interactivity. 
<br>
<br>
Homework #5, the visualizations were built using Streamlit, which does not support interactive plots in the same way as Jekyll with Vega-Lite. In Homework #6, using Jekyll for web development allows us to integrate and interactive plots using the vegachart HTML tag, enabling better interaction and embedding within a static website.
</p>

# Visualization: Licenses Over Time

<vegachart schema-url="{{ site.baseurl }}/assets/json/license_trend.json" style="width: 100%"></vegachart>

<p>
<br>
In this plot, I am visualizing the distribution of licenses across different license statuses. Specifically, it shows how many licenses exist for each type of status. The x-axis represents the count of licenses, while the y-axis lists the license statuses. 
<br>
<br>
I used a quantitative (Q) encoding for the x-axis to display the count of licenses for each license status. This helps show the number of licenses varies across different license statuses. For the y-axis, I used a nominal (N) encoding for licnese status, as these are categorical values ("active", etc.). Each status is placed along the y-axis as a separate category. I didn't use any color encoding, as the focus is on the count of licenses for each license status. I decided to keep the chart simple without color to emphasize the counts. If i were to add color, I might use it to represent additional variables such as license type or region, but I didn't include that in this plot.
<br>
<br>
There were no complex data transformations in this plot. I simply grouped the data by License Status and counted the number of licenses per status using count(). The data was already clean and structured, so no significant changes were needed. 
<br>
<br>
This plot is different from Homework #5 in several ways. For Homework #5, I used Streamlit to create an interactive visualization with various widgets, but in this plot, I'm using Altair within a Jekyll page, which is not interactive beyond basic zooming and panning.
</p>

Below is where we can put some links to both the data and the analysis code as buttons:

```
<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://blog.4dcu.be/programming/2021/05/03/Interactive-Visualizations.html" text="The Analysis" %}
</div>
```

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/schen270/schen270.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>


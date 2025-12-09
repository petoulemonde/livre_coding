Title : The Power of Pandas Plots: Backends

Sous-titre : Create interactive graphics from Pandas effortlessly

## Index

1. Context
2. Backends  
    2.1. Matplotlib  
    2.2. Plotly  
    2.3. Hvplot
3. Discussion
4. A word before you go

# 1. Context

Python has a multitude of visualization packages, the three best known of which are: [Matplotlib](https://matplotlib.org/) (and seaborn), [Plotly](https://plotly.com/), and [Hvplot](https://hvplot.holoviz.org/). Each of these 3 packages has its strengths, but requires an entry cost to pay to learn how to use this package, sometimes quite substantial.

The idea for this article came to me when I discovered the [Mind Map of Pandas Methods](https://blog.dailydoseofds.com/p/interactive-mind-map-of-all-pandas) offered by the [Daily Dose of Data science newsletter](https://blog.dailydoseofds.com/) (a newsletter that I highly recommend). I was then discovering the Hvplot visualization package at the same time. I thought the idea of switching from one visualisation backend to another as easily as with Hvplot was brilliant ([here](https://hvplot.holoviz.org/user_guide/Plotting_with_Plotly.html) is an example to switch from Hvplot to Plotly from Hvplot). Seeing that we could do it with pandas too, I found the idea too interesting not to share it.

Pandas is at the heart of data science in Python, and we all know how to use it. But Matplotlib integrated into Pandas is aging, and is being overtaken both in ease of use and in presentation by other packages. The power of the Pandas visualization backend allows you to take advantage of the latest visualization packages for data exploration and result rendering, without having to invest time in learning these packages, which are nevertheless super powerful!

# 2. Backends

Pandas was built on 2 packages, Numpy and Matplotlib. This explains why we use Matplotlib scripts to generate graphs, and therefore the generated graphs are matplotlib graphs.

Since its creation, Pandas has evolved and offers the user the possibility to modify the visualization backend used by Pandas.

The 6 available backends that I found during my research are:

- Plotnine (ggplot2)
- Plotly
- Altair
- Holoviews
- Hvplot
- Pandas_bokeh
- Matplotlib (default backend)

There are several methods available to change a backend::

- 2 global methods :

```python
pd.set_option("plotting.backend", '<name of backend>')  
# OR  
pd.options.plotting.backend = '<name of backend>'  
```

- 1 local method :

```python
df.plot(backend='<name of backend>', x='...')
```

Note: Changing the backend requires Pandas >= 0.25, and sometimes requires specific dependencies to be important, such as with Hvplot below.

Here are 2 examples:

- with Plotly :

```python
import pandas as pd # Basic packages  
  
pd.options.plotting.backend = "plotly"  
  
df = pd.DataFrame(dict(a=[1,3,2], b=[3,2,1]))  
fig = df.plot()  
fig.show()
```

- with Hvplot :

```python
import numpy as np  
import pandas as pd # Basic packages  
  
import hvplot  
import hvplot.pandas # ! Specific dependency to install  
  
pd.options.plotting.backend = 'hvplot' # Backend modification  
  
data = np.random.normal(size=[50, 2])  
df = pd.DataFrame(data, columns=['x', 'y'])  
  
df.plot(kind='scatter', x='x', y='y') # Plotting
```

## **2.1. Matplotlib**

[Matplotlib](https://matplotlib.org/) is the default visualization backend of Pandas. In other words, if you don’t specify a backend, Matplotlib will be used. It is an efficient package to quickly visualize your data to explore it or extract results, but it is aging and is being caught up in both ease of use and rendering power by other packages.

The advantage of Matplotlib is that since Pandas has been built on Matplotlib since its creation, the integration of Matplotlib into pandas is perfect, all matplotlib functions can be used in Pandas.

As a reminder, here are the 11 Matplotlib display methods integrated into Pandas :

- “area” for area plots,
- “bar” for vertical bar charts,
- “barh” for horizontal bar charts,
- “box” for box plots,
- “hexbin” for hexbin plots,
- “hist” for histograms,
- “kde” for kernel density estimate charts,
- “density” an alias for “kde”,
- “line” for line graphs,
- “pie” for pie charts,
- “scatter” for scatter plots.

## 2.2. Plotly

[Plotly](https://plotly.com/) is a visualization package developed by the company Plotly. The company has developed the framework Plotly.js, to allow interactive visualization of data within Python. The company Plotly also offers the Python dashboarding package [Dash](https://dash.plotly.com/.

To use Plotly from Pandas, simply import _Plotly express_ and change the backend:

```python
import pandas as pd  
import plotly.express as px # Import packages  
  
df = pd.read_csv("iris.csv")  
  
# Modifying locally Pandas backend  
df.plot.scatter(backend = "plotly", x = "sepal.length", y = "sepal.width")
```

Pandas returns an object with the same type than Plotly:

```python
df.plot.scatter(backend = "plotly", x = "sepal.length", y = "sepal.width")   
# → <class 'plotly.graph_objs._figure.Figure'>  
  
px.scatter(x=df["sepal.length"], y = df["sepal.width"])   
# → <class 'plotly.graph_objs._figure.Figure'>
```

The advantage is that you can directly integrate a graphic created in Pandas into the Plotly universe, especially Dash!  
One limitation is that Plotly’s integration with Pandas is not yet perfect as detailed on the Plotly website ([details on the Plotly website](https://plotly.com/python/pandas-backend/)).

## 2.3. Hvplot

[Hvplot](https://hvplot.holoviz.org/) is an interactive visualization package based on bokeh.  
It is an exciting package, which I discovered some time ago and which continues to fascinate me, as much for Hvplot which integrates the notion of backend as in Pandas as for the [Holoviz suite](https://holoviz.org/) and related packages like [Panel](https://panel.holoviz.org/) to create dynamic client-side websites.

Without even the notion of Pandas backend, Hvplot doesn’t require over-learning to start being used, just replace _.plot()_ of Pandas with _.hvplot()_:

```python
import pandas as pd  
import hvplot  
  
df = pd.read_csv("iris.csv")  
  
# Plot with Pandas  
df.plot.scatter(backend = "hvplot", x = "sepal.length", y = "sepal.width")   
  
# Same plot with hvplot  
df.hvplot.scatter(backend = "hvplot", x = "sepal.length", y = "sepal.width") 
```

Using the Hvplot backend is done in the same way as for the Plotly backend, you just need to import a dependency of the Hvplot package:

```python
import numpy as np  
import pandas as pd # Basic packages  
  
import hvplot   
import hvplot.pandas # Specific dependency to install  
  
pd.options.plotting.backend = 'hvplot' # Backend modification  
  
data = np.random.normal(size=[50, 2])  
df = pd.DataFrame(data, columns=['x', 'y'])  
  
df.plot(kind='scatter', x='x', y='y') # Plotting
```

Like Plotly, charts generated from Pandas with the hvplot backend are of type Hvplot :

```python
df.plot.scatter(backend = "hvplot", x = "sepal.length", y = "sepal.width")   
# → <class 'holoviews.element.chart.Curve'>  
  
df.hvplot.scatter(backend = "hvplot", x = "sepal.length", y = "sepal.width")   
# → <class 'holoviews.element.chart.Curve'>
```

Hvplot is part of the extremely powerful Holoviz suite with many other associated tools to push data analysis very far, i.e. tools like [Panel](https://panel.holoviz.org/), [geoviews](https://geoviews.org/), [datashader](https://datashader.org/) and others. This type of concordance allows to create graphs from pandas and still be able to take advantage of the Holoviz suite.

# 3. Conclusion

Pandas backends are an extremely efficient solution to discover and take advantage of the latest Python visualization packages without having to invest time: in 18 characters including spaces, it is possible to locally transform a standard matplotlib graph into an interactive Plotly graph, and therefore to take advantage of all the benefits of this type of visualization.

However, this solution has certain limitations: it is not suited to highly advanced visualisation objectives that require a great deal of customisation such as advanced visualization in data journalism, because the integration of packages in Pandas is not yet perfect. In addition, this solution only covers visualization packages built on-top of Pandas, and excludes other visualization solutions such as D3.js.

Hvplot is currently my favorite package for visualization: it is extremely easy to get started with at first, works with all the major data manipulation packages (Polars, Dask, Xray, …) and is part of a continuum of applications that allows you to go from graphs to dynamic full client-side websites.

# 4. A word before you go

During my research, I didn’t find as much documentation as I expected. I think the concept is great, so I expected a lot of articles. So feel free to tell me in the comments if you find this solution really useful, or if it’s just a cool thing with no real use.

Thanks for reading!
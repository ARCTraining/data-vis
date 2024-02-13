# Understanding composition: bar charts

Bar charts are valuable tools for displaying and comparing categorical data. They visually represent the distribution or composition of data across various categories, enabling easy identification of patterns, trends, and relationships. Bar charts are effective in conveying information in a clear and concise manner, making them a popular choice for communicating data insights to a wide audience.

While making a series of example bar charts, we will discuss visual encoding in this context

## Example data

For this bar plot, we will be using the following simple dataframe, with numerical values across different categories:

| Category | Results A | Results B |
|:--|:--|:--|
| Cat 1 | 1 | 2 |
| Cat 2 | 27 | 35 |
| Cat 3 | 32 | 15 |
| Cat 4 | 15 | 18 |

We will plot these in a variety of different ways, highlighting why different ways of plotting are useful in different situations, and conversely, how they could mislead you or your audience. Later, we will also look at some other categorical plot types that are possible.

## Create data set

First, import the required packages:

```python
# Import necessary libraries
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
```

Then, create the data frame:

```python
categories = ["Cat 1", "Cat 2", "Cat 3", "Cat 4"]
results_a = [1, 27, 32, 15]
results_b = [2, 35, 15, 18]

data = pd.DataFrame({"Results A": results_a,
                     "Results B": results_b},
                    index=categories)
```


## Basic bar plot using Pandas

For our initial example, we want to create a bar plot with two different groupings: this will show the categories "Cat 1" to "Cat 4" on the x-axis, with colours differentiating "Results A" and "Results B".

We will later use seaborn to build a bar plot, but for now we are going to use a built-in function from pandas as this allows us to create a stacked bar plot.

```python
# Create figure and axes
fig, ax = plt.subplots()

# pandas.plot with option "bar" to create barplot
data.plot(kind="bar", ax=ax, stacked=True) # can toggle "stacked"

# Set labels
ax.set_xlabel("Category")
ax.set_ylabel("Count")
```

|![image](figs/barplot1.png) | 
|:--| 
| Our basic example stacked bar plot. *Alt text: a stacked bar plot with three categorical groupings on the x axis: "Cat 1", "Cat 2", "Cat 3" and "Cat 4", and two groupings shown by colour (blue and orange): "Results A" and "Results B". The y axis shows count, scaled from 0&ndash;65.* |
|![image](figs/barplot2.png) | 
| The same data as above, but with bars staggered instead of stacked. *Alt text: a bar plot with three categorical groupings on the x axis: "Cat 1", "Cat 2", "Cat 3" and "Cat 4", and two groupings shown by colour (blue and orange): "Results A" and "Results B". The y axis shows count, scaled from 0&ndash;65.* |

## Visual encoding

As we discussed in previous sessions, it is a good idea to have a few different methods of distinguishing categories of data, and not to rely solely on colour. In the case of a bar plot, we are a little limited in that we do not have a choice of line style or marker shape to quickly differentiate different data series.

Before we do anything else, let's just pick a better colour scheme from [Color Brewer](https://colorbrewer2.org/#type=diverging&scheme=PuOr&n=5). We can check how well this colour palette will work using [Viz Palette](https://projects.susielu.com/viz-palette?colors=[%22#e66101%22,%22#b2abd2%22]&backgroundColor=%22white%22&fontColor=%22black%22&mode=%22normal%22) to test it in greyscale and for a range of simulated colour sight difficulties.

Once we've picked a palette, we can define this in Python:

`new_palette = ["#e66101","#b2abd2"]`

This can then be used by simply adding the `color` variable to the function call (note that Python uses American spelling):

```python
data.plot(kind="bar", ax=ax, color=new_pal)
```
|![image](figs/barplot3.png) | 
|:--| 
| Our basic example bar plot, with a Color Brewer palette. These colours are better distinguishable in greyscale and with a colour vision deficiency. *Alt text: a stacked bar plot with three categorical groupings on the x axis: "Cat 1", "Cat 2", "Cat 3" and "Cat 4", and two groupings shown by colour (orange and lilac): "Results A" and "Results B". The y axis shows count, scaled from 0&ndash;65.* |


We can also add a pattern or "hatch" to the bars to further help distinguish them from each other. Unfortunately, it's a little bit more complex to add *different* hatch patterns to different categories. To add a basic hatch, just modify the `plot` function call:

```python
data.plot(kind="bar", ax=ax, color=new_pal, hatch="//")
```

To change the colour of the hatch, it's easiest to just modify the `edgecolor` argument:

```python
data.plot(kind="bar", ax=ax, color=new_pal, hatch=".", edgecolor="white")
```

Try out some of these hatches on your plot:

```python
hatches = [
    '/', '\\', '|', '-', '+', 'x', 'o', 'O', '.', '*',
    '//', '\\\\', '||', '--', '++', 'xx', 'oo', 'OO', '..', '**',
    '/o', '\\|', '|*', '-\\', '+o', 'x*', 'o-', 'O|', 'O.', '*-',
]
```

Note that the hatches apply to all bars: not very useful for distinguishing different categories. We can fix this by cycling through a list of different hatch patterns (with the same number of hatch patterns as there are categories). In order to make this a little easier, I've built a small **function** to do this for you. You just need to give it an ax (set up when you run `fig, ax = plt.subplots()`, and a list of hatches):

```python
def apply_hatch_pattern(ax, hatch_patterns):
    bars = ax.patches
    hatches = []
    for h in hatch_patterns:
        for i in range(int(len(bars)/len(hatch_patterns))):
            hatches.append(h)
    for bar, hatch in zip(bars, hatches):
        bar.set_hatch(hatch)
```

You can define this function by putting it in a cell and running it. Then you can use it by calling `apply_hatch_pattern(ax, hatch_patterns)` after you've created your plot. While the pandas plot function automatically builds a legend for you, you must add it again manually because it will not have the hatches overlaid.

```python
fig, ax = plt.subplots()

data.plot(kind="bar", ax=ax, color=new_pal, stacked=True, edgecolor="white")

apply_hatch_pattern(ax, hatch_patterns=["*", "//"])
ax.set_xlabel("Category")
ax.set_ylabel("Count")
ax.legend()
```

|![image](figs/barplot4.png) | 
|:--| 
| Our example stacked bar plot, with a Color Brewer palette and hatch markings. *Alt text: a stacked bar plot with three categorical groupings on the x axis: "Cat 1", "Cat 2", "Cat 3" and "Cat 4", and two groupings shown by colour (orange and lilac) and hatch pattern (diagonal lines,and stars): "Results A" and "Results B". The y axis shows count, scaled from 0&ndash;65.* |

## Comparing composition

When comparing the composition of a group, for example the proportion of "Results A" vs. "Results B" in each of the categories, it can be difficult when the absolute number of results varies largely, for example between "Cat 1" and "Cat 2". We can visualise the data in a different way to better pick out the proportions per category by normalising the values in each category to 100:

```python
data["Total"] = data["Results A"] + data["Results B"]
data["Results A (%)"] = (data["Results A"]/data["Total"]) * 100
data["Results B (%)"] = (data["Results B"]/data["Total"]) * 100
```

This code adds the columns `"Total"`, `"Results A (%)"` and `"Results A (%)"` to our dataframe:

| Category | Results A | Results B | Total | Results A (%) | Results B (%) |
|:--|:--|:--|:--|:--|:--|
| Cat 1 | 1 | 2 | 3 | 33.333333 | 66.666667 |
| Cat 2 | 27 | 35 | 62 | 43.548387 | 56.451613 |
| Cat 3 | 32 | 15 | 47 | 68.085106 | 31.914894 |
| Cat 4 | 15 | 18 | 33 | 45.454545 | 54.545455 |

We can now plot these new columns. Because we *only* want to plot `"Results A (%)"` and `"Results A (%)"` and not the entire dataframe, we now need to specify just these columns. In the same way that we can pull out one column of a dataframe by using square brackets (like `data["Total"]`), we can also include a **list** of column names like `["Results A (%)", "Results B (%)"]`:

```python
fig, ax = plt.subplots()
data[["Results A (%)", "Results B (%)"]].plot(kind="bar",
                                              stacked=True,
                                              ax=ax,
                                              color=new_pal,
                                              edgecolor="white")

apply_hatch_pattern(ax, hatch_patterns=["*", "//"])

ax.set_xlabel("Category")
ax.set_ylabel("Proportion [%]")
```

|![image](figs/barplot5.png) | 
|:--| 
| Our example stacked bar plot, now shown as a proportion of 100 %. *Alt text: a stacked bar plot with three categorical groupings on the x axis: "Cat 1", "Cat 2", "Cat 3" and "Cat 4", and two groupings shown by colour (orange and lilac) and hatch pattern (diagonal lines,and stars): "Results A" and "Results B". The y axis shows proportion, scaled from 0&ndash;100 %.* |

Because the bar plots now fill the entire axes area, the legend awkwardly overlaps, so we need to move it outside of the plot. Also, because we didn't manually call `ax.legend()`, the legend has not updated to include the hatch patterns.

We can move the legend by adding arguments into the `ax.legend()` function call:

`ax.legend(bbox_to_anchor=(0.5, 1.15), loc='upper center', ncol=2, frameon=False)`,

where `bbox_to_anchor` tells you where on the "bounding box" (the axes area) you want the legend positioned (so in this case, 0.5 along x - so centered horizontally, then 1.15 on y - so just above the plotting area); `loc` tells you where on the legend is being positioned here (so the upper centre of the legend box); `ncol` defines that there should be two columns as opposed to the default of one column and multiple rows; and finally `frameon = False` switched off the grey box around the legend.

We can also add seaborn's despine function to tidy up the plot:

```python
fig, ax = plt.subplots()
data[["Results A (%)", "Results B (%)"]].plot(kind="bar",
                                              stacked=True,
                                              ax=ax,
                                              color=new_pal,
                                              edgecolor="white")

apply_hatch_pattern(ax, hatch_patterns=["*", "//"])

ax.set_xlabel("Category")
ax.set_ylabel("Proportion [%]")
ax.legend(bbox_to_anchor=(0.5, 1.15), loc='upper center', ncol=2, frameon=False)
sns.despine()
```

|![image](figs/barplot6.png) | 
|:--| 
| Our example stacked bar plot, now shown as a proportion of 100 %. *Alt text: a stacked bar plot with three categorical groupings on the x axis: "Cat 1", "Cat 2", "Cat 3" and "Cat 4", and two groupings shown by colour (orange and lilac) and hatch pattern (diagonal lines,and stars): "Results A" and "Results B". The y axis shows proportion, scaled from 0&ndash;100 %.* |

## Possible pitfalls


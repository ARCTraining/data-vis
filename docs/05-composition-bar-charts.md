# Understanding composition: bar charts

For this bar plot, we will be using the following simple dataframe, with numerical values across different categories:

| Category | Results A | Results B |
|:--|:--|:--|
| Cat 1 | 1 | 2 |
| Cat 2 | 27 | 35 |
| Cat 3 | 32 | 15 |
| Cat 4 | 15 | 18 |

We will plot these in a variety of different ways, highlighting why different ways of plotting are useful in different situations, and conversely, how they could mislead you or your audience. Later, we will also look at some other categorical plot types that are possible.

# Create data set

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


# Basic bar plot using Pandas

For our initial example, we want to create a bar plot with two different groupings: this will show the categories "Cat 1" to "Cat 4" on the x-axis, with colours differentiating "Results A" and "Results B".

We will later use seaborn to build a bar plot, but for now we are going to use a built-in function from pandas as this allows us to create a stacked bar plot.

```python
# Create figure and axes
fig, ax = plt.subplots()

# pandas.plot with option "bar" to create barplot
data.plot(kind="bar", ax=ax, stacked=True)

# Set labels
ax.set_xlabel("Category")
ax.set_ylabel("Count")
```

|![image](figs/barplot1.png) | 
|:--| 
| Stacked bar plot. *Alt text: here* |

# Some other categorical plots
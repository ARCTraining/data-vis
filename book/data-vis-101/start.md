# Introduction to Data Visualisation, with Python

This course is designed to introduce concepts relating to good data visualisation, utilising packages available for Python.

This course should be useful for anyone who works with data and needs to visualise results. While the term "scientific data visualisation" is used in this documentation due to the sources we have collated, the subject matter and example datasets should be applicable to wider research areas than STEM.

This course focuses on the production of static visualisations, and not interactive dashboards.

```{admonition} Objectives
:class: note
This course should help you to:

- Become familiar with best practice with regards to scientific data visualisation
- Build a toolkit of resources to help you create objective, informative plots
- Use Python and Python libraries such as Matplotlib and Seaborn to create aesthetically pleasing graphics
- Be aware of some common issues when it comes to data visualisation
```

This course uses Python as a tool to create graphics. We use packages such as Numpy, Pandas, Matplotlib, and Seaborn in the interactive coding sessions to collaboratively build different example plots, looking at the entire workflow step by step, including downloading and manipulating the starting data into useable formats. We use a free Google-hosted equivalent of a Jupyter Notebook, called [Google Colab](https://colab.google/) to avoid compatibility issues with people using different machines; however we strongly recommend working locally on your machine with actual research data to avoid issues with regards to data security. While this course is an _introduction_ to data visualisation in Python, it is expected that you have some basic experience with Python and understand the data types such as `lists`, `numpy arrays`, `dictionaries`, and have some basic experience with the packages `numpy` and `pandas`.

```{admonition} Pre-requisites
:class: warning
To take this course, please ensure:

- That you have some basic Python experience, either through taking our SWD1a course, or self-taught
- That you have a Google account to use Google Colab
```


## Suggested schedule

This is subject to change.

| Session Name | Duration | Notes |
| --- | --- | --- |
| Introduction | 1hr | Introduction session with slideshow, discussing the _Ten Simple Rules for Better Figures_ by [Rougier, Droettboom and Bourne, 2014](https://doi.org/10.1371/journal.pcbi.1003833). |
| Building your first plot | 30 mins | Interactive coding session. Introducing the tools we are using in this course; demonstrating how to import modules and load data into your Colab Runtime; the many ways of creating a figure with Python; saving figures with different resolutions and file extensions; discussing the default settings available in different modules; looking at how to read documentation. |
| Comparisons: line plots | 1 hr | Interactive coding session. Creating line plots and discussing choice of element size, line style, marker shape, annotations, legends.|
| Distributions: histograms | 1 hr | Building histograms with overlain kde line plots. Discussing figure aesthetics, gridlines, annotations and "chartjunk".|
| Composition: bar charts| 1 hr | Creating stacked bar charts, both absolute and normalised to 100 %; discussing accidentally misleading plots with changing baselines; when proportional vs. absolute values matter. |
| Heatmaps: matrices and images| 1 hr | Creating correlation matrices and statistical plots with Seaborn; discussing use (and misuse) of colour maps; loading and plotting images using Matplotlib colour maps. |
| Reproducible workflows| 1 hr | Building reuseable plotting scripts; creating a toolbox for rapid and reproducible data visualisation; using functions to modularise your code. |
| Closing discussion | 30 mins| Discussing good practice and when rules should be broken; how data visualisation can make or break your research; crowdsourcing tools and resources.|

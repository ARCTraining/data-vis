# Loading in data

In this course, we will use randomly generated data for the majority of the example plots.

This is because we want simple datasets that allow us to demonstrate different ways of plotting, without distracting you with complex data. Also, we don't want to focus too much on any one area of research - or inadvertently misrepresent research data. We want to create simple, adaptable plots that you can use for your datasets.

Each tutorial will include instructions on how to generate your own random data, which you can follow to produce a similar but not identical plot to what we will demonstrate (with some variation because your data is random!).

Alternatively, once we get on to the more complex plots where we use `DataFrames` to store data, we will also provide a link to data we have already generated in the form of a `.csv` file, that you can download to use. While we will still provide instructions to quickly generate random data, downloading and working with a `.csv` file will give you experience in how you might work with your own data files.

For the final section on heatmaps, we will load a non-random example dataset as this is a bit easier to work with!

## General method for loading data

If you want to download data from a URL, you can use the `wget` command:

```bash
!wget -O /content/pick-a-file-name.csv https://the_url_to_where_your_data_is_stored
```

This will save your data to `/content/pick-a-file-name.csv` on the virtual machine.

You can then load in this data using an appropriate command:

```python
pd.read_csv(`/content/pick-a-file-name.csv`)
```

or

```python
jpg_image = plt.imread("/content/example_image.jpg")
```

Read [this article](https://realpython.com/pandas-read-write-files/) for more information on reading and writing files.

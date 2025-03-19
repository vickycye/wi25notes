14 January 2025

---
### Quick Notes
- Review pipe operator in R
- R generally uses a bin size of 30

### To do
- Submit Lab 2 to gradescope

---
### Lab Notes

- `?dataset_name` outputs more information about the dataset
- `filter(dataset, column : requirements)` outputs the dataframe with the specified column and value requirements, `dataset %>% filter(column : requirements)` does the same thing.
- For assignment, use `var1 <- var2`, or `var1 = var2`
- `na.rm = TRUE` means it removes empty inputs

 **Summary statistics:** Some useful function calls for summary statistics for a single numerical variable are as follows:
- `mean`
- `median`
- `sd`
- `var`
- `IQR`
- `min`
- `max`
- `n()` for frequency

In R:

| AND | &   |
| --- | --- |
| OR  | \|  |
| NOT | !   |
Here are some of the most important data visualization we will use:

- `ggplot()` in combination with `geom_histogram()` to produce histograms of a given variable

```
ggplot(data = nycflights, aes(x = dep_delay)) +
  geom_histogram()
```

```
ggplot(data = nycflights, aes(x = dep_delay)) +
  geom_histogram(binwidth = 15)
```

```
ggplot(data = nycflights, aes(x = dep_delay)) +
  geom_histogram(binwidth = 150)
```

- `ggplot()` in combination with `geom_boxplot()` for box plots

```
ggplot(nycflights) +
  geom_boxplot(aes(x = factor(month), y = dep_delay))
```

- `ggplot()` in combination with `geom_point()` for scatterplots

```
ggplot(nycflights) +
  geom_point(aes(x = factor(month), y = dep_delay))
```



---
Back to: [[STAT 311 A - Class Details]]

#Stats 

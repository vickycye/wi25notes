9 January 2025

---
### Quick Notes
- R markdown in RStudio is similar to google colab

### To do
- Explore the canvas to see if I need to turn anything in

---
### Section Notes

`?` command gives information about the Help panel
In R, `dataframe$column` is displaying specific information for a column in the dataframe that comes before the $. 

`ggplot()` builds the plot for the dataset: 
- The first argument is always the name of the dataset you wish to use for plotting.
- Next, you provide the variables from the dataset to be assigned to different `aes`thetic elements of the plot, such as the x and the y axes.

For `arbuthnot`:

```
ggplot(data = arbuthnot, aes(x = year, y = girls)) + geom_point()
// can also use geom_line() to display a line graph
```

Adding a new column to the dataframe:
```
arbuthnot <- arbuthnot %>%
  mutate(total = boys + girls)
```

![[r_add_new_variable_dataframe.png]]


---
Corresponding Lecture: N/A

Back to: [[STAT 311 A - Class Details]]

#Stats 

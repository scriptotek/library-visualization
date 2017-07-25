---
title: "Alluvial diagrams and scatterplots"
teaching: 10
exercises: 20
questions:
- "How do we create simple geomaps depicting new items in our collection?"
- "What ‘different’ ways of visualizing it exist, and how useful are they?"
objectives:
- "First objective."
keypoints:
- Using RAWgraphs you can try out graphs that give more possibilities than the Excel spreadsheets, for example, alluvial diagrams
- Scatterplots are graphs useful for showing correlations, distributions, and trends
---
# Alluvial diagrams and area charts in RAWGraphs

Now, we switch to the **Popular searches** dataset. As mentioned before, this set includes up to 500 of the most popular queries done via uio.oria.no. We will try out some more fancy visualizations, as well as a more ‘serious’ scatterplot graph in this module.

*First steps:*

1. Create a new Google Spreadsheets file (`File` > `New Spreadsheet`)

2. Choose `File` > `Import` > `Upload`. Choose `Insert new sheet` in the next screen.

3. Name the Spreadsheet and rename the imported worksheet to `UserQueries`

Let’s look at the most popular queries in 2016.

> ## Exercise 1: Exploring the top queries in 2016
> 
> 1. First, select all cells (ctrl+A) and choose `Data` > `pivot table`. Rename the new sheet to `QueriesPivot`.
> 
> 2. Let’s count the number of queries. For Rows, choose `Search String`, and for Values, choose `Search string` (`COUNTA`).
> 
> 3. Make sure the Rows are sorted by `COUNTA of Search String` and change the order to `Descending`.
> 
> The numbers are kind of low, aren’t they? Only 13 searches for historisk tidsskrift.
> 
> > ## Discussion
> >
> > What is the problem?
> >
> {: .discussion}
> 
> 4. Remove `Search String` from values
> 
> 5. Add field to values: `Searches`
> 
> 6. Change `Summarize by` to SUM and correct the `Sort by` property under Rows to reflect that.
> 
> 7. Lets add some more details. Add two fields to values: `Signed in` and `On Campus`
> 
> Try on your own to further explore the data. Anything you notice? How would you visualize this?
> 
> Let’s visualize this. We will use RAWgraphs again for this purpose.
> 
> 1. Go to the UserQueries sheet.
> 
> We will use the date in column R, but it is not formatted correctly for visualization in RAW. Let’s amend that.
> 
> 2. Select column R, with the dates, and choose `Format` > `Number` > `9-26-08`
> 
> 3. Go back to the pivot table (`QueriesPivot`) and delete the previous `Signed in` and `ON campus`.
> 
> 4. Add the field `Month (date)` under columns. Remove `show totals`.
> 
> 5. Select the first 10 queries in the pivot table, including the column headers and all months. Copy them (ctrl + C).
> 
> 6. Open a new tab and go to [http://app.rawgraphs.io/](http://app.rawgraphs.io/)
> 
> 7. Paste the data into the `Load your data` field.
> 
> Whoops! An error. What’s wrong?
> 
> Correct this by adding a name for the first column in the text field (you can observe it is now empty). Put the cursor on the first line of the text field and add the column name Query.
> 
> ![Load data (1)]({{ page.root }}/fig/06-load-your-data.png)
>
> Notice the message under the text box, which says `Your data seems unstacked. Click here to stack it`. This is caused by how we put the dates into different columns.
> 
> From [minitab.com](https://support.minitab.com/en-us/minitab/18/help-and-how-to/manipulate-data-in-worksheets-columns-and-rows/supporting-topics/data-types-and-arrangements/stacked-and-unstacked-data/):
> 
>     “If data are unstacked, each column contains observations from one group. There is no grouping column.”
>     “If data are stacked, the sample values for all groups are in a single column, with a corresponding column of labels that identifies the sample. This column of labels is referred to as a grouping column...”
> 
> Hence, we have to stack the data to use it in RAWGraphs. Luckily this can be done for us:
> 
> 8. Click on the message to stack the data. Under `Select a dimension to stack on` choose `Query`. Notice the difference? The contents of the previous columns are transferred into different rows.
> 
> ![Load data (2)]({{ page.root }}/fig/06-load-your-data-02.png)
>
> 9. Scroll down, choose the `Streamgraph` chart.
> 
> 10. Drag the `Query` dimension into the `Group` field, the [todo: check] column into the Date field, and the Value into the `Size` field.
> 
> ![Streamgraph]({{ page.root }}/fig/06-streamgraph.png)
>
> Any observations from the data?
> 
> Try out some other graphs. In particular, the **Area graph**, the **Bump chart**, and the **Horizon graph**. Which do you like most and why?
>
> ![Area Graph)]({{ page.root }}/fig/06-area-graph.png)
> 
{: .challenge}

Finally, we are going to make a **scatterplot**. 

> ## What is a **scatterplot**?:
>
> It is a type of chart which can be useful for showing relationships between two to three variables, to show data distributions, and for displaying trends.
>Using a scatterplot it is possible to discover patterns, correlations, clusters and outliers, and it is possible to compare a large number of values.
>
{: .callout}

> ## Exercise 2: Scatterplot
>
> For our scatterplot, we are going to look at the relation between the **length of a query**, and the **number of results** retrieved in the search system. To do so, we have to extend the dataset.
> 
> First, we will add a length in characters column to our source data.
> 
> 1. Go to the **first empty column** in the `UserQueries` sheet
> 
> 2. Type `=LEN(B2)` in cell `V2`
> 
> 3. Copy this formula (ctrl+C), select the whole V column and paste it (ctrl+V).
> 
> Make sure the length value is now visible in the whole column.
> 
> 4. Add the name `Query Length (characters)` to the column (i.e. in the first row).
> 
> Next, we will add a column reflecting the number of words of a query.
> 
> 5. Go to the first empty column in the UserQueries sheet (most likely `W`)
> 
> 6. Type `=LEN(B2)-LEN(SUBSTITUTE(B2;" ";""))+1`
> 
> 7. Copy this formula (ctrl+C), select the whole column and paste it to fill it (ctrl+V).
> 
> 8. Add the name `Query Length (words)` to the column.
> 
> Verify if the formula is correct by comparing the calculated number of words to the `Search String` column.
> 
> Now, we need a pivot table again.
> 
> 1. First, select all cells (ctrl+A) and choose `Data` > `Pivot table`. Rename the new sheet to `ScatterPivot1`.
> 
> 2. For the rows, add `Query length (characters)` and remove `show totals`.
> 
> 3. For the values, add `Results`.
> 
> `Summarize by SUM` doesn’t appear to be correct. What would you choose and why?
> 
> 4. Change the `Summarize by` to `AVERAGE`.
> 
> 5. Duplicate the pivot table (right click the tab and choose `duplicate`). Rename the copied table to `ScatterPivot2`.
> 
> 6. Remove group by `Query length (characters)` from Rows
> 
> 7. Add `Query length (words)` to Rows
> 
> 8. Remove `Show totals`
> 
> Now go to [plot.ly/create](https://plot.ly/create). 
> 
> 1. Copy all the values from the `ScatterPivot1` table.
> 
> 2. Paste them into `Grid 1` of plot.ly
> 
> 3. Copy all the values from the `ScatterPivot2` table.
> 
> 4. Make a new Grid using `+Grid`. Paste the data into `Grid 2` of plot.ly
> 
> 5. Click `+Trace`. For `X`, choose `Grid 1 - A` in the dropdown menu. For `Y` choose `Grid 1 - B`.
> 
> 6. Again, click `+Trace`. For `X`, choose `Grid 2 - A`. For `Y` choose `Grid 2 - B`. Scroll down to do so.
> 
> 7. **Rename** the headers
> 
> 8. **Restyle** the graph (Go to `Style`)
> 
> 9. Go to `notes` (Add an `Annotation` to explain the outliers).
> 
> ![Scatterplot]({{ page.root }}/fig/06-scatterplot.png)
>
> Hence, we obtained an image of the number of characters/words versus the number of results. We can observe a slight correlation (i.e. more characters results in less retrieved results).
> 
{: .challenge}

> ## Further exercises
> 
> If you have time, you can explore the queries more qualitatively: what do the long and short queries actually look like? This can easily be done using the pivot tables
{: .challenge}

[todo: lesson ending, further reading.]
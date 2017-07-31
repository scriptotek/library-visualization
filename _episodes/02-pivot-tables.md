---
title: "Pivot tables and basic visualizations"
teaching: 10
exercises: 40
questions:
- "What are pivot tables?"
- "How do we use them to summarize data?"
- "How do we create basic visualizations from the summaries in pivot tables?"
- "What are design guidelines for basic visualizations such as column charts, bar charts and pie charts?"
objectives:
- "First objective."
keypoints:
- Pivot tables are data summarization tools, useful to quickly summarize data
- Pivot tables can be useful for doing exploratory data analysis, but also for visualization
- Data understanding and cleaning is still of key importance
- Column chart visualizations should be used when having 7 categories or less
- Bar charts should be used when having more than 7 categories
- Pie charts should only be used with caution

---
# The why and how of pivot tables

We will work with very large sets of data, regarding **new physical items** and **popular searches**, including 10,000s of rows. To be able to actually visualize these data, we have to apply some kind of summarization. This can be done in different ways. One way to summarize data is by writing a script that does the summarization for you, which we will not really touch upon in this workshop, but for which we will give further pointers at the end of this workshop. A second way is by using a common package to do these summaries in a so-called pivot table.

# Introduction to pivot tables

From Wikipedia: “In data processing, a pivot table is a data summarization tool found in data visualization programs such as spreadsheets or business intelligence software. Among other functions, a pivot table can automatically sort, count, total or average the data stored in one table or spreadsheet, displaying the results in a second table showing the summarized data.”

Tools which can be used to create pivot tables are for instance Microsoft Excel, OpenOffice/LibreOffice Calc, Google Spreadsheets. In this workshop, we will work with Google Spreadsheets, but most of the functionality works in the same way in both Excel and OpenOffice. Compared to Google Spreadsheets, Microsoft Excel has some additional features, which allow for more advanced filtering and processing.

First, we have to **import our data into Google Spreadsheets**:

1. [Open Google spreadsheets](https://docs.google.com/spreadsheets/u/0/), choose `Blank`
    
2. Make sure that the correct “locale” (region settings) are set. Choose `File` > `Spreadsheet settings`.  Under `locale`, choose: `Norway (Norwegian Bokmal)`. This ensures that comma is understood as the decimal point, that dates are handled correctly, etc.
    
3. Choose `File` > `Import` > `Upload`. Choose `Select a file from your computer`. Locate the file **NewPhysicalItems.xlsx** and select it.
    
4. When requested in the dialog box select `Insert new sheet` in the next menu.
    
5. Name the worksheet **NewItems** (to rename the sheet double click on the sheet name (at the bottom of the window) or click on the small arrow next to the name and choose `Rename…`). 

> ## Some notes about the use of Google Spreadsheets to keep in mind
> 
> * It can be slow from time to time, when using a large dataset such as the New Physical Items dataset. A message “script on this page may be busy, or it may have stopped responding” can sometimes appear. Be sure not to close the page, but to select ‘continue’, or ‘wait’, until the processing finishes. The Chrome browser seems to work slightly faster than Firefox in this regard.
> * Copying text using the menu elements does not work on most machines, so use the keyboard shortcuts **Ctrl+C** and **Ctrl+V** on Windows, or **Cmd+C** and **Cmd+V** on Mac to copy and paste, respectively. Using keyboard shortcuts is good practice anyways, that can make you work more efficiently in any software.
>
{: .callout}

> ## Exercise 1: Create a Pivot Table showing the most frequent books per publisher
> 
> Let’s create our first pivot table. Follow the following steps:
>
>1. Select **all the data** in the **NewItems** sheet (Ctrl + A (Windows) or Cmd + A (Mac))
>
>2. Choose `Data` > `Pivot table…`
>
>3. Notice at the bottom of the window that a new sheet has been created. Rename it to **PublisherPivot** (again, by double clicking on the sheet name or right-clicking and choosing `Rename…`)
>
>Now, we are ready to **add rows and values** to our pivot table. For this, use the ‘**Report Editor**’ functionality on the right-hand side.
>
>4. **Rows**: Click `add field`. Choose `Publisher` from the list of fields which appears
>
>It should now show: `Group by: Publisher`
>
>5. **Values**: Click `add field`. Again, choose `Publisher` from the list
>
>It now shows: `Group by: publisher`, and `Summarize by: SUM`.
>
>6. Click on `SUM` and change the value to `COUNTA` (counting all values)
>
>We now see a list of publishers and how often they appear in our dataset, in our pivot table. You may observe that some more data cleaning could be done (e.g. merging 'Ace Books' and 'Ace Books' inc.). 
>
>Right now, the order is alphabetical, which does not reveal many insights in the most common publishers in our datasets. Thus, we have to adapt the sorting. We now will order the publishers by how often they occur in the dataset.
>
>7. Under rows, click on `Sort by: Publisher`. Choose the option `COUNTA of  Publisher` from the list.
>
>Now, we see the ordering has changed, but it starts at the lowest value, not the highest one. Since we’re interested in the most frequently occuring publishers, we will have to reorder the set:
>
>8. Click `Order: Ascending`, and change the value to: `Descending`.
>
> This results in a list of the top publishers in this dataset.
>
> > ## Answer
> >
> > 		Oxford University Press		726
> > 	Routledge			700
> > 	Universitetsforl			529
> > 	Cambridge University Press	440
> > 	Cappelen Damm			360
> > 	Fagbokforl			314
> > 	Gyldendal akademisk		297
> > 	Palgrave Macmillan		287
> > 	Gyldendal			235
> > 	Cappelen Damm akademisk		207
> >
> {: .solution}
> 
{: .challenge}

>## Discussion
>
>Can you spot some issues with the pivot table we just made?
>
{: .discussion}

For these types of lists, data cleaning (which can for instance be done via OpenRefine) is very important, since variations in names will directly influence the counts we obtain. Often this ends up as an iterative process where you start by doing some initial cleanup of the data, then carry out a first analysis (like we just did), which reveals more issues with the data that you can go back to clean up before continuing. 

# Charting in Google Sheets

After creating our first pivot table, we can now move on to creating our first chart in Google Spreadsheets.


> ## Exercise 2: Creating our first chart in Google Spreadsheets
> 
> 1. First, select the **top 10 of publisher names and number of items** with the mouse.
>
> 2. Choose `Insert` > `Chart` from the top menu
>
> As you observe, Google Spreadsheets provides a chart editor where you can select the chart type (in the “Chart editor” on the right side). Check out the different options by selecting a number of them.
>
> > ## Discussion
> > 
> > Which of the visualizations would you choose for this dataset? Why?
> > 
> {: .discussion}
>
> 3. Select the `Column chart` from the `Chart type` dropdown menu.
>
> To change the appearance of the graph, just click on the elements of it. Try out some options:
>
> 4. Left-click on the **series** (the bars in the graph) and change the color to your liking.
> 
> 5. Left-click on the **names of the publishers**, and change the font from `12` to `10`.
> 
> 6. Let’s remove the legend, since it is not very useful in this graph. Click on the **legend** of the graph, and under `Legend` on the right-hand side, choose `Position` and click on `none`..
> 
> 7. Add a **title** to the graph (right-click the graph, and select `Chart & axis titles` and add the title in the right box. You could also add it using the right-hand side `Chart editor` box, selecting the second tab: `Customize` > `Chart & axis titles`).
> 
> Try out the other options to customize your graph yourself. 
> 
> * E.g., change the orientation of the labels, or the scale of the Y axis.
>
> > ## Answer
> >
> > ![Most Frequent publishers]({{ page.root }}/fig/02-frequent-publishers.png)
> >
> {: .solution}
> 
{: .challenge}


> ## Exercise 3: Summarizing author data
> 
> Let’s **duplicate our pivot table** and change its contents.
> 
> 1. Right-click on the **name** of the Pivot table (i.e., `PublisherPivot`) and select `Duplicate`
> 
> 2. Change the name of the sheet to **AuthorPivot**
> 
> 3. Delete the graph by clicking on it and pressing the *backspace* or *delete* key (or by clicking on the icon with three 'dots', and choosing `Delete chart`). Then remove the rows and values by clicking on the `X`'s in the `Report Editor` on the right-hand side.
> 
> Let’s make a new pivot table:
> 
> 4. For the rows, now click `Add field` and choose `Author`.
> 
> 5. For the values, now choose `Add field` and select again `Author`. For `Summarize by`, choose `COUNTA`.
> 
> 6. For the Rows, now choose `Order: Descending`, and `Sort by: COUNTA of Author`.
> 
> After a little while, the pivot table should appear, and look like below.
>
> > ## Answer
> >
> > 	1. Norge				58
> > 	2. Ibsen, Henrik 1828-1906	41
> > 	3. Falkanger, Thor 1934-		33
> > 	4. Vance, Jack			23
> > 	5. Silverberg, Robert		22
> > 	6. Lødrup, Peter 1932-2010	19
> > 	7. Lindstrøm, Tom L. 1954-	19
> > 	8. Bradbury, Ray			17
> > 	9. Asimov, Isaac			17
> > 	10. Schartum, Dag Wiese 1956-	16
> >
> {: .solution}
>
> > ## Discussion
> >
> > What do you notice when looking at the pivot table?
> >
> > {: .discussion}
>
> Let’s go more into detail for this graph and filter it.
> 
> 1. Click `Add field` next to the Filter label. Choose `Acquisition method`.
> 
> 2. Click on `Show: All items`. Click `Clear` and then `GIFT` so that only `GIFT` is checked.
> 
> 3. Sort by `CountA of author`
> 
> > ## Discussion
> >
> > What do you observe?
> >
> > {: .discussion}
> 
{: .challenge}

# Visualizing distributions per library

We have thus far looked at some publisher data, and at the authors of newly acquired books. To get more insights, we will now check how the books are distributed per library.

> ## Exercise 4: Checking the distribution of new books per library and visualizing it
> 
> 1. Remove the filter we have just added, by clicking the `X` next to `Filter: Acquisition method`
> 
> 2. Choose **Columns**: `Add field`. Select `Library name`.
> 
> Now, we may have to wait a little bit, since we are generating a lot of summary data. Finally, you will see a large table with the authors as rows, and all different university libraries as columns.
> 
> We get some idea about the distribution per library, but it is quite an overwhelming amount of data. **Any observations?** We can notice that there is e.g. some overlap between the most purchased authors in different libraries. 
> 
<!-- Let’s **filter** the data to make it more ‘readable’.
> 
> 1. Click `Add field` next to the `Filter` label. Choose `Library name`.
> 
> 2. Click on ‘Show:’ `All items`. Click `Clear` to uncheck all library names. Now select `Humanities & Social Sciences Library`, `Science Library`, `Medical Library` and `Law Library`. (Or your own favourite library!).
> 
> Wait for the table to update (this may take a little while - if the browser shows the warning that the page has become unresponsive choose ‘wait’). --> 
>
> Now, we can visualize this dataset using a ‘Stacked bar chart’
> 
> 1. Select the **top 40** of all author rows with all columns (to select; either click and drag, or you can click on the top left cell and, while you hold down the shift key, press the bottom right cell in our range. The latter way is especially useful if you need to make a much larger selection.)
> 
> 2. Now choose `Insert` > `Chart`. Go to the `Chart types` tab. Check out the different types of graphs Google Spreadsheets offers. Finally, choose the second ‘Bar’ chart (`Stacked Bar chart`). Click on `Insert`.
> 
> 3. Go to `Customize` and add a **descriptive title**. Then click the **names** on the Y axis and change the font size to 10. Enlarge the chart vertically by dragging the blue box handle on the bottom until all author names are shown.
> 
> > ## Answer
> >
> > ![Most Frequent publishers]({{ page.root}}/fig/02-frequent-publishers-per-library.png)
> >
> {: .solution}
>
> > ## Discussion
> >
> > Any observations based on the graph?
> >
> {: .discussion}
>
{: .challenge}

To sum up, In our first exercises we have started to use **Pivot Tables**, and we have explored **column charts** and **bar charts**.

# Basic charting guidelines

There are some guidelines for these types of charts (which we may have not fully followed!).

[EazyBI.com](https://eazybi.com/blog/data_visualization_and_chart_types/) suggests that **Column charts** should **not have more than 7 categories**.
 If there is time involved in the data (e.g. months or years), it should always be on the horizontal axis, moving from left to right. Also, it is important to make the Y axis start at 0 to avoid misleading information. 

Actually, we showed the 10 most occurring publishers in a column chart, which turns out was not the optimal choice.

**Bar charts**, on the other hand, can be used when having **more than 7 categories**. We used this type of chart in our second example. An advantage of a bar chart is that it allows for using longer category names, such as the author names we visualized.
A frequently applied simple chart which we did not use is the **Pie chart**, which should be used with caution - ideally with only 2 categories, and with a maximum of 6. They should not be used when the category values are very similar or different.

A final guideline for these kind of graphs is to **keep it simple and to reduce clutter**. For instance, one should not use 3D effects in Pie charts, since they do not add any value and will make it harder to identify and compare the sizes of the pie slices (which is already hard with 2D pie charts because humans are not great at estimating and comparing angles). In general, one should remove all unnecessary decorations and lines.
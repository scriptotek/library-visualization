---
title: "Introduction"
teaching: 30
exercises: 0
questions:
- "What is visualization?"
- "What are common fallacies in terms of visualization?"
objectives:
- "First objective."
keypoints:
- "Visualization comes in many forms and variations."
- It is not straightforward to create reliable and engaging visualizations, and one has to keep in mind our cognitive biases.
- When viewing visualizations made by others, always keep an eye open for ‘visualization lies’
---

# Visualization: An introduction

“A picture can say more than a 1000 words”, is the old adagium. This also holds true for data: some large datasets which we work with, only reveal some of their secrets after carefully visualizing them. 

The question is, of course, how to actually visualize data in practical terms. Also, the exact form of visualizations influence how useful they are.

# Some famous examples:

[image 1]

Depicting events Russian military campaign by Napoleon (1812-13). Can make information more clear. (https://www.edwardtufte.com/tufte/minard)

[image 2]

Ease navigation: Tube map London (http://www.bbc.co.uk/london/travel/downloads/tube_map.gif)

[image 3]
Saving lives: tracing the source of a cholera outbreak in Soho, London (1854), map used to find cause of epidemic. Dr. John Snow (source: https://www1.udel.edu/johnmack/frec682/cholera/, https://www1.udel.edu/johnmack/frec682/cholera/snow_map.png).

[image 4]
Provide insights into scientific data: climate change “hockey stick” graph (Michael E. Mann, CC-BY)
https://upload.wikimedia.org/wikipedia/commons/0/0a/Mann_hockeystick.jpg

# Visualizations

Let's start by looking at the concept of 'visualization'.

> ## Defining Visualization
>
> Cairo (2016)’s definition:  “A visualization is any kind of visual representation of information designed to enable communication, analysis, discovery, exploration, etc.”
> 
{: .callout}

Davis (2009) distinguishes the following types of visualization:
* **Statistical visualizations**
e.g. [Supreme Court Justices](https://upload.wikimedia.org/wikipedia/commons/c/c6/Graph_of_Martin-Quinn_Scores_of_Supreme_Court_Justices_1937-Now.png)
* **Infographics**
e.g. [An internet minute](https://commons.wikimedia.org/wiki/File:Internet_Minute_Infographic.jpg)
* **Maps**
e.g. [New York Times immigration explorer](http://www.nytimes.com/interactive/2009/03/10/us/20090310-immigration-explorer.html?mcubz=1)
* **Network visualizations**
e.g. [Social network analysis visualization](https://upload.wikimedia.org/wikipedia/commons/9/9b/Social_Network_Analysis_Visualization.png)
* **Artistic visualizations** (“data as art”)
e.g. [“Forest of Numbers”](http://flowingdata.com/2017/02/20/forest-of-numbers/)

Hence, the word ‘visualization’ encompasses a wide range of possible diagrams. In this workshop, we will not look at all these different types of visualizations, but mainly focus on (statistical) charts.

> ## What is a chart, then?
>
> Cairo (2016) defines it as such: “A chart is a display in which data are encoded with symbols that have different shapes, colors, or proportions.”
> 
{: .callout}

 

# Common goals of visualization
Visualizations can be made for a wide range of purposes. It may reveal things that were not visible before, and can be used for exploratory data analysis. Potential goals are manyfold:

*Analyzing data, often exploratory
“Graphing data needs to be iterative because we often do not know what to expect of the data; a graph can help discover unknown aspects of the data, and once the unknown is known, we frequently find ourselves formulating new questions about the data.” (Cleveland 1985, as cited in Spence, 2001) 
* Disseminating results of analysis
for instance in a news article or scholarly paper
* Decision making
taking actions based on evidence in the data
* Conveying a message, for instance social issues

While there are many other potential goals for visualization, we mainly focus on exploratory data analysis and dissemination in this lesson.

## Qualities of visualizations
Cairo (2016) suggests a number of qualities of visualizations (which are often not met in practice!):

* *Functional*
It should depict data accurately, but also be useful to people
* *Beautiful*
A visualization should be ‘attractive’ to different audiences
* *Insightful*
It should reveal evidence that we could have missed without the visualization
* *Enlightening*
A visualization may “change our minds” (hopefully for the better...)
* *Truthful*
A visualization should depict truthful and honest research

The last point is especially important: statistics may not be (entirely) correct, and this applies more gravely to visualizations.

# Fallacies of visualization
Designing an understandable and reliable visualization is far from straightforward. <!--A frequently used quote in this context is that there are “Lies, damned lies, … and statistics”. Mark Twain attributed this to British Prime Minister Benjamin Disraeli, which in itself may not be entirely correct ([source](https://en.wikipedia.org/wiki/Lies,_damned_lies,_and_statistics)).-->
One the one hand, there is the importance of the **origins, quality and scope** of underlying data. It is essential to understand the whole picture, that is, how data is generated, if it is complete, or if it is a sample. 

For instance, in this lesson we will be working with a dataset containing *popular searches*. It is important to ask oneself what “popular” means in this case. 

> ## The popular searches dataset
>
> This dataset, originating from Primo Analytics, contains up to 500 different query variations per month, as performed in the University of Oslo library discovery system Oria. In the case of this university, this amounts to 5% of all searches done in the system.
> 
{: .callout}

Moreover, data processing is important, as each round of processing may influence what you see in the end (and this is even before starting to visualize data).

Cairo (2016) has summarized some of our **inherent biases** which have an effect on our judgement of visualizations:
* **Patternicity**
“Detecting interesting patterns, regardless of whether or not they are real”
* **Storytelling**
Trying to find cause-effect relationships for patterns we observe
* **Confirmation**
Confirming our own beliefs (cognitive dissonance, confirmation bias)

Also during the creation of visualizations, we may introduce issues (consciously or unconsciously) due to bias or mistakes in interpretation. See [Flowing Data](https://flowingdata.com/2017/02/09/how-to-spot-visualization-lies/) for a summary of common ‘visualization lies’.

While there is always some interpretation involved in both creating and reading visualizations, we can try to keep in mind some of these issues and try to prevent them.



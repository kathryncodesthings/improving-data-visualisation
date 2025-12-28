# Data projects

These projects showcase my technical data skills and my ability to solve real business problems. Each one starts with a practical question from stakeholders, uses data analysis to test assumptions, and ends with clear, actionable insights.

Where relevant, I include links to the full analysis and code.

---

## Improving data visualisation

Skills demonstrated: data visualisation; communicating insights to non-technical audiences.

### Business question

A common problem for Finance is how to visualise I&E data. This is a challenge for many reasons - lots of data, wanting compare year-on-year movements while still clearly showing the composition of each year's I&E, granularity versus readability. 

I can't share internal data from my work, so I've picked a similar type of chart and shown how I would improve it. Here's one that shows the revenue sources for the Canadian National Broadcasting Corporation for two years.

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/original.png)

### What are the problems with this chart?

The whole image is confusing. You might think at a glance that this is showing **three different** revenue categories, one totalling $1.7bn, one totalling $490m, and one totalling $248m. But it isn't! The leftmost column ($1.7bn) is for **all** revenue, and the next two columns break down that revenue further. This isn't how most cluster bar charts work, making it difficult for data users to interpret. At worst, it could mislead data users.

This leads to a puzzling label for the dark blue section of the first column: 'Revenue'. Isn't it all revenue?

The y axis isn't continuous. There's a jump between $700m and $1.7bn so that the leftmost 'total' revenue bar wouldn't completely overshadow the 'breakdown' bars. This means that the largest revenue bar is disproportionately smaller than it should be, which could - again - confuse and mislead data users. It makes the $1.2bn of Government revenue look smaller than the $490m in the next column, for example.

There are also some smaller problems which could be cleaned up:
* The y axis could be removed as all the data points are labelled. This could reduce some of the visual clutter.
* The order of the years is back-to-front from what most data users would expect. Although new -> old is customary for financial statements, data users would expect to see old -> new when looking at time series data visualisation.
* Needing to look back and forth to the key to get the data category isn't ideal.
* It's also not easy to compare categories year-on-year quickly. This takes more time, and it's easy for users to make a mistake.

### Revision 1: Stacked bar chart

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/Improved%20viz%201.png)

I created this in Power BI and made the following improvements:
* Added a clear headline to give data users a quick takeaway, highlighting the most significant information in the graphic
* Removed the confusing multiple columns, combining all revenue streams into one column per year
* Swapped the year order so that data users can read it in a more familiar way (oldest to newest / left to right)
* Put labels directly on the graph to make it easier to read (no need to look back and forth for colours/lables)
* And I can therefore remove the unnecessary y axis, reducing visual clutter

However, there are still some issues with the graph:
* Most significantly, the smallest segment (digital advertising revenue) can't accomodate a label
* Needing width for the widest labels means the columns have to be large, taking up a lot of space
* To compare categories, data users still need to look back and forth between the two columns and mentally compare the two values for each category. 

I could add a label manually in a a pop-out box to solve the first problem. I could also adjust the label formatting and sizes.

I decided to try a different solution: a slope graph.

### Revision 2: Slope graph

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/Improved%20viz%202.png)

This was built in the web service Flourish. 

I had the same problem that the creator of the original graph had: the largest revenue source is so far above the others that it leaves a lot of white space in the middle of the visual. 

Additionally, there are two categories that are so close in value together that they have to overlap at the bottom of the graph.

While this does successfully show the movement year-on-year more clearly, it's not suitable.

### Revision 3: horizontal clustered bar chart

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/Improved%20viz%203.png)

This was built in the web service Flourish. 

This was my favourite of the three revisions. This layout compares the year-on-year movements and the overall composition of the revenue. There is some loss of information (it doesn't show total revenue, as it's been split into bars). However, I think this is the best compromise for illustrating the makeup of the revenue while comparing the year-on-year changes.

The horizontal format minimises the problem of wasted space due to the large outlying category, and is easy for data users to read as it's in the same left to right format as most written English text.

There are some small tweaks made to improve the visualisation:
* Shading the previous year paler and the most recent year darker, to focus attention on the most recent year
* Sorting the sources of revenue from largest to smallest also communicates to the data user which are the highest revenue sources

It also draws out the important message that the main reason for the decline in revenue is a decline in advertising revenue, something that wasn't as obvious from the other visualisations.

If I  wanted to really draw attention to the advertising revenue decrease, for example if this was for a presentation, I would shade the advertising revenue bars a different, brighter colour.

## Conclusions
Depending on what the company wants to communicate to its data users, different visuals will be suitable. It might be ideal to have a pullquote highlighting 'Revenue decreased xx%' to promote the overall movement, and have the third visualisation to show more detail. There's always some compromise necessary, however this version of the chart shows the key data clearly, in a format that data users can quickly absorb and understand.

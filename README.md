# Improving data visualisation

A common problem for Finance is how to visualise I&E data. This is a challenge for many reasons - lots of data, wanting compare year-on-year movements while still clearly showing the composition of each year's I&E, granularity versus readability. 

I can't share internal data from my work, so I've picked a similar type of chart and shown how I would improve it. Here's one that shows the revenue sources for the Canadian National Broadcasting Corporation for two years.

## What are the problems with this chart?

The whole image is confusing. You might think at a glance that this is showing **three different** revenue categories, one totalling $1.7bn, one totalling $490m, and one totalling $248m. But it isn't! The leftmost column ($1.7bn) is for **all** revenue, and the next two columns break down that revenue further. This isn't how most cluster bar charts work, making it difficult for data users to interpret. At worst, it could mislead data users.

This leads to a puzzling label for the dark blue section of the first column: 'Revenue'. Isn't it all revenue?

The y axis isn't continuous. There's a jump between $700m and $1.7bn so that the leftmost 'total' revenue bar wouldn't completely overshadow the 'breakdown' bars. This means that the largest revenue bar is disproportionately smaller than it should be, which could - again - confuse and mislead data users. It makes the $1.2bn of Government revenue look smaller than the $490m in the next column, for example.

There are also some smaller problems which could be cleaned up:
* The y axis could be removed as all the data points are labelled. This could reduce some of the visual clutter.
* The order of the years is back-to-front from what most data users would expect. Although new -> old is customary for financial statements, data users would expect to see old -> new when looking at time series data visualisation.
* Needing to look back and forth to the key to get the data category isn't ideal.
* It's also not easy to compare categories year-on-year quickly. This takes more time, and it's easy for users to make a mistake.

## Revision 1
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

## Revision 2

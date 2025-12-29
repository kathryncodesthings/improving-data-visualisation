# Data projects

These projects showcase my technical data skills and my ability to solve real business problems. Each one starts with a practical question from stakeholders, uses data analysis to test assumptions, and ends with clear, actionable insights.

Where relevant, I include links to the full analysis and code.

---

## Improving data visualisation

Skills demonstrated: data visualisation; analytical judgement; communicating insights to non-technical audiences; translating complex data into clear narratives.

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/original%20to%20improved.png)

### Business question

Finance teams often struggle to visualise income and expenditure data in a way that is:
* Clear and intuitive for non-financial audiences
* Able to show both year-on-year change and overall composition
* Detailed enough to be accurate, without overwhelming the reader

This is a common problem across many sectors, not just higher education.

As I can't share internal data from my role, I used a publicly available example showing revenue sources for CBC-Radio Canada across two years, and demonstrated how I would improve the visual communication.

![Bar chart showing revenue sources for CBC-Radio Canada for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/original.png)

> Source: CBC-Radio Canada 2018-2019 Annual Report ([PDF](https://site-cbc.radio-canada.ca/documents/impact-and-accountability/finances/2018-2019-annual-report.pdf)), page 39

### What are the problems with this chart?

At first glance, the chart is confusing and difficult to interpret correctly. The layout appears to show three separate revenue totals ($1.7bn, $490m and $248m), when in fact:
* The left-hand column represents total revenue
* The two columns to the right break that total into components

This is not how most grouped bar charts are structured, which makes the visual misleading and increases the risk of misinterpretation.

The y axis isn't continuous. There's a jump between $700m and $1.7bn so that the leftmost 'total' revenue bar wouldn't  overshadow the 'breakdown' bars. This means that the largest revenue bar is disproportionately smaller than it should be, which could mislead data users. It makes the $1.2bn of Government revenue look smaller than the $490m in the next column, for example.

There are also some smaller design issues:
* The y axis could be removed as all the data points are labelled
* The order of the years runs newest to oldest, which is counterintuitive for most time-based visuals
* Needing to look back and forth to the key to get the data category isn't ideal
* Year-on-year comparisons are slow and it's easy for users to make a mistake

Overall, the chart demands too much effort from the reader and risks communicating the wrong message.

### Revision 1: Stacked bar chart

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/Improved%20viz%201.png)

I recreated the chart in Power BI, focusing on clarity and reducing ambiguity.

Key improvements:
* Added a clear headline to communicate the main takeaway immediately
* Used a single bar per year, stacking revenue sources to show composition clearly
* Reordered the years from oldest to newest for intuitive reading
* Placed labels directly on the bars to remove reliance on a legend
* Removed the y-axis to reduce visual clutter

This version is clearer, but it still has limitations:
* The smallest category (digital advertising) cannot comfortably display a label
* Long labels force the bars to be wide, using space inefficiently
* Comparing individual categories year-on-year still requires mental effort

While these issues could be partially mitigated, I decided to explore a different visual approach: a slope graph.

### Revision 2: Slope graph

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/Improved%20viz%202.png)

This version was built using Flourish and focuses explicitly on change over time.

It makes year-on-year movement clearer, but introduces new problems:
* One revenue source is so much larger than the others that it creates excessive white space
* Two categories at the lower end overlap, reducing readability
* The visual struggles to balance scale and legibility

Although slope graphs are powerful in the right context, this dataset isn’t well suited to the format.

### Revision 3: horizontal clustered bar chart

![Bar chart showing revenue sources for the Canadian National Broadcasting Corporation for two years](https://github.com/kathryncodesthings/improving-data-visualisation/blob/main/Improved%20viz%203.png)

This was also created in Flourish and is my preferred solution.

This layout:
* Makes year-on-year comparisons easy and fast
* Still communicates the composition of revenue
* Avoids distortion caused by very large outliers
* Uses a left-to-right reading flow that feels natural to most users

There is a trade-off: total revenue is no longer shown explicitly. However, for most decision-making contexts, understanding what changed and why is more important than seeing the total figure.

Additional refinements:
* The earlier year is shown in a lighter shade, drawing attention to the most recent data
* Revenue sources are sorted from largest to smallest, reinforcing their relative importance

This version clearly highlights the key problem behind the revenue decline: a fall in advertising revenue. This was far less obvious in the original chart.

If this visual was being used in a presentation, I'd consider highlighting advertising revenue in a stronger colour to focus viewers' attention further.

## Conclusions
This project demonstrates that there is no single 'correct' chart. The best visual depends on **what the organisation wants to communicate**.

In practice, a strong approach might include, depending on the medium of commuication and the intended audience:
* A headline or pull-quote summarising the overall change (e.g. 'Revenue fell by X% from $x to $y')
* A supporting visual like the final chart to explain why the change happened

This short project shows my ability to:
* Critically assess existing data visualisations
* Select and justify alternatives based on audience needs
* Communicate complex financial information clearly and efficiently

It also highlights an important principle: good data visualisation for businesses is about supporting informed decision-making, not decoration.

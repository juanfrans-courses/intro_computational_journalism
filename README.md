# Introduction to Computational Journalism
* Columbia University | School of Journalism | Summer 2019
* June 3 - 7, 9am - 4pm | Pulitzer Hall 601A
* Professor: Juan Francisco Saldarriaga (jfs2118)

Journalists who can identify, refine, and interrogate the information they need within a large data set are in-demand and publishing the most exciting work in the industry. The *Introduction to Computational Journalism* course at Columbia Journalism School, teaches the fundamentals: how to scrape data from the web, digitize PDFs and use other digital sources to compile your own data sets; a primer on Python and its most popular data analysis library, Pandas; and how to build your initial analysis and visualizations.

#### Prerequisites
This data journalism course is designed for those with basic analytic skills or experience (Excel and/or databases). All students will need a laptop with administrative install abilities.

#### Objectives
* Find stories within the data, and work within your team and newsroom to report them out
* Learn the fundamentals of Python and the Python data analysis tool Pandas
* Scrape and clean publicly available data from the web
* Automatically submit online forms and scrape the results
* Convert tabular data from PDFs into spreadsheet-compatible formats
* Extract text from PDF images of documents (OCR)
* Combine multiple data sets
* Perform exploratory data analysis and visualization

#### The School
The Columbia University Graduate School of Journalism is the premiere institution for the study and practice of journalism in the world. Led by our award-winning faculty of active reporters, editors, filmmakers and digital media specialists, our programs are intensive, rigorous, and demanding. Our professional development programs, fellowships and workshops offer opportunities for seasoned practitioners and media executives to advance their knowledge and expertise.

## Course Syllabus
Course time will be full-day, Monday through Friday. Instruction time will be divided between short lectures (90-120 minutes) and exercises done individually and in small teams.

### Monday, June 3
[*Basic data analysis (Excel / Google Sheets / Open Refine / PDFs)*](01_Excel_GoogleSheets_OpenRefine_PDFs/README.md)
* Introductions and overall plan for the week
* Data processing & organization: workflow and principles
  * Raw data and data wrangling
  * Suggested data and file organization
* Basic data analysis in *Excel* & *Google Sheets*:
  * Loading different types of data (`.csv` & `.txt`)
  * Performing basic summary calculations
  * Writing and copying formulas
  * Cleaning and wrangling data:
    * Splitting columns, concatenating, selecting n characters to the left or right
    * Find and replace
    * Wildcards (`*`, `?`, `~`)
  * Useful functions:
    * `if` statements and similar functions (`countif`, `sumif` and `sumifs`)
    * Retrieving specific values from tables (`index`, `match`, `vlookup`)
    * Merging tables with `index` + `match` or `vlookup`
  * Pivot tables
  * Exporting data (`.csv` & `.txt`)
* Other tools to clean and transform data: *OpenRefine*
* Extracting tables from *PDFs*
* *Python* installation troubleshooting

### Tuesday, June 4
*Fundamentals of programming*
* Overview of the "stack":
  * How does it all fit together: Python, R, SQL, Jupyter Notebook, Anaconda, Pandas, Command Line, Version Control
* Introduction to the command line
* What is *Python*, what is it used for, and how is it different from other languages (R, Java, JavaScript, C++, SQL, Markdown, HTML, CSS)
* Introduction to programming:
  * Variables and data types
  * Comments
  * Operations
  * `if` `else` statements
  * Errors
  * `try` `catch` statements
  * Loops
  * Functions
  * Objects

### Wednesday, June 5
*Fundamentals of data analysis & exploratory data visualization*
* Overview of the libraries: *Pandas*, *Numpy* & *Matplotlib*
* What is a dataframe?
* How to import data
* Useful functions to describe and summarize a dataset:
  * `head`, `tail`, `size`, `count`, `shape`, `describe`, `unique`
* How to filter dataframes and how to create semi-random samples
* Replacing values and NaN
* Changing types of data
* Grouping values
* Joining and merging datasets
* Exploratory data visualization
* Exporting graphs and files

### Thursday, June 6
*Web scrapping, APIs & submitting online forms*
* Basics of the web:
  * HTML, CSS, JavaScript
  * Basic structure of a website
  * Inspector tools (Firefox, Chrome, Safari)
* Querying APIs with *Python*
  * Requests
  * Two factor authentication
* Web-scrapping with *Python* and *Beautiful Soup*:
  * Getting a site and extracting useful information into a dataframe
* Automatically submitting forms with *Python* and *Selenium*

### Friday, June 7
*Introduction to text analysis & SQL*
* Text analysis and regular expressions:
  * Cleaning and transforming text datasets (lemmatizing)
  * Extracting insights from text:
    * Counting words
    * n-grams
    * Concordance
    * Lexical diversity
    * Sentiment analysis
* Introduction to SQL:
  * Basic syntax
  * Building a database and importing data
  * Querying a database
  * Joins and merges
  * Exporting data

### Other topics
Here are some of the other topics we might explore if time allows it:
* Web basics: building your own site
* Version control (git & Github)
* Creating a bot on AWS to query APIs or scrape a website
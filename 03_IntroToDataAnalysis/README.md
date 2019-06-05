# Introduction to Data Analysis

## Continuation from last class
* Data is plural
* **comments**
* Loops + `while`
  * Coin flip example
  * Random sample:
    * Vanilla Python
        ```
        from random import sample 
        list1 = [1, 2, 3, 4, 5]  
        print(sample(list1,3)) 
        ```
    * Pandas: `df['num_legs'].sample(n=3, random_state=1)` or `df.sample(frac=0.5, replace=True, random_state=1)`
* Conditionals
* Functions
* Handling errors
* Objects
* [Python cheatsheet](https://github.com/computationaljournalism/columbia2019/blob/master/cheatsheets/Python_Cheatsheet.ipynb)
* Load education data in Python (`import csv`)
* Look back to one of Buzzfeed's Jupyter Notebooks?
* Share the Dropbox folder with the group

## References
* [Datacamp Jupyter Notebook shortcuts](https://towardsdatascience.com/jypyter-notebook-shortcuts-bf0101a98330)

## Pandas & dataframes (+Numpy)
* What are they?
* Why are they better?

### Exercise 1A - Load taxi data and explore it
* Reproducing research from Ben Wellington - [How software in half of NYC cabs generates $5.2 million a year in extra tips](https://iquantny.tumblr.com/post/107245431809/how-software-in-half-of-nyc-cabs-generates-52)
* [Download](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page) taxi data for October 2014.
* Why October?
* Checkout notebook to export one week of data
* There's a white space in the front of the headers
### Exercise 1B - Load the old-school way and explore it

## Reproduce Ben's analysis
* Should we only do weekdays? Probably
* You could also do this with a random sample ==> show how to get one
* `head(n)` to show more rows when you print the head

## Pending
* Mapping: top origins or destinations for tippers
* Join tables
* Look at a Buzzfeed notebook
* Random sample Pandas
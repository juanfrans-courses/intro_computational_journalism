# Excel, Google Sheets, OpenRefine & PDFs

## Introductions & overview
* Introductions:
  * Background & experience
  * Expectations for the course
  * Equipment
  * Possible datasets to explore
  * Common tasks and workflows
  * Stories to reproduce
  * Need for more web & visualization?
* Overview of the course

## Principles of data processing
The question is, how do we organize and write our analysis or code so that in the future, we and others, can understand, test, and reproduced what we have done.

Here are some principles we are aiming for:
* **Transparency**: we can review every step in the process
* **Auditability**: we can test every step along the way
* **Reproducibility**: every person that does this analysis gets the same results, every single time
* **Scalability**: the same process can be done with more than one file, by more than one person, or more than one time
* No overwriting raw data
* Try to reduce complexity
* Separate **data** from **logic**
* Raw data often says more about the **collection** process than about **reality**

There is a question as to how much effort and attention we should put into documenting our process. A good documentation certainly helps, but it is extremely hard to make it complete and to keep it up to date. In many cases it would actually be better to write code in a way that it is self explanatory and does not need separate documentation.

This way of thinking should also be reflected in the way you organize your folders and files:
* One way of organizing your data and files to help achieve these principles is the following:
  * Input/ (starting files, raw files, files downloaded or given to us by our sources)
  * Src/ ("source", code)
  * Output/ (transformed, cleaned data, or graphs, charts, reports)
* This basic structure can be expanded and subdivided into individual "tasks" or operations:
  * ImportData/ (eg. transforming data from an Excel file into a `.csv`)
    * Input/
    * Src/
    * Output/
  * CleanData/ (eg. removing rows with missing values)
    * Input/ (this will probably be, or point towards, the output files from the previous task)
    * Src/
    * Output/
  * AggregatingByLocation/ (eg. aggregating data by location into neighborhoods)
    * Input/ (this will probably be, or point towards, the output files from the previous task)
    * Src/
    * Output/
  * JoiningWithDemographics/ (eg. joining demographic data)
    * Input/ (this will probably be, or point towards, the output files from the previous task)
    * Src/
    * Output/
  * Analysis/
    * Input/ (this will probably be, or point towards, the output files from the previous task)
    * Src/
    * Output/
* At a more complex level, the input files could be replaced by "symlinks" (symbolic links): `ln -s "/Users/name/myFile" "/Users/name/Desktop/myLink"`

## Basic data analysis in Excel & Google Sheets
### Exercise 1 - Importing data
The data for this exercise comes from the [Education Data Explorer](https://educationdata.urban.org/data-explorer/) and from the [US Census Bureau Small Area Income and Poverty Estimates (SAIPE)](https://www.census.gov/data/datasets/2016/demo/saipe.html). You can find a downloaded version of the data [here](data/EducationData).

#### Basic import
* *Note that if you import your data to Google Sheets you will be uploading it to Google's servers and effectively sharing it with them. If privacy is essential you should avoid using any cloud service.*
* Because Excel and Google Sheets often convert text to numbers or text to dates automatically, it is highly recommended that instead of double-clicking on your files, you always use Excel's or Google Sheets menu:
  * In Excel open a new file and do `Data/Get External Data/Import Text File`
  * In Google Sheets do `File/Import`
* Follow the prompts and make sure the delimiter is the right one (in this case commas) and the columns that need to be text are marked as such. In Google Sheet, you can just import all as text.

#### Encodings
Often, Excel will not choose the right encoding to read a specific file. In these cases you will see certain special characters appear as question marks or squares or diamonds. If you notice this, you should make sure that when you import the file you choose the right encoding, which will usually be `utf-8`.

#### Special delimiters
Sometimes a file is neither comma nor tab, nor semicolon delimited. Sometimes the columns are based on the position of the characters. In this case, you can either divide the columns in the import menu or do it afterwards using the `left`, `right` and `mid` formulas. Those formulas take the following form:
* `=left(string, position_from_left)`
* `=right(string, position_from_right)`
* `=mid(string, position, number_of_characters_to_extract)`

There are other ways of splitting or combining columns and text:
* In Excel `Data/Text to Columns...` takes a block of text and splits it into two or more columns based on a given character or set of characters.
* In Google Sheets you can right click on the column and choose `Split text to columns...`
* To aggregate columns (or values) you can use the `concatenate` function. This function takes the following form: `=concatenate(text1, text2, text3...)`. The text here can be either hard-coded text or reference to a cell.

Finally, to clean a table you can use the `Edit/Find/Replace...` function in Excel to replace all instances of a value (or lack of) with another value. This tool takes in wildcards (see below).

### Exercise 2 - Basic summary calculations
Some of the basic summary calculations you can perform in Excel or Google Sheets are:
* Mean: `=average(range)`
* Median: `=median(range)`
* Standard deviation: `=stdev(range)`

These three formulas automatically ignore text in the range.

### Exercise 3 - If statements
`if` statements perform simple logical tests and return a specific value for a `true` result and another for a `false` result:
* The simplest syntax of this function is `=if(logical_test, [value_if_true], [value_if_false])`
* You can also nest multiple `if` statements in one formula. This would take the following form: `=if(logical_test, if(logical_test, [value_if_true], [value_if_false]), [value_if_false])`
* There are many more functions based on this simple logic, such as:
  * `countif`, which counts the number of times a specific value occurs in a table. Its basic syntax is `=countif(range, value)`
  * `sumif`, which sums values based on a specific logical test. Its basic syntax is `=sumif(range, criteria, [sum_range])`
  * `sumifs`, which sums based on more than one logical test. Its basic syntax is `=sumifs(sum_range, range1, criteria1, [range2], [criteria2], ...)`
* **Wildcards**: In these formulas (and in many other operations) you may use `*`, `?`, or `~` as wildcards:
  * `*` stands for multiple characters (eg. `pq*`, `*pq`, `p*q`)
  * `?` stands for only one character (eg. `c*ty` is different than `c?ty`)
  * `~` is used when you actually have a `?` or a `*` that is not a wildcard (eg. `who~?*`)

### Exercise 4 - Looking up values
`index` and `match` functions let you lookup the location of a value or the value itself based on certain criteria:
* The `index` function returns the value based on a table, row number, and row column:
  * It has the following syntax: `=index(array, row_num, [column_num])`
  * It can also take a series of tables: `=index((table1, table2, table3), row_num, [column_num], [area_num])`
  * And it can also return a whole row or column, just select the output cells and click `ctrl + shift + enter`
* The `match` function returns the position of a value in a row, column or table:
  * It takes the following syntax: `=match(lookup_value, lookup_array, match_type)`
  * `match_type` is either `True` or `False`. `False` requires an exact match, and `True` will use an approximation (eg. 575 will match to 500, after sorting A to Z, the largest value that's less than the lookup value)
  * If `match_type` is `False` and the `lookup_value` is text, the lookup value can also include *wildcards*.
* Finally, you can use the `index` and `match` functions together to get a specific value based on a condition:
  * Basic syntax: `{=index(array, match(lookup_value, lookup_column, FALSE), [column_num])`
  * And you can also use multiple criteria like this: `=index(array, match(1, (A1 = range1 * B1 = range2 * C1 = range3), 0))}` (use ctrl + shift + enter)
* *Note that in Excel, as well as in Google Sheets, the first column is identified as column number 1. This is not the case in programming (Python and others), where the first column is identified as column number 0.*

### Exercise 5 - Joining tables
There are a couple of ways of joining tables in Excel or Google Sheets, but the most common one is through the `vlookup` function, which allows you to lookup a value in a table and return a value on the same row but from a different column.
* The basic syntax of this function is `=vlookup(value, table, col_index, [range_lookup])`
* Just as in the `match` function the `range_lookup` can be `True` or `False`. `False` requires an exact match, whereas `True` will approximate.
* In addition, wildcards can also be included in the `value` field when dealing with text.
* To use the `vlookup` function to join two tables, you need to copy a modified version of the formula in every cell:
  * That modified version, takes the following form: `=vlookup(value, $table, $col_index, [range_lookup])`.
  * The `$` sign allows you to copy a formula without it changing the reference cells. Since all the values we are looking up will reference the same table and column, we must use the `$` sign to prevent these ranges from changing as we copy the formula.

### Exercise 6 - Pivot tables
Pivot tables are one of the most useful tools in Excel or Google Sheets. They allow you to aggregate data from a table in a variety of ways. In addition, creating them is extremely easy:
* In Excel go to `Data/Summarize with Pivot Table`
* And in Google Sheets do `Data/Pivot Table...`
* This operation will lead you to a menu where you can choose the location of your pivot table. Because you will certainly experiment with different configurations of your table, and it will thus expand and contract, it is recommended to create them in their own separate sheet.
* In the new sheet you will see a menu that allows you to drag and drop the different columns in your table into the different components of the pivot table: filters, rows, columns, and values.
* And the values themselves can be aggregated with different operations: sum, count, maximum, minimum, average, standard deviation, etc.
* Finally, once you have the pivot table that reflects your analysis, you can copy it and paste it in its own sheet, making sure that you **paste as value**.
* You can then export this sheet as its own `.csv` file.

## OpenRefine
[OpenRefine](http://openrefine.org/), formerly Google Refine, is a program to clean and transform messy data. It contains a powerful set of tools that allow you to group and visualize your data, understand where some of its errors might lie, and transform it.

In addition, it has two more advantages:
* It does not require that you upload your data to a cloud service. Yes, it works in the browser, but it does through a localhost, which means that the data you use always stays in your computer.
* It maintains a log of the transformations you perform to your data, which means that you can go back to any point at any time, and you also have a record of what you did to your data to clean it and transform it.

### Exercise 7 - Load data into OpenRefine & clean columns
For these exercises we will be using a subset of [New York City's 311 Service Requests](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9) data. You can find a downloaded version of the data [here](data/311_RodentData_2019/311_RodentData_2019.csv)

First import the data into OpenRefine. Select the file and make sure all the import options are correct:
* Comma separated
* First row contains headers
* `""` are used to enclose cells that contain separators (in this case, commas)
* If all is correct, create the project.

Even though the 311 data is pretty clean, it still contains problems. For example, look at the column `City`. You will notice that a lot of the cells contain `NEW YORK`, but others contain boroughs `QUEENS` or `BROOKLYN`, others even contain the name of the neighborhood, and some of those names are in uppercase and others in lowercase.

To correct some of this, click on the dropdown menu next to the column title and select `Facet/Text facet`. On the right hand panel you will see the list of all the values, sorted alphabetically. There are 88 different values.

To make them all title case, click again on the dropdown menu next to the header and select `Edit cells/Common transforms/To titlecase`. You will notice that now there are only 48 different values.

Take a look at the changes you've done and the history you've created for this file. This is one of the great features in *OpenRefine* that goes a long way towards *reproducibility*.

### Exercise 8 - Loading another dataset into OpenRefine
Now load the educational dataset to learn how to load character delimited files:
* The character spacing for the 2016 file should be `2,6,73,9,9,9,11,10`. *OpenRefine* takes the number of spaces between characters, not from the start of the line.
* Some other cleaning and transforming techniques are:
  * Removing trailing spaces
  * Transforming text to numbers
  * Renaming columns
* Finally, when the dataset is clean, export it as a tab delimited file. There is single right delimiter to choose. It all depends on the content of the dataset and whether or not that particular delimiter might be found within the dataset.

Note: *OpenRefine's* projects might get too large and take up too much memory. It is always useful to take a look at what projects you've created and delete the ones that you no longer need. However, always make a point to document well what transformations your data went through.

## Putting it all together
### Exercise 9 - Exploring Federal Election Commission data
Use what you have learned to clean, transform, explore, join and analyze the Federal Election Commission 2015 - 2016 [datasets](data/FederalElectionCommission). These datasets were downloaded from the [Federal Election Commission site](https://classic.fec.gov/finance/disclosure/ftpdet.shtml#a2015_2016) and on that site you can find their corresponding data dictionaries.

## Tables from PDFs
*Tabula* is a very useful tool that allows you to extract tables from `.pdf` files into `.csv` or *Excel* spreadsheets. Just as with *OpenRefine*, *Tabula* through your browser but does not upload your documents to the cloud.

You can install *Tabula* by following the instructions [here](https://tabula.technology/).

### Exercise 10 - Extract table data from NYPD report
Use *Tabula* to extract the tables embedded in this [NYPD 2017 End-Of-Year Report](data/NYPD_EndOfYearReport) originally downloaded from [here](https://www1.nyc.gov/assets/nypd/downloads/pdf/analysis_and_planning/year-end-2017-enforcement-report.pdf).

As with *OpenRefine*, you need to check where *Tabula* saves your documents and manage their storage.

## Optical Character Recognition
When `.pdf` files are not encoded as text but as images, *Optical Character Recognition* (*OCR*) tools or software might be necessary to extract information into formats that we can analyze.

The easiest way of doing this might be through *Google Documents*. If you are comfortable with uploading your documents to a cloud service, you can upload your documents to your *Google Drive*, right click on them, and choose `Open with/Google Docs`. *Google* will then attempt to convert your image documents (`.pdf`, `.jpg`, `.png`, or others) to text.

If you are not comfortable with uploading your documents to the cloud you might want to try [*Tesseract*](https://github.com/tesseract-ocr/tesseract/wiki) which will run locally on your machine.

Finally, *Amazon* just announced a service called [*Textract*](https://aws.amazon.com/textract/) which promises to scan large amounts of documents in very little time and extract text from them.
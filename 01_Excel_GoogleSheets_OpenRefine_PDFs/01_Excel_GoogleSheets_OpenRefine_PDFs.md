# Excel, Google Sheets, OpenRefine & PDFs

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

#### Basic summary calculations
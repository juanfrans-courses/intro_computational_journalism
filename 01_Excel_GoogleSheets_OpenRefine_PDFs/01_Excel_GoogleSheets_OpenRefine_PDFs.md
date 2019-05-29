# Excel, Google Sheets, OpenRefine & PDFs

### Principles of data processing
The question is, how do we organize and write our analysis (code) so that in the future, we and others, can understand, test, and reproduced what we have done.

Here are some principles we are aiming for:
* *Transparency*: we can review every step in the process
* *Auditability*: we can test every step along the way
* *Reproducibility*: every person that does this analysis gets the same results, every single time
* *Scalability*: the same process can be done with more than one file, by more than one person, or more than one time
* No overwriting raw data
* Try to reduce complexity
* Separate *data* from *logic*
* Raw data often says more about the *collection* process than about *reality*

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
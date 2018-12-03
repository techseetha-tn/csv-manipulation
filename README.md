# perfect-practise
Requirement details: 
Program that would 
(1) read "specialized" CSV files. The application uses LP and TOU sample types.
(2) calculate median using a column from the CSV file, configured in App.config as "MedianReferenceColumn"
(3) find records that are 20% above or below the median. The percentage factor is configured as "PercentageFactor"
(4) print the abnormal records in the format {file name} {datetime} {value} {median value} where datetime must be a column in teh CSV. This is also configured in App.config as "DateTimeColumn"

Architecture details:

A simple console application is used (Report.Solution). Report.Provider layer takes care of processing the CSV files. It follows Single Responsibility and Factory design pattern. Entities are defined to hold CSV column details, input parameters and output parameters. Business logic is placed in Utility which is common for the files.
NLog unit test framework is used to write unit test cases.

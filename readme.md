# Ingestion Task

This exercise is designed to give an opportunity to show how you design and write code. It is not intended to be particularly
complex, and the emphasis here should be on clarity and correctness of code.

Please do not use any AI,

1. Take the CSV files and write out into multiple parquet files, each containing 10000 rows. The expected output schema is:

PageID - integer
PageName - string
UserID - integer
UserLocation - string
ViewDateTime - timestamp
DeviceType - string enum(Tablet, Mobile or Desktop)
UserAgent - string
BrowserType - string
SessionDuration - string format("minutes:seconds")
Year - string(4) - year from timestamp
Month - string(2) - month from timestamp - zero padded
Day - string(2) - day of month from timestamp - zero padded
DayPart - enum(

- "Morning" if between 7am and 9am,
- "Lunch" if between 12am and 2pm,
- "Evening" if between 5pm and 10pm,
- "Night" if between 10pm and 7am,
- "" if none of the above
  )

And rows with errors in should be not included in the parquet files, but warnings should be created for each failing row

Please include some timing information in the console output

2. Repeat with the 2nd CSV file

3. Add to the script the distinct set of browser type and versions in the dataset

# Portfolio Project 2 - PowerBI + Power Query - Data Professionals Survey

Welcome to my second portfolio project. In this **data transformation and visualisation project**, I transform data from a survey of professionals in the data industries in Power Query and then visualise it as an interactive 2-page dashboard with PowerBI.

In this repository, there is 1 PowerBI file (the dashboard project) and 1 Excel worksheet (the dataset).

The original data required extensive cleaning before visualisation, but instead of doing this in Excel, I have done it within the PowerBI project itself using Power Query.
 

**Transforming Data 1 - Yearly Salary**

For example, the dataset column listing survey responses for "Current yearly salary (in USD)" is listed in alphanumeric salary ranges, e.g. 41k-65k, 106-125k etc. This format is not numeric, and also it is a range, not an individual number, making it unsuitable for visualisation.

Therefore, I first converted the ranges into individual numbers by splitting the column into two new columns, using the hyphen "-" as a delimiter. This gave me e.g. "41k" and "65k" in 2 separate columns. I then transformed each alphanumeric value into a numeric value, e.g. replacing "45k" with "45,000".

Then, using these 2 new numeric columns, I calculated a new column of the average of the 2 values. While this may not be optimal in determining industry average salaries, given that the original data collected itself was in a range format and not individual responses, this method gives us a suitable way of visualising the data, while still being reasonable enough to glean insights from the data.
 

**Transforming Data 2 - Others: Custom Responses**

I did similar transformation of data in other columns. Wherever responses were "Others", the original survey listed "Others: Please specify..." with each individual allowed to provide a custom response. I again split the columns, using the semi-colon ":" as the delimiter, and then deleted the second column with the custom responses. This retained all "Others" responses in the original column along with the main options, allowing me to simplify visualisation with all "Others" responses grouped together.
 

**Transforming Data 3 - Difficulty Level**

One of the questions on the survey was "How difficult was it for you to break into Data?". The 5 response options were "Very Difficult", "Difficult", "Neutral", "Easy" and "Very Easy".

However, these are text values. So during visualisation, PowerBI listed them in alphabetical order, i.e. Difficult - Easy - Neutral -Very Difficult - Very Easy. In order to get the desired order of difficulty, I created a duplicate column and replaced each value with an added number in front, i.e. "1 - Very Difficult", "2 - Difficult", "3 - Neutral", "4 - Easy" and "5 - Very Easy".

I then had PowerBI sort the original difficulty level column (included in the table) according to the new duplicate column (with numbers added). This then allowed the "Getting a Job in Data" table on dashboard page 2 to have the difficulty levels listed in order from Very Easy down to Very Difficult, as PowerBI could now simply match each response in the original column to its corresponding value in the numbered column.

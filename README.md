# Portfolio Project 2 - PowerBI and Power Query - Data Professionals Survey

Welcome to my second portfolio project. In this **data transformation and visualisation project**, I transform data from a survey of data professionals across industries (data scientists, data analysts, data engineers etc.) in Power Query and then visualise it as an interactive 2-page dashboard with PowerBI.

The original data required extensive cleaning before visualisation, but instead of doing this in Excel, I have done it within the PowerBI project itself using Power Query.

**Transforming Data 1 - Yearly Salary**

For example, the dataset column listing survey responses for "Current yearly salary (in USD)" is listed in alphanumeric salary ranges, e.g. 41k-65k, 106-125k etc. This format is not numeric, and also it is a range, not an individual number, making it unsuitable for visualisation.

Therefore, I first converted the ranges into individual numbers by splitting the column into two new columns, using the hyphen "-" as a delimiter. This gave me e.g. "41k" and "65k" in 2 separate columns. I then transformed each alphanumeric value into a numeric value, e.g. replacing "45k" with "45,000".

Then, using these 2 new numeric columns, I calculated a new column of the average of the 2 values. While this may not be optimal in determining industry average salaries, given that the original data collected itself was in a range format and not individual responses, this method gives us a suitable way of visualising the data, while still being reasonable enough to glean insights from the data.

![portfolio_2-image-transformating_data_1](https://user-images.githubusercontent.com/122973220/213428543-0ea1cd43-a23e-47a4-b408-9f9cab894b56.jpg)

**Transforming Data 2 - Others: Custom Responses**

I did similar transformation of data in other columns. Wherever responses were "Others", the original survey listed "Others: Please specify..." with each individual allowed to provide a custom response. I again split the columns, using the semi-colon ":" as the delimiter, and then deleted the second column with the custom responses. This retained all "Others" responses in the original column along with the main options, allowing me to simplify visualisation with all "Others" responses grouped together.

![portfolio_2-image-transformating_data_2](https://user-images.githubusercontent.com/122973220/213428528-ee97c2c3-ed15-4b35-92a2-2522853b7d15.jpg)

**Transforming Data 3 - Difficulty Level**

One of the questions on the survey was "How difficult was it for you to break into Data?". The 5 response options were "Very Difficult", "Difficult", "Neutral", "Easy" and "Very Easy".

However, these are **_text_** values. So during visualisation, PowerBI listed them in **_alphabetical_** order, i.e. Difficult - Easy - Neutral -Very Difficult - Very Easy. In order to get the desired order of difficulty, I created a duplicate column called Difficulty Code, adding a number in front of each value, i.e. "1 (Very Easy)", "2 (Easy)", "3 (Neutral)", "4 (Difficult)" and "5 (Very Difficult)".

I then selected the original Difficulty Level column (which is the column I included in the table) and had PowerBI "sort by column" (under column tools) by the new Diffculty Code column (with numbers added). This then allowed the "Getting a Job in Data" table on dashboard page 2 to have the difficulty levels listed in order from Very Easy down to Very Difficult, as PowerBI could now simply match each Difficulty Level response in the original column to its corresponding Difficulty Code value in the numbered column.

![portfolio_2-image-transformating_data_3](https://user-images.githubusercontent.com/122973220/213427728-b7315e85-b628-44ac-b980-7eb19a75beb7.jpg)

**Finished Dashboard**

Here are the screenshots of the finished dashboard.

Page 1

![portfolio_2-image-dashboard_1](https://user-images.githubusercontent.com/122973220/213431666-8fd8b534-cd1f-40a3-9f6a-aecc04776e3b.jpg)

Page 2

![portfolio_2-image-dashboard_2](https://user-images.githubusercontent.com/122973220/213431780-c9ed74b9-e2f6-46c9-8fcf-b83a26491259.jpg)


**Project Files and Data Source Citation**

The survey was conducted and dataset provided by Alex Freberg (also known as Alex The Analyst), special thanks to him - https://www.alextheanalyst.com/

In this repository, there is 1 PowerBI file (the dashboard project) and 1 Excel worksheet (the dataset).

# English Wikipedia Monthly Article Traffic Dataset

This repository encompasses data and analyses for the project that emphasizes Professionalism & Reproducibility. The primary objective was to construct, analyze, and publish a dataset showcasing monthly article traffic for a selected set of pages from English Wikipedia spanning from July 1, 2015, to September 30, 2023.

## Data Source

The selected set of pages can be accessed [here](./thank_the_academy.AUG.2023.csv%20-%20thank_the_academy.AUG.2023b.csv). This dataset includes the names of the articles and their corresponding links.

## Project Process

### Step 1: Data Acquisition

#### Goal
To measure article traffic, data was collected from the Pageviews API, providing access to desktop, mobile web, and mobile app traffic data from July 2015 through the previous complete month.

#### Key Actions
1. Set the API endpoint for the Pagecounts API.
2. Parse the excel sheet of a [subset](thank_the_academy.AUG.2023.csv%20-%20thank_the_academy.AUG.2023b.csv) of the English Wikipedia that represents a substantial number of articles about academy award-winning movies.
3. Iteratively call the API for each article across three types of accesses (desktop, mobile-web, mobile-app).
4. Merge the JSON files as per the specified file naming conventions.

#### Data Files Produced
- [Monthly Mobile Access Data](./academy_monthly_mobile_201507-202309.json): JSON file containing monthly mobile access data for the specified time range.
- [Monthly Desktop Access Data](./academy_monthly_desktop_201507-202309.json): JSON file containing monthly desktop access data for the specified time range.
- [Monthly Cumulative Data](./academy_monthly_cumulative_201507-202309.json): JSON file containing monthly cumulative data (sum of mobile and desktop traffic) for the specified time range.

### Step 2: Pre-Processing

#### Goal 
To aggregate and process the combined data to generate JSON files suitable for further analysis. 

#### Key Actions
1. Fetch data for desktop and mobile (app and web combined), summing up view counts for the respective article and timestamp.
2. Iteratively process each article's data from the JSON file (combined file) and aggregate the counts accordingly.
3. Store the final result with the appropriate naming conventions.

Here's a summary of the preprocessing steps:

`Combining Mobile and Desktop Views`: We aggregate the views from both desktop and mobile access types, categorizing them by article and timestamp. This combined data aids in generating a comprehensive view of overall traffic.

`Creating Combined JSON Objects`: For each unique combination of article and timestamp, we create a JSON object representing the combined views, specifying project details, granularity, access, and more.

`Storing JSON Objects`: The generated combined JSON objects are stored in the academy_monthly_cumulative_201507-202309.json file, capturing the overall view traffic.

`Creating Mobile-Combined JSON Objects`: Similarly, we create JSON objects for mobile traffic, following the same procedure, and store them in the academy_monthly_mobile_201507-202309.json file.

By performing these preprocessing steps, we prepare the data for further analysis and visualization, ensuring it's organized and in a suitable format for subsequent tasks.


### Step 3: Analysis

The analysis encompassed visualizing specific subsets of the data as time series using various graphs.

- Maximum and Minimum Average Page Requests
- Top 10 Peak Page Views
- Articles with Fewest Months of Data

Each of these analyses provided valuable insights into the article traffic across different access types.

## Licensing

The dataset is made available under the [Creative Commons License](https://creativecommons.org/licenses/by/4.0/).

## Wikipedia API Documentation

For further information on Wikipedia API, refer to the [official documentation](https://wikimedia.org/api/rest_v1/).

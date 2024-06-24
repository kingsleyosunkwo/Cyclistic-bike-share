# Cyclistic-bike-share
### How do annual members and casual riders use Cyclistic bikes differently?


## TABLE OF CONTENT
### Introduction
- [Project Overview](project-overview)
- [Business Task](business-task)
- [Stakeholders](stakeholders)
  
### Data Preparation
- [Data Sources](data-sources)
- [Data Organization](data-organization)
- [Data Credibility](data-credibility)
- [Data Privacy and Security](data-privacy-and-security)
- [Data Integrity Verification](data-integrity-verification)
- [Data Issues](data-issues)
- [Data Download and Storage](data-download-and-storage)
  
### Data Processing
- [Tools Used](tools-used)
- [Data Cleaning Steps](data-cleaning-steps)
- [Error Checking](error-checking)
- [Data Transformation](data-transformation)
- [Cleaning Documentation](cleaning-documentation)
  
### Exploratory Data Analysis (EDA)
- [Summary Statistics](summary-statistics)
- [Visualization of Data](visualization-of-data)
- [Trends and Relationships](trends-and-relationships)
- [EDA Results](eda-results)

### Statistical Analysis and Modeling
- [Statistical Methods Used](statistical-methods-used)
- [Modeling Steps](modeling-steps)
- [Model Results](model-results)
- [Interpretation of Results](interpretation-of-results)
  
### Data Visualization
- [Visualization Techniques](visualization-techniques)
- [Visualizations Created](visualizations-created)
- [Interpretation of Visualizations](interpretation-of-visualizations)
  
### Findings and Recommendations
- [Summary of Findings](summary-of-findings)
- [Business Insights](business-insights)
- [Recommendations](recommendations)
- [Documentation](Documentation)
  
### R Scripts
- [GitHub Workflow](github-workflow)
- [Markdown Files](markdown-files)
- [Final Report and Presentation](final-report-and-presentation)
  
### Final Report and Presentation
- [Executive Summary](executive-summary)
- [Detailed Report](detailed-report)
- [Presentation Slides](presentation-slides)
- [Appendices](appendices)
  
### Appendices
- [Data Dictionary](Data-Dictionary)
- [Additional Analysis](additional-analysis)
- [References](references)

### Introduction
---
### Project Overview
The project focuses on conducting a detailed analysis of Cyclistic bike-share data from Chicago to uncover insights that will support strategic marketing decisions. Cyclistic is aiming to maximize annual memberships by understanding how different customer segments (annual members vs. casual riders) utilize their bike-share service differently. The analysis will involve exploring trip data over the past 12 months to identify patterns, trends, and behaviors among Cyclistic users. The ultimate goal is to provide actionable recommendations that will help Cyclistic convert casual riders into annual members through targeted marketing strategies backed by data-driven insights.

### Business Task
The business task is to analyze Cyclistic bike-share data to understand how annual members and casual riders utilize the service differently. Specifically, the analysis aims to uncover behavioral patterns, usage trends, and preferences of these customer segments. The insights derived will inform the development of a new marketing strategy focused on converting casual riders into annual members. The strategy will be data-driven, leveraging findings from the analysis to enhance customer retention and maximize annual memberships, thereby driving long-term growth for Cyclistic.

### Stakeholders
1. Lily Moreno: Director of Marketing at Cyclistic, responsible for campaign development and strategic initiatives to promote the bike-share program.
2. Cyclistic Marketing Analytics Team: Data analysts tasked with collecting, analyzing, and reporting data to guide marketing strategies.
3. Cyclistic Executive Team: Decision-makers who will approve the recommended marketing strategies based on data-driven insights.
4. Cyclistic Operations Team: Responsible for the operational aspects of the bike-share program, including bike maintenance, station management, and customer support.
5. Cyclistic IT Team: Manages data infrastructure, security, and technical support for data analysis.
6. Cyclistic Customer Service Team: Provides insights into customer feedback and user experience with the bike-share service.
7. Customers (Annual Members and Casual Riders): End-users whose behaviors and preferences will be analyzed to improve service offerings and membership conversion strategies.

These stakeholders play crucial roles in various aspects of the project, from data collection and analysis to strategy implementation and operational management.

### Data Preparation
---
### Data Sources
1. Trip Data: Historical records of bike trips taken by Cyclistic users. This dataset typically includes information such as trip duration, start and end times, bike ID, user type (annual member or casual rider), and possibly additional demographic or user-specific data.
2. Station Data: Information about the bike stations managed by Cyclistic, including location coordinates, station capacity, and other operational details.
3. Weather Data: Optional but often included for seasonality analysis, weather data such as temperature, precipitation, and wind speed can provide insights into how weather conditions affect bike usage patterns.
4. Geographical Data: Geographic information system (GIS) data may be used to analyze spatial patterns of bike usage across different areas of Chicag
5. Customer Data (Optional): Demographic information, user preferences, and historical membership data may also be included if available and relevant.

### Data Organization
1. Trip Data:
- Structure: The Date is stored in CSV (Comma-Separated Values) format, of whcih i uploaded to Rstuido and converted to a database tables.
- Organization: Each row represents a single bike trip with columns for trip details such as trip duration, start time, end time, bike ID, user type, and possibly additional attributes like user demographics.
- Combining Data Files
To handle the data more efficiently, especially given the volume and the fact that the data spans from January 2024 to May 2024 in separate CSV files, I combined all these files into a single dataset. This approach ensures a seamless analysis process and helps in maintaining consistency.

Steps to Combine Data Files
---
I. Locating the Files:
All the CSV files were stored in a designated folder on my local computer.

II. Combining Files Using Command Prompt on Windows:
I used the Command Prompt to concatenate all CSV files into a single file. Below are the steps and commands used:

a. Navigate to the Folder:
Open the Command Prompt and navigate to the directory containing your CSV files.

```
C:\Users\user\Desktop\Data Analytics\Coursea\Capstone project\Cyclistic_Trip_Data Cousera Capstone Project\Raw_data_for_cyclistic_trip_data\Csv
files extracted for Cyclistic trip analysis from 2024 data
```
b. Combine the Files:
Use the following command to concatenate all CSV files into a single file named Combined_2024_Cyclistic_trip_analysis_data.csv

```
copy *.csv Combined_2024_Cyclistic_trip_analysis_data.csv
```
c. Rationale for Combining Files:
Combining the files simplifies the data processing workflow. Instead of loading multiple files and merging them within R, which can be resource-intensive, combining them beforehand reduces the computational load during the analysis phase. It also ensures that all data is in a consistent format and ready for immediate use.

d. Loading the Combined File in R:
After combining the files, the next step was to load the combined data file into R for further processing and analysis

```
# Load necessary libraries
install.packages("tidyverse")
library(tidyverse)
library(lubridate)

# Load the combined data file
combined_data <- read_csv("Combined_2024_Cyclistic_trip_analysis_data")

# Preview the first few rows of the data
head(Combined_2024_Cyclistic_trip_analysis_data)

# Check the structure of the data
str(Combined_2024_Cyclistic_trip_analysis_data)

```

- Key Fields:
### Data Credibility


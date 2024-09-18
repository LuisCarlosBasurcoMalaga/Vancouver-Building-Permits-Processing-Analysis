# Vancouver Building Permit Response Time Analysis

## Project Overview
This project focuses on analyzing the time it takes for the Vancouver government to process and respond to building permit requests. The permits include construction, demolition, and modification. By leveraging AWS services such as S3, Glue, CloudWatch, EC2, and DataBrew, we are able to ingest, clean, analyze, and visualize the response times for different types of permits.

__The main objective is to:__

Calculate the average time taken for the government to respond to permit requests.
Identify patterns in response times based on the type of work 'Addition / Alteration', 'New Building' 'Demolition / Deconstruction', 'Salvage and Abatement', 'Outdoor Uses (No Buildings Proposed)', 'Temporary Building / Structure'.
Provide visual insights for better understanding of response time distribution and government efficiency.
AWS Services Used.

# Vancouver-Building-Permits-Processing-Analysis

# Exploratory Data Analysis

**Project Description:** _Exploratory Data Analysis for Vancouver Building Permits Processing Analysis_

**Project Title:** _Exploratory Data Analysis for Vancouver-Building-Permits-Processing-Analysis_

__Objective:__ 

**Understand the structure and quality of the data:** Identify and correct potential problems in the data, such as missing values, duplicates or inconsistencies. This ensures that the data are reliable for further analysis.

**Initial pattern detection:** Analyze the distribution of critical variables such as “permitLapsedDays” to understand how response times vary by permit type and other characteristics (such as job type or geographic area).

**Visualizing trends:** Identify trends over time (e.g., have response times increased in recent years?) using graphs to help visualize changes in wait days.

**Identifying relationships:** Examine possible relationships between variables, such as whether certain types of jobs or specific permits tend to take longer to be approved.

**Establish hypotheses:** From the patterns and relationships observed, formulate hypotheses about factors influencing delay times.

## Data Collection and Preparation:

The dataset was sourced from the City of Vancouver Open Data Portal, which provides publicly available information on building permits issued by the city.

Permit Types: 'Addition / Alteration', 'New Building' 'Demolition / Deconstruction', 'Salvage and Abatement', 'Outdoor Uses (No Buildings Proposed)', 'Temporary Building / Structure'.
Attributes: Permit number, issue date, project description, type of work, project value, response time, etc.

# Dataset: 

+ **PermitNumber:** A unique identification number assigned to each permit issued.
+ **PermitNumberCreatedDate:** The date on which the permit number was created.
+ **IssueDate:** The date the permit was officially issued.
+ **PermitElapsedDays:** Number of days that elapsed between the application and permit issuance.
+ **ProjectValue:** Estimated monetary value of the project related to the permit.
+ **TypeOfWork:** Type of work to be performed (e.g., construction, demolition, modification).
+ **Address:** Address of the location where the project will be performed.
+ **ProjectDescription:** Brief description of the project for which the permit is being requested.
+ **PermitCategory:** Permit category according to the type of project.
+ **Applicant:** Name of the applicant who managed the permit.
+ **ApplicantAddress:** Applicant's address.
+ **PropertyUse:** Intended use of the property (residential, commercial, etc.).
+ **SpecificUseCategory:** Specific property use category (more detailed than PropertyUse).
+ **Building Contractor:** Name of the contractor performing the work.
+ **BuildingContractorAddress:** Contractor's address.
+ **IssueYear:** The year in which the permit was issued.
+ **GeoLocalArea:** Local geographic area associated with the project.
+ **Geom:** Geospatial geometry of the project site.
+ **YearMonth:** Year and month in which the permit was issued.
+ **geo_point_2d:** Geographic coordinates (latitude and longitude) of the project site.



The following AWS services were utilized to manage, process, and analyze the data:

**S3:**
Stores raw and processed data. Used to store both original and transformed data.

**AWS Glue DataBrew:**
Visual tool for preparing and exploring data. It is ideal for exploratory analysis without writing code.

**Amazon Athena:**
Allows you to run SQL queries directly on data stored in Amazon S3, facilitating exploratory analysis of large volumes of data.

**Amazon SageMaker:**
Although primarily a tool for machine learning, you can also use SageMaker for advanced exploratory analysis using notebooks and visualizations.

**Amazon QuickSight:**
BI tool for creating dashboards and interactive visualizations.

## Descriptive Statistics:

During the Data Collection phase of my project analyzing building permit response times in the City of Vancouver, I observed that the dataset was of exceptionally high quality. The data was free of duplicates, missing values, and formatting errors, which allowed for a smooth transition into the analysis phase without extensive data cleaning. This high data integrity ensured that the insights derived were based on accurate and reliable information.




Inspect the structure of the dataset (columns, data types, missing values).
Check distribution of permits by type of work and by year.
Summary Statistics

Calculate basic statistics (mean, median, mode) for the response time, project value, etc.
Visualize distributions of response time to understand the overall trend.
Analysis by Type of Work

Group permits by type (construction, demolition, modification) and analyze their respective response times.
Compare the average response time for each category.
Time Series Analysis

Plot the permit issuance dates to identify trends over time.
Identify any seasonality or periods where response times fluctuate significantly.
Screenshots:

Response time distribution graph.
Permit types breakdown by year.










o	Load the Titanic dataset using Python libraries like Pandas.
o	Perform initial data cleaning, which includes handling missing values, correcting data types, and renaming columns for clarity.
2-	Descriptive Statistics:
o	Generate summary statistics (mean, median, mode) for numerical features (like Age and Fare) and frequency distributions for categorical features (like Pclass and Sex).
3-	Data Visualization:
o	Create visualizations to illustrate key insights:
	Histograms and Boxplots: Analyze the distribution of continuous variables like Age and Fare.
	Bar Charts: Showcase survival rates across different categories (e.g., Sex, Pclass).
	Heatmaps: Visualize correlations between numerical variables.
4-	Survival Analysis:
o	Compare survival rates:
	By gender: Determine if there is a significant difference in survival rates between male and female passengers.
	By class: Analyze how passenger class affected survival chances.
	By age group: Create age bins to assess survival across different age demographics.
5-	Insights and Findings:
o	Summarize the findings based on data visualizations and statistical analyses, highlighting notable trends and patterns (e.g., women and children had higher survival rates, first-class passengers had a significant survival advantage).
6-	Conclusion:
o	Discuss the implications of the findings and suggest further analyses or data-driven decisions that could be explored, such as building predictive models to classify survival based on passenger features.






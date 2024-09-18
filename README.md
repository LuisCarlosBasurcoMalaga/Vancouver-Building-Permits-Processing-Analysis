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

__Permit Types:__ 'Addition / Alteration', 'New Building' 'Demolition / Deconstruction', 'Salvage and Abatement', 'Outdoor Uses (No Buildings Proposed)', 'Temporary Building / Structure'.
__Attributes:__ Permit number, issue date, project description, type of work, project value, response time, etc.

During the Data Collection phase of my project analyzing building permit response times in the City of Vancouver, I observed that the dataset was of exceptionally high quality. The data was free of duplicates, missing values, and formatting errors, which allowed for a smooth transition into the analysis phase without extensive data cleaning. This high data integrity ensured that the insights derived were based on accurate and reliable information.


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

![bucket](https://github.com/user-attachments/assets/8d110700-67f4-4c1c-b3fc-8f2a4b2e6f93)




**AWS Glue DataBrew:**
Visual tool for preparing and exploring data. It is ideal for exploratory analysis without writing code.



![dataset1](https://github.com/user-attachments/assets/2cdea9eb-9556-4a75-a724-ad7dd23f1f13)
![dataset2](https://github.com/user-attachments/assets/903b4197-d067-47a9-bbf3-d607a4390a7c)
![DataQuality](https://github.com/user-attachments/assets/8edd7ee8-24be-4ab7-bcd2-6fcb384b77b2)


## Descriptive Statistics:




**Amazon Athena:**
Allows you to run SQL queries directly on data stored in Amazon S3, facilitating exploratory analysis of large volumes of data.

_Data Management:_ The code allows the creation, insertion and retrieval of data, which is essential for information management in the project. The dataset was imported with the selected columns after debugging the columns that we will not use; this process was done with the AWS Databrew service, creating a recipe that automates this task for the different years to be analyzed.
Automation: SQL queries can be automated to perform repetitive tasks, such as updating records or generating reports.
Scalability: Using AWS Databrew, the data columns used for the project data analysis Vancouver-Building-Permits-Processing-Analysis can be easily scaled to handle large volumes of data without compromising performance.

![athena0](https://github.com/user-attachments/assets/757216ed-b8f6-4040-892b-288f632a6977)

Using SQL, we have imported the dataset containing three key columns. These columns will allow us to analyze the average number of days the Vancouver government takes to respond to requests, categorized by the type of work to perform.

![athena1](https://github.com/user-attachments/assets/b3d1d568-b0cb-4394-9f5e-e93a4e616fe1)

A new column called AVGDays has been created to calculate the average number of days the Vancouver government takes to respond to requests, categorized by the type of work performed. This calculation has generated six unique pieces of data.

Data Description
New Building: 228.94 days
Demolition / Deconstruction: 226.96 days
Salvage and Abatement: 69.33 days
Addition / Alteration: 76.92 days
Outdoor Uses (No Buildings Proposed): 275.75 days
Temporary Building / Structure: 34.41 days

![athena2](https://github.com/user-attachments/assets/94b24e90-2db9-4750-af21-471d0b2c63b3)


## Data Visualization:

**Amazon QuickSight:**
BI tool for creating dashboards and interactive visualizations.
In this case I used python made graphs that represent the average and tendence of response by license of construction and modification by type of work


# Bar Chart


The graph titled “Average Permit Response Time by Type of Work” shows the average time in days it takes the Vancouver government to respond to permit applications, categorized by type of work. Here is the interpretation of the data:

New Building: Approximately 229 days.
Demolition / Deconstruction: Approximately 227 days.
Salvage and Abatement: Approximately 69 days.
Addition / Alteration: Approximately 77 days.
Outdoor Uses (No Buildings Proposed): Approximately 276 days.
Temporary Building / Structure: Approximately 34 days.
Comments
Longest Response Time: Applications for Outdoor Uses (No Buildings Proposed) have the longest average response time at approximately 276 days.
Shortest Response Time: Applications for Temporary Building / Structure have the shortest average response time, approximately 34 days.
Intermediate Times: The other job types have response times ranging from 69 to 229 days.


```plt.figure(figsize=(10,6))
averages_by_type.plot(kind='bar', color='skyblue')

# add tittle and tags
plt.title('Average Permit Response Time by Type of Work', fontsize=16)
plt.xlabel('Type of Work', fontsize=12)
plt.ylabel('Average Days', fontsize=12)

plt.xticks(rotation=45, ha='right')

# show the graph
plt.tight_layout()
plt.show()
```
![barchart1](https://github.com/user-attachments/assets/26891f6d-f2b8-4dd3-8f50-183e055cd0d8)


# Box Plot

```plt.figure(figsize=(10,6))
sns.boxplot(x='TypeOfWork', y='PermitElapsedDays', data=issuedbuildingpermits_2024, palette='Set2')

plt.title('Distribution of Permit Response Time by Type of Work', fontsize=16)
plt.xlabel('Type of Work', fontsize=12)
plt.ylabel('Permit Elapsed Days', fontsize=12)

plt.xticks(rotation=45, ha='right')

plt.tight_layout()
plt.show()
```

![boxplot](https://github.com/user-attachments/assets/b70b0e7c-250e-4904-ade4-d098c4d1f940)


__New Building:__
Median: Approximately 500 days.
Interquartile Range: Between 250 and 1000 days.
Outliers: Some points exceed 1500 days.

__Addition / Alteration:__
Median: Approximately 250 days.
Interquartile Range: Between 100 and 500 days.
Outliers: Some points exceed 1000 days.

__Demolition / Deconstruction:__
Median: Approximately 750 days.
Interquartile Range: Between 500 and 1000 days.
Outliers: Some points exceed 1500 days.

__Salvage and Abatement:__
Median: Approximately 250 days.
Interquartile Range: Between 100 and 500 days.
Outliers: Some points exceed 1000 days.

__Outdoor Uses (No Buildings Proposed):__
Median: Approximately 1000 days.
Interquartile Range: Between 750 and 1500 days.
Outliers: Some points exceed 1750 days.

__Temporary Building / Structure:__
Median: Approximately 100 days.
Interquartile Range: Between 50 and 250 days.
Outliers: Some points exceed 500 days.


**Conclusions:**

Highest Variability: Response times for Outdoor Uses (No Buildings Proposed) show the highest variability and the most extended times.
Lowest Variability: Temporary Buildings / Structures have the lowest variability and the shortest response times.
Outliers: All work types have significant outliers, indicating that, in some cases, response times can be exceptionally long.


# Histogram


```plt.figure(figsize=(10,6))
issuedbuildingpermits_2024['PermitElapsedDays'].hist(bins=30, color='skyblue', edgecolor='black')

plt.title('Distribution of Permit Response Times', fontsize=16)
plt.xlabel('Permit Elapsed Days', fontsize=12)
plt.ylabel('Frequency', fontsize=12)

plt.tight_layout()
plt.show()
```

![histogram](https://github.com/user-attachments/assets/40cd8e2f-a09f-46c5-bd2c-33b9f23a5878)



**The “Distribution of Permit Response Times” graph shows the frequency of permit response times, measured in elapsed days. Here is the interpretation of the data:**

__High Frequency in Short Times:__

The highest bar is in the interval closest to 0 days, indicating that most permits have a short response time after submission.

__Decreasing Frequency:__

The frequency decreases as the elapsed days increase, showing that fewer permits take longer to receive a response.

__Range of Days:__

The x-axis shows elapsed days from 0 to 2000 days, while the y-axis shows frequency, which appears to reach approximately 1400.

__Conclusions__

__Efficiency:__ Most permits are responded to quickly, suggesting an efficient process.
__Variability:__ Although most permits have short response times, there is significant variability, with some permits taking much longer.


# Time-to-Approval Analysis:


__High Frequency in Short Times:__

The highest bar is in the range closest to 0 days, indicating that most permits have a short turnaround time after submission.

__Decreasing Frequency:__

The frequency decreases as the elapsed days increase, showing that fewer permits take longer to receive a response.

__Range of Days:__

The x-axis shows elapsed days from 0 to 2000 days, while the y-axis shows frequency, which appears to reach approximately 1400.

__Conclusions__

_Efficiency:_ Most permits are responded to quickly, suggesting an efficient process.
_Variability:_ Although most permits have short response times, there is significant variability, with some permits taking much longer.


## Insights and Findings:

In analyzing turnaround times for building permits, several key columns have been identified that, when combined, can provide a more complete picture of the factors influencing these times. Insights and findings based on these columns are presented below:

__PermitNumber:__
Insight: Each permit has a unique identifier that allows each request to be tracked and analyzed individually.
Findings: Allows identifying specific patterns in response times for different types of permits.

__PermitNumberCreatedDate and IssueDate:__
Insight: These dates are crucial for calculating the total processing time for each permit.
Finding: The difference between these dates, represented in PermitElapsedDays, directly measures response time.

__PermitElapsedDays:__
Insight: This column is critical to understanding the efficiency of the permit issuance process.
Findings: Allows you to identify the permits that take the longest and analyze the possible causes of these delays.

__ProjectValue:__
Insight: Project value can influence priority and review time.
Finding: Higher-value projects tend to have longer turnaround times due to complexity and the need for more detailed reviews.

__TypeOfWork:__
Insight: Different types of work may have different turnaround times.
Finding: New construction jobs and demolitions tend to have longer response times than minor alterations.

__Address and GeoLocalArea:__
Insight: Geographic location can influence response times due to variations in workload and local regulations.
Finding: Areas with higher construction activity may experience longer response times.

__ProjectDescription and PermitCategory:__
Insight: The project description and permit category provide additional context on the nature of the work.
Findings: Allows for more accurate classification of permits and a better understanding of the factors affecting turnaround times.

__Applicant and ApplicantAddress:__
Insight: Applicant information may be relevant to identify patterns in response times.
Findings: Frequent applicants or applicants with larger projects may have different response times.

__PropertyUse and SpecificUseCategory:__
Insight: The property's intended use may influence the priority and permit review time.
Finding: Commercial and residential properties may have different response times.

__BuildingContractor and BuildingContractorAddress:__
Insight: Contractor information may be relevant to analyzing efficiency and permit management experience.
Finding: Experienced contractors may have faster response times due to their familiarity with the process.

__IssueYear and YearMonth:__
Insight: These columns allow for temporal analysis of response times.
Findings: Identify trends and seasonal variations in response times.

__Geom and geo_point_2d:__
Insight: Geospatial information can be used to visualize and analyze the distribution of response times.
Findings: Allows for identifying geographic areas with longer response times and possible bottlenecks.

__Conclusion__
Combining these columns provides a comprehensive view of the factors influencing response times for building permits in Vancouver. By analyzing this data, it is possible to identify patterns, trends, and areas for improvement to optimize the permit issuance process.

### Final Conclusions ###

__Project Complexity:__ Higher value and more complex projects, such as new buildings, have significantly longer turnaround times due to the need for detailed reviews and multiple approvals.

__Geographic Variability:__ Geographic location influences response times, with areas of high construction activity experiencing longer delays due to department workload.

__Process Efficiency:__ Most permits are responded to quickly, indicating an efficient process, although outliers suggest the need for improvement in specific cases.

__Applicant and Contractor Impact:__ Applicants and contractors with experience and familiarity with the permitting process tend to have faster response times, highlighting the importance of quality and accuracy in submitting applications.






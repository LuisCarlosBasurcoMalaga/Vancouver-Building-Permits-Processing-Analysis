# Vancouver-Building-Permits-Processing-Analysis

## Exploratory Data Analysis

**Understand the structure and quality of the data:** Identify and correct potential problems in the data, such as missing values, duplicates or inconsistencies. This ensures that the data are reliable for further analysis.

**Initial pattern detection:** Analyze the distribution of critical variables such as “permitLapsedDays” to understand how response times vary by permit type and other characteristics (such as job type or geographic area).

**Visualizing trends:** Identify trends over time (e.g., have response times increased in recent years?) using graphs to help visualize changes in wait days.

**Identifying relationships:** Examine possible relationships between variables, such as whether certain types of jobs or specific permits tend to take longer to be approved.

**Establish hypotheses:** From the patterns and relationships observed, formulate hypotheses about factors influencing delay times.


PermitNumber: A unique identification number assigned to each permit issued.
PermitNumberCreatedDate: The date on which the permit number was created.
IssueDate: The date the permit was officially issued.
PermitElapsedDays: Number of days that elapsed between the application and permit issuance.
ProjectValue: Estimated monetary value of the project related to the permit.
TypeOfWork: Type of work to be performed (e.g., construction, demolition, modification).
Address: Address of the location where the project will be performed.
ProjectDescription: Brief description of the project for which the permit is being requested.
PermitCategory: Permit category according to the type of project.
Applicant: Name of the applicant who managed the permit.
ApplicantAddress: Applicant's address.
PropertyUse: Intended use of the property (residential, commercial, etc.).
SpecificUseCategory: Specific property use category (more detailed than PropertyUse).
Building Contractor: Name of the contractor performing the work.
BuildingContractorAddress: Contractor's address.
IssueYear: The year in which the permit was issued.
GeoLocalArea: Local geographic area associated with the project.
Geom: Geospatial geometry of the project site.
YearMonth: Year and month in which the permit was issued.
geo_point_2d: Geographic coordinates (latitude and longitude) of the project site.



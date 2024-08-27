# Solving an SDG Problem with Data (Choose Your SDG)

## Overview
Select a Sustainable Development Goal (SDG) that resonates with you and develop a data-driven solution to address a specific problem within that SDG. Design a database, perform data analysis, and use Microsoft Excel as the user interface.

## Objectives
- Choose an SDG and identify a specific problem to address.
- Design and implement a relational database relevant to your chosen problem.
- Write SQL queries to retrieve and analyze data.
- Use Microsoft Excel for data visualization and analysis.

## Requirements

### Part 1: SDG Selection and Problem Definition
- **SDG Selection:** Choose an SDG (e.g., SDG 3: Good Health, SDG 7: Affordable and Clean Energy).
- **Problem Definition:** Define a specific problem within your chosen SDG that can be addressed using data.

### Part 2: Database Design
- **ERD:** Design an ERD for your project, including entities relevant to your SDG problem.
- **Schema:** Write SQL statements to create the database schema based on your ERD.
- **Sample Data:** Populate the database with relevant sample data.

### Part 3: SQL Programming
- **Data Retrieval:** Write SQL queries to retrieve relevant data based on your problem definition.
- **Data Analysis:** Write SQL queries to analyze data and generate insights related to your SDG problem.

### Part 4: Data Analysis Using Excel
- **Import Data:** Import data from your database into Excel.
- **Analysis:** Analyze the data using pivot tables, charts, and other Excel tools.
- **Dashboard:** Create an interactive Excel dashboard to visualize key insights.

### Part 5: Integration and Testing
- **Integration:** Document the process of importing data into Excel and ensuring consistency.
- **Testing:** Test the integration and functionality of your Excel dashboard.

### Part 6: Presentation
- **Pitch Deck:** Develop a 10-slide PowerPoint presentation as taught in the entrepreneurship module covering:
  - Project overview and SDG alignment.
  - Problem definition and significance.
  - Database design and schema.
 
To help you complete your Week 8 assignment on solving a Sustainable Development Goal (SDG) problem with data, I will guide you through each part of the assignment step by step. I will provide you with a structured approach, including examples and templates that you can adapt to your needs.

### Week 8 Assignment: Solving an SDG Problem with Data

#### Part 1: SDG Selection and Problem Definition

**1. SDG Selection:**
I choose **SDG 3: Good Health and Well-being**.

**2. Problem Definition:**
The specific problem I want to address is the **high incidence of preventable diseases** in low-income communities due to lack of access to healthcare services and health education. This problem can be addressed through data analysis of healthcare access and disease prevalence.

---

#### Part 2: Database Design

**1. ERD (Entity-Relationship Diagram):**
Here’s a simple ERD for the project:

- **Entities:**
  - **Patients** (PatientID, Name, Age, Gender, IncomeLevel)
  - **Diseases** (DiseaseID, DiseaseName, PreventionMethods)
  - **HealthcareAccess** (AccessID, PatientID, FacilityName, DistanceToFacility)
  - **HealthEducation** (EducationID, PatientID, TopicsCovered, DateAttended)

You can create this ERD using tools like Lucidchart or draw.io.

**2. Schema:**
Here are the SQL statements to create the database schema based on the ERD:

```sql
CREATE TABLE Patients (
    PatientID INT PRIMARY KEY,
    Name VARCHAR(100),
    Age INT,
    Gender VARCHAR(10),
    IncomeLevel VARCHAR(50)
);

CREATE TABLE Diseases (
    DiseaseID INT PRIMARY KEY,
    DiseaseName VARCHAR(100),
    PreventionMethods TEXT
);

CREATE TABLE HealthcareAccess (
    AccessID INT PRIMARY KEY,
    PatientID INT,
    FacilityName VARCHAR(100),
    DistanceToFacility DECIMAL(5,2),
    FOREIGN KEY (PatientID) REFERENCES Patients(PatientID)
);

CREATE TABLE HealthEducation (
    EducationID INT PRIMARY KEY,
    PatientID INT,
    TopicsCovered TEXT,
    DateAttended DATE,
    FOREIGN KEY (PatientID) REFERENCES Patients(PatientID)
);
```

**3. Sample Data:**
You can populate the database with relevant sample data. Here’s an example:

```sql
INSERT INTO Patients (PatientID, Name, Age, Gender, IncomeLevel) VALUES
(1, 'John Doe', 30, 'Male', 'Low'),
(2, 'Jane Smith', 25, 'Female', 'Low'),
(3, 'Emily Johnson', 40, 'Female', 'Medium');

INSERT INTO Diseases (DiseaseID, DiseaseName, PreventionMethods) VALUES
(1, 'Diabetes', 'Regular check-ups, Healthy diet'),
(2, 'Hypertension', 'Regular exercise, Low salt diet');

INSERT INTO HealthcareAccess (AccessID, PatientID, FacilityName, DistanceToFacility) VALUES
(1, 1, 'Community Health Center', 1.5),
(2, 2, 'Local Clinic', 3.0);

INSERT INTO HealthEducation (EducationID, PatientID, TopicsCovered, DateAttended) VALUES
(1, 1, 'Diabetes Management', '2024-01-15'),
(2, 2, 'Healthy Eating', '2024-01-20');
```

---

#### Part 3: SQL Programming

**1. Data Retrieval:**
Here are some SQL queries to retrieve relevant data:

- Retrieve all patients and their healthcare access:
```sql
SELECT Patients.Name, HealthcareAccess.FacilityName, HealthcareAccess.DistanceToFacility
FROM Patients
JOIN HealthcareAccess ON Patients.PatientID = HealthcareAccess.PatientID;
```

- Find patients with a specific disease:
```sql
SELECT Patients.Name, Diseases.DiseaseName
FROM Patients
JOIN HealthEducation ON Patients.PatientID = HealthEducation.PatientID
JOIN Diseases ON Diseases.DiseaseID = 1; -- Example for Diabetes
```

**2. Data Analysis:**
Here are some SQL queries to analyze data:

- Count of patients by income level:
```sql
SELECT IncomeLevel, COUNT(*) AS PatientCount
FROM Patients
GROUP BY IncomeLevel;
```

- Average distance to healthcare facilities:
```sql
SELECT AVG(DistanceToFacility) AS AverageDistance
FROM HealthcareAccess;
```

---

#### Part 4: Data Analysis Using Excel

**1. Import Data:**
You can import data from your database into Excel using the `Data` tab and selecting `Get Data` > `From Database`.

**2. Analysis:**
- Use **Pivot Tables** to summarize patient counts by income level.
- Create **charts** to visualize the average distance to healthcare facilities.

**3. Dashboard:**
Create an interactive dashboard in Excel that includes:
- Key metrics (e.g., total patients, average distance).
- Charts showing the distribution of diseases and healthcare access.

---

#### Part 5: Integration and Testing

**1. Integration:**
Document the process of importing data into Excel, including any steps taken to ensure data consistency (e.g., formatting, data types).

**2. Testing:**
Test the Excel dashboard by checking that all data updates correctly and that the visualizations reflect the underlying data accurately.

---

#### Part 6: Presentation

**1. Pitch Deck:**
Develop a 10-slide PowerPoint presentation covering:
- **Slide 1:** Title Slide
- **Slide 2:** Project Overview and SDG Alignment
- **Slide 3:** Problem Definition and Significance
- **Slide 4:** Database Design and Schema
- **Slide 5:** Sample Data Overview
- **Slide 6:** SQL Queries for Data Retrieval
- **Slide 7:** SQL Queries for Data Analysis
- **Slide 8:** Excel Dashboard Overview
- **Slide 9:** Key Insights from Data Analysis
- **Slide 10:** Conclusion and Next Steps

You can create the presentation using PowerPoint, Google Slides, or Canva.

---

### Deliverables for Submission
1. **SDG Problem Definition Document**: A document outlining the chosen SDG and the specific problem addressed.
2. **ERD**: A visual representation of the Entity-Relationship Diagram.
3. **SQL Scripts**: A file containing all SQL statements used for creating the schema and queries.
4. **Excel Workbook**: An Excel file containing the imported data, analysis, and dashboard.
5. **Integration Documentation**: A document detailing the integration process between the database and Excel.
6. **Pitch Deck Presentation**: A link to the PowerPoint presentation or a PDF version.

  - Data analysis insights.
  - Excel dashboard demonstration.
- **Delivery:** Present your pitch deck, demonstrating how your project addresses the SDG problem.

## Deliverables (upload onto this repo)
- SDG problem definition document
- ERD
- SQL scripts
- Excel workbook with data analysis and dashboard
- Integration documentation
- Pitch deck presentation (Provide the link e.g Canva or Gamma in your documentation)


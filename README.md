**Assignment Overview**
This project demonstrates practical implementation of SQL JOINs and Window Functions using a veterinary clinic scenario in Rwanda. The assignment showcases database development skills for business analytics.

 **Business Scenario: Kigali Pet Care Veterinary Clinic**
*Business Context*
Clinic Name: Kigali Pet Care Veterinary Clinic
Location: Kigali, Rwanda
Industry: Animal Healthcare Services
Scope: Domestic pets and livestock common in Rwanda

**Data Challenge**
*The clinic needs to analyze treatment patterns across different districts of Kigali to:*

1.Identify most popular services by area
2.Track revenue growth over time
3.Understand customer visit frequency
4.Optimize resource allocation

**Expected Outcomes**
1.Identify top 3 treatments per district for targeted service improvement
2.Analyze monthly revenue trends for financial planning
3.Segment customers for loyalty program development
4.Improve clinic scheduling based on demand patterns

 **Database Schema**
ER Diagram
text
      PET_OWNERS                    ANIMALS                     VISITS
    +-------------+               +-------------+             +-------------+
    | owner_id PK |◄------------+ | owner_id FK |             | visit_id PK |
    | owner_name  |               | animal_id PK|◄----------+ | animal_id FK|
    | district    |               | animal_name |             | visit_date  |
    | phone_number|               | animal_type |             | treatment   |
    +-------------+               | breed       |             | cost        |
                                  +-------------+             +-------------+
Tables Description
1. pet_owners Table
Stores information about pet owners in Kigali.

owner_id (INT, PRIMARY KEY): Unique identifier

owner_name (VARCHAR): Owner's full name

district (VARCHAR): Kigali district (Gasabo, Kicukiro, Nyarugenge)

phone_number (VARCHAR): Contact information

2. animals Table
Contains details of registered animals.

animal_id (INT, PRIMARY KEY): Unique identifier

owner_id (INT, FOREIGN KEY): References pet_owners

animal_name (VARCHAR): Animal's name

animal_type (VARCHAR): Dog, Cat, Cow, Goat

breed (VARCHAR): Animal breed

3. visits Table
Records all veterinary visits and treatments.

visit_id (INT, PRIMARY KEY): Unique identifier

animal_id (INT, FOREIGN KEY): References animals

visit_date (DATE): Date of visit

treatment_type (VARCHAR): Type of treatment

cost (DECIMAL): Cost in Rwandan Francs (RWF)

 Implementation Details
Success Criteria (5 Measurable Goals)
Top 3 treatments per district → RANK()

Running monthly revenue totals → SUM() OVER()

Month-over-month growth percentage → LAG()

Customer quartile segmentation → NTILE(4)

Three-month moving average revenue → AVG() OVER()

Part A: SQL JOINs Implementation
1. INNER JOIN
Retrieves complete visit records with owner and animal details for operational reporting.

2. LEFT JOIN
Identifies registered pet owners who haven't brought animals yet, useful for marketing campaigns.

3. RIGHT JOIN
Finds animals with no visit history to schedule preventive care reminders.

4. FULL OUTER JOIN
Provides complete data audit showing all relationships and gaps.

5. SELF JOIN
Compares pet owners within same districts for community-based promotions.

Part B: Window Functions Implementation
Category 1: Ranking Functions
Functions used: RANK(), ROW_NUMBER(), DENSE_RANK()

Use case: Identifying top treatments per district

Business value: Service optimization by area

Category 2: Aggregate Window Functions
Functions used: SUM(), AVG(), MIN(), MAX()

Use case: Revenue trends and running totals

Business value: Financial tracking and performance analysis

Category 3: Navigation Functions
Functions used: LAG(), LEAD()

Use case: Month-over-month growth analysis

Business value: Trend identification and forecasting

Category 4: Distribution Functions
Functions used: NTILE(4), CUME_DIST()

Use case: Customer segmentation

Business value: Targeted marketing and loyalty programs

**Analysis Results**
Descriptive Analysis (What happened?)
Total Revenue: 26,000 RWF from 5 visits

Most Active District: Gasabo (60% of visits)

Most Common Treatment: Vaccination (40% of visits)

Average Treatment Cost: 5,200 RWF

Customer Distribution: 4 owners across 3 districts

Diagnostic Analysis (Why did it happen?)
District Performance: Gasabo's higher population density explains its dominance

Service Popularity: Vaccination frequency reflects strong preventive care awareness

Revenue Patterns: Single high-value treatment (10,000 RWF) influenced averages

Timing Factors: Visit clustering suggests salary cycle influence

Prescriptive Analysis (What should be done next?)
Resource Allocation: Increase staff in Gasabo during peak periods

Marketing Focus: Target Kicukiro with vaccination promotion packages

Service Expansion: Consider mobile clinic services for Nyarugenge

Customer Retention: Implement loyalty program for frequent visitors

Preventive Care: Develop SMS reminder system for vaccinations

📁 Project Structure
text
plsql_window_functions_[studentID]_[firstName]/
│
├── README.md                          # This file
├── ER_Diagram.png                     # Visual database schema
│
├── schema/
│   ├── create_tables.sql              # Table creation scripts
│   └── insert_data.sql                # Sample data insertion
│
├── part_a_joins/                      # SQL JOIN implementations
│   ├── 01_inner_join.sql
│   ├── 02_left_join.sql
│   ├── 03_right_join.sql
│   ├── 04_full_outer_join.sql
│   └── 05_self_join.sql
│
├── part_b_window_functions/           # Window function implementations
│   ├── 01_ranking_functions.sql
│   ├── 02_aggregate_functions.sql
│   ├── 03_navigation_functions.sql
│   └── 04_distribution_functions.sql
│
├── screenshots/                       # Query result screenshots
│   ├── join_results/
│   └── window_functions/
│
└── analysis/                          # Analytical documentation
    ├── descriptive_analysis.txt
    ├── diagnostic_analysis.txt
    └── prescriptive_analysis.txt
🛠️ Technical Specifications
Database Management System
DBMS: Oracle Database

Tool Used: Oracle SQL Developer

SQL Version: Oracle SQL

Key Features Implemented
✅ All 5 required JOIN types

✅ All 4 categories of window functions

✅ 3 related tables with proper relationships

✅ Complete business scenario with Rwanda context

✅ Error-free SQL scripts

✅ Professional documentation

📚 References
Oracle Corporation. Oracle Database SQL Language Reference. Oracle Help Center.

Oracle Corporation. Oracle Database Data Warehousing Guide. Oracle Help Center.

Course materials from INSY 8311: Database Development with PL/SQL

Online SQL tutorials and documentation

Rwanda-specific context from local veterinary practices

🔏 Academic Integrity Statement
"All sources were properly cited. Implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation."

I confirm that:

All SQL queries were written and tested independently

All analysis represents original thinking and interpretation

Proper citations are provided for referenced materials

The work complies with AUC-A academic integrity policies

Student Signature: __________________________
Date: __________________________

📬 Submission Details
Repository URL: [INSERT YOUR GITHUB LINK HERE]

Last Commit Hash: [INSERT COMMIT HASH]

Submission Time: [INSERT DATE AND TIME]

Email Submission Sent To: eric.maniraguha@auca.ac.rw
Subject: INSY 8311 SQL Assignment I – [Your Name] – Group [Your Group]

✅ Verification Checklist
Technical Requirements
All 5 JOIN types implemented correctly

All 4 window function categories demonstrated

Minimum 3 related tables with PK/FK relationships

ER diagram included

SQL scripts execute without errors

Documentation Requirements
Professional README file

Clear business problem definition

5 measurable success criteria

Three-level analysis (descriptive, diagnostic, prescriptive)

Screenshots of query results

Proper references and citations

Submission Requirements
GitHub repository is public

Repository follows naming convention

Email prepared for submission

All files properly organized

Integrity statement included

🙏 Acknowledgments
I would like to express gratitude to:

Instructor Eric Maniraguha for guidance and support

African University College of Africa (AUCA) for the learning platform

Colleagues and classmates for collaborative learning

The open-source community for valuable resources

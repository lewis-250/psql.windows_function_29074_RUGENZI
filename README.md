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
[screenshots pl/ERDiagram.png](URL "erdiagram")

Tables Description
1. pet_owners Table
Stores information about pet owners in Kigali.

.owner_id (INT, PRIMARY KEY): Unique identifier
.owner_name (VARCHAR): Owner's full name
.district (VARCHAR): Kigali district (Gasabo, Kicukiro, Nyarugenge)
.phone_number (VARCHAR): Contact information

2. animals Table
Contains details of registered animals.

.animal_id (INT, PRIMARY KEY): Unique identifier
.owner_id (INT, FOREIGN KEY): References pet_owners
.animal_name (VARCHAR): Animal's name
.animal_type (VARCHAR): Dog, Cat, Cow, Goat
.breed (VARCHAR): Animal breed

3. visits Table
Records all veterinary visits and treatments.

.visit_id (INT, PRIMARY KEY): Unique identifier
.animal_id (INT, FOREIGN KEY): References animals
.visit_date (DATE): Date of visit
.treatment_type (VARCHAR): Type of treatment
.cost (DECIMAL): Cost in Rwandan Francs (RWF)

 **Implementation Details**
*Success Criteria (5 Measurable Goals)*
1.Top 3 treatments per district → RANK()
2.Running monthly revenue totals → SUM() OVER()
3.Month-over-month growth percentage → LAG()
4.Customer quartile segmentation → NTILE(4)
5.Three-month moving average revenue → AVG() OVER()

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

**Part B: Window Functions Implementation**
**Category 1: Ranking Functions**
.Functions used: RANK(), ROW_NUMBER(), DENSE_RANK()
.Use case: Identifying top treatments per district
.Business value: Service optimization by area

**Category 2: Aggregate Window Functions**
.Functions used: SUM(), AVG(), MIN(), MAX()
.Use case: Revenue trends and running totals
.Business value: Financial tracking and performance analysis

**Category 3: Navigation Functions**
.Functions used: LAG(), LEAD()
.Use case: Month-over-month growth analysis
.Business value: Trend identification and forecasting

**Category 4: Distribution Functions**
.Functions used: NTILE(), CUME_DIST()
.Use case: Customer segmentation
.Business value: Targeted marketing and loyalty programs

**Analysis Results**
*Descriptive Analysis (What happened?)*
.Total Revenue: 26,000 RWF from 5 visits
.Most Active District: Gasabo (60% of visits)
.Most Common Treatment: Vaccination (40% of visits)
.Average Treatment Cost: 5,200 RWF
.Customer Distribution: 4 owners across 3 districts

**Diagnostic Analysis (Why did it happen?)**
1.District Performance: Gasabo's higher population density explains its dominance
2.Service Popularity: Vaccination frequency reflects strong preventive care awareness
3.Revenue Patterns: Single high-value treatment (10,000 RWF) influenced averages
4.Timing Factors: Visit clustering suggests salary cycle influence

**Prescriptive Analysis (What should be done next?)**
1.Resource Allocation: Increase staff in Gasabo during peak periods
2.Marketing Focus: Target Kicukiro with vaccination promotion packages
3.Service Expansion: Consider mobile clinic services for Nyarugenge
4.Customer Retention: Implement loyalty program for frequent visitors
5.Preventive Care: Develop SMS reminder system for vaccinations

**Technical Specifications**
*Database Management System*
.DBMS: Oracle Database
.Tool Used: Oracle SQL Developer
.SQL Version: Oracle SQL

**Key Features Implemented**
1. All 5 required JOIN types
2. All 4 categories of window functions
3. 3 related tables with proper relationships
4. Complete business scenario with Rwanda context
5. Error-free SQL scripts
6. Professional documentation

 **References**
1.Oracle Corporation. Oracle Database SQL Language Reference. Oracle Help Center.
2.Oracle Corporation. Oracle Database Data Warehousing Guide. Oracle Help Center.
3.Course materials from INSY 8311: Database Development with PL/SQL
4.Online SQL tutorials and documentation
5.Rwanda-specific context from local veterinary practices

 **Academic Integrity Statement**
"All sources were properly cited. Implementations and analysis represent original work. No AI-generated content was copied without attribution or adaptation."

I confirm that:

All SQL queries were written and tested independently

All analysis represents original thinking and interpretation

Proper citations are provided for referenced materials

The work complies with AUC-A academic integrity policies

Student Signature: __________________________
Date: __________________________


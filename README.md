# .NetCourse_Day13
# Comprehensive Entity-Relationship Model SRS Documentation

## Problem_1 : Musicana Recording Label System

### Overview
The Musicana Recording Label System manages musicians, instruments, albums, and songs recorded at Musicana. It tracks relationships between musicians, their instruments, the songs they perform, and the albums they produce.

### Entities and Attributes
- **Musician**
  - `Musician_ID` (PK)
  - `Name`
  - `Address` (Street, City)
  - `Phone_Number`
  
- **Instrument**
  - `Instrument_Name` (PK)
  - `Musical_Key`
  
- **Album**
  - `Album_Title` (PK)
  - `Copyright_Date`
  - `Album_ID`
  
- **Song**
  - `Song_Title` (PK)
  - `Author`

### Relationships
- **Musician-Instrument:** Many-to-Many
- **Album-Song:** One-to-Many
- **Musician-Song:** Many-to-Many
- **Album-Producer:** One-to-Many

### Key Features
- Track musicians' details and their instruments.
- Record songs and associate them with musicians and albums.
- Manage album production details and copyright information.

---

## Problem_2 : Real Estate Firm System

### Overview
This system manages sales offices, employees, properties, and owners. It records property ownership and assignments of employees and managers to sales offices.

### Entities and Attributes
- **Sales Office**
  - `Office_Number` (PK)
  - `Location`
  
- **Employee**
  - `Employee_ID` (PK)
  - `Employee_Name`
  - `Office_Number` (FK)
  
- **Property**
  - `Property_ID` (PK)
  - `Location` (Address, City, State, Zip_Code)
  - `Office_Number` (FK)
  
- **Owner**
  - `Owner_ID` (PK)
  - `Owner_Name`

### Relationships
- **Sales Office-Employee:** One-to-Many
- **Sales Office-Manager:** One-to-One
- **Property-Sales Office:** One-to-Many
- **Property-Owner:** Many-to-Many (with `Percent_Owned`)

### Key Features
- Manage sales office and employee assignments.
- Track property listings and their ownership percentages.
- Associate each sales office with a manager.

---

## Problem_3 : General Hospital Management System

### Overview
The General Hospital Management System handles ward details, patients, consultants, nurses, and drug administration. It captures all key data related to patient care and staff management.

### Entities and Attributes
- **Ward**
  - `Ward_ID` (PK)
  - `Name`
  
- **Patient**
  - `Patient_ID` (PK)
  - `Name`
  - `Date_Of_Birth`
  - `Ward_ID` (FK)
  - `Leading_Consultant_ID` (FK)
  
- **Consultant**
  - `Consultant_ID` (PK)
  - `Name`
  
- **Nurse**
  - `Nurse_Number` (PK)
  - `Name`
  - `Address`
  - `Ward_ID` (FK)
  
- **Drug**
  - `Drug_Code` (PK)
  - `Recommended_Dosage`
  - `Brand_Name`
  
- **Administration_Record**
  - `Record_ID` (PK)
  - `Patient_ID` (FK)
  - `Nurse_Number` (FK)
  - `Drug_Code` (FK)
  - `Dosage`
  - `Date`
  - `Time`

### Relationships
- **Ward-Patient:** One-to-Many
- **Ward-Nurse:** One-to-One
- **Patient-Consultant:** One-to-Many (Leading), Many-to-Many (Examinations)
- **Patient-Drug Administration:** One-to-Many
- **Drug-Nurse-Patient:** Many-to-Many (via `Administration_Record`)

### Key Features
- Manage ward assignments and supervision.
- Record patient details, consultations, and drug administration.
- Maintain detailed logs of drug dosages and administration times.

---

## Case_Study : Education System

### Overview
The Education System manages students, departments, courses, and instructors. It records the grades of students in various courses and tracks department management.

### Entities and Attributes
- **Student**
  - `St_ID` (PK)
  - `Fname`
  - `Lname`
  - `St_Age`
  - `St_Address`
  
- **Department**
  - `Dept_ID` (PK)
  - `Dep_Name`
  
- **Course**
  - `Crs_ID` (PK)
  - `Crs_Name`
  - `Crs_Duration`
  - `Crs_Description`
  
- **Instructor**
  - `Ins_ID` (PK)
  - `Ins_Name`
  - `Ins_Salary`
  - `Ins_HourRate`
  - `Ins_Bonus`
  - `Ins_Address`
  
- **Topic**
  - `Top_ID` (PK)
  - `Top_Name`

### Relationships
- **Student-Course:** Many-to-Many (with `Grade`)
- **Department-Instructor:** One-to-Many (with one manager per department)
- **Instructor-Course:** Many-to-Many (with evaluation)
- **Topic-Course:** One-to-Many

### Key Features
- Manage student enrollments and grades.
- Track department assignments and instructors.
- Organize courses under topics and associate instructors with evaluations.

---

# V02 — Student Locality & Geographic Classification

> **Student Geographic Classification Module for Accreditation & Outreach Analysis**

## 📌 Project Overview

Institutions need to understand the geographic distribution of their students for **accreditation, institutional planning, outreach analysis, and reporting**.

This project develops a **Student Locality & Geographic Classification Module** that uses a student's address/origin information to automatically classify them into one of five geographic categories:

* 🏠 **Local**
* 📍 **District**
* 🗺️ **Within State**
* 🚩 **Other State**
* 🌍 **International**

The system provides a complete workflow to **Create → View → Search/Filter → Update → Report/Insight** and includes a distribution dashboard for analyzing the geographic spread of the student population.

---

## 🎯 MVP Objective

Build a student geographic classification module that:

1. Captures student address and geographic information.
2. Identifies the student's district, state, and country.
3. Determines the appropriate locality category.
4. Displays the classification when viewing a student.
5. Provides search and filtering functionality.
6. Displays a distribution dashboard.
7. Ensures dashboard totals match the underlying student records.

---

## 🏫 Business / Accreditation Requirement

Institutions must report the geographic spread of their student body across:

| Category          | Description                                                           |
| ----------------- | --------------------------------------------------------------------- |
| **Local**         | Student belongs to the same locality as the institution               |
| **District**      | Student belongs to another locality within the institution's district |
| **Within State**  | Student belongs to another district within the same state             |
| **Other State**   | Student belongs to a different state within the country               |
| **International** | Student belongs to another country                                    |

This information can support:

* Accreditation reporting
* Student diversity analysis
* Outreach planning
* Admission analysis
* Institutional strategic planning
* Geographic distribution reports

---

# 🔄 System Flow

```text
┌───────────────┐
│    Student    │
└───────┬───────┘
        │
        ▼
┌───────────────────────┐
│ Address / Origin Data │
│                       │
│ • Address             │
│ • District            │
│ • State               │
│ • Country             │
└───────────┬───────────┘
            │
            ▼
┌─────────────────────────┐
│ Locality Classification │
│                         │
│ Compare student origin  │
│ with institution       │
│ location                │
└────────────┬────────────┘
             │
             ▼
     ┌─────────────────┐
     │ Classification  │
     └────────┬────────┘
              │
      ┌───────┼────────┬────────────┐
      ▼       ▼        ▼            ▼
   Local   District  State     Other State
                                  │
                                  ▼
                             International
              │
              ▼
┌────────────────────────────┐
│   Distribution Dashboard   │
│                            │
│ • Category Counts          │
│ • Percentages              │
│ • Filters                  │
│ • Geographic Insights      │
└────────────────────────────┘
```

---

# 🖥️ UI Flow

```text
┌─────────────────┐
│ Student Module  │
└────────┬────────┘
         │
         ▼
┌────────────────────────┐
│ Student List           │
│                        │
│ Search | Filter | Add  │
└────────┬───────────────┘
         │
         ▼
┌────────────────────────┐
│ Student Details        │
│                        │
│ Name                   │
│ Address                │
│ District               │
│ State                  │
│ Country                │
│ Locality Category      │
└────────┬───────────────┘
         │
         ▼
┌────────────────────────┐
│ Classification Engine  │
│                        │
│ Institution Location   │
│          +             │
│ Student Origin         │
└────────┬───────────────┘
         │
         ▼
┌────────────────────────┐
│ Classification Result  │
│                        │
│ Local                  │
│ District               │
│ Within State           │
│ Other State            │
│ International          │
└────────┬───────────────┘
         │
         ▼
┌────────────────────────────┐
│ Distribution Dashboard     │
│                            │
│ Total Students             │
│ Local Students             │
│ District Students          │
│ Within State Students      │
│ Other State Students       │
│ International Students     │
└────────────────────────────┘
```

---

# 🗃️ Data Captured

Each student record contains geographic information required for classification.

### Student

| Field             | Description                          |
| ----------------- | ------------------------------------ |
| Student ID        | Unique student identifier            |
| Student Name      | Student's full name                  |
| Address           | Student's residential/home address   |
| District          | Student's district                   |
| State             | Student's state                      |
| Country           | Student's country                    |
| Locality Category | Calculated geographic classification |

### Institution Location

The institution's reference location is required for comparison.

| Field            | Description          |
| ---------------- | -------------------- |
| Institution Name | Name of institution  |
| District         | Institution district |
| State            | Institution state    |
| Country          | Institution country  |

---

# 🧠 Locality Classification Logic

The classification is determined by comparing the student's origin with the institution's reference location.

```text
IF Country != Institution Country
        ↓
   INTERNATIONAL

ELSE IF State != Institution State
        ↓
   OTHER STATE

ELSE IF District != Institution District
        ↓
   WITHIN STATE

ELSE IF Locality != Institution Locality
        ↓
   DISTRICT

ELSE
        ↓
   LOCAL
```

> **Note:** The exact locality definition can be configured according to the institution's geographic boundaries and accreditation requirements.

---

# 🏗️ ER Design Decision

## Should Locality Category Be Stored or Calculated?

### Decision: Calculate the locality category from geographic data

The **locality category should not be treated as an independent master record that users manually enter**.

Instead, it should be derived from:

* Student address/origin
* Student district
* Student state
* Student country
* Institution locality
* Institution district
* Institution state
* Institution country

### Why?

Storing the category manually creates a risk of inconsistent or outdated information.

For example:

```text
Student:
District = Udupi
State = Karnataka
Country = India

Institution:
District = Dakshina Kannada
State = Karnataka
Country = India
```

The system can determine:

```text
Same Country
        ↓
Same State
        ↓
Different District
        ↓
WITHIN STATE
```

If the student's address is updated, the classification can also be recalculated.

### Recommended Architecture

```text
Student Geographic Data
          │
          ▼
Classification Service
          │
          ▼
Locality Category
          │
          ├── Student Details
          │
          └── Dashboard / Reports
```

This prevents users from manually entering potentially incorrect classifications.

---

# 🗄️ Database Schema

## Core Entities

```text
Institution
    │
    ├──────── Department
    │              │
    │              ▼
    │           Program
    │              │
    │              ▼
    │        Academic Year
    │              │
    │              ▼
    │           Semester
    │              │
    │              ▼
    └────────── Student
```

## Student Entity

```text
Student
--------------------------------
student_id       PK
name
address
locality
district
state
country
program_id       FK
semester_id      FK
```

## Institution Entity

```text
Institution
--------------------------------
institution_id   PK
name
locality
district
state
country
```

## Department Entity

```text
Department
--------------------------------
department_id    PK
institution_id   FK
name
```

## Program Entity

```text
Program
--------------------------------
program_id       PK
department_id    FK
name
```

## Academic Year Entity

```text
AcademicYear
--------------------------------
academic_year_id PK
year
```

## Semester Entity

```text
Semester
--------------------------------
semester_id      PK
academic_year_id FK
semester_number
```

---

# 🔗 Entity Relationship Diagram

```text
                    ┌────────────────────┐
                    │    Institution     │
                    ├────────────────────┤
                    │ institution_id PK  │
                    │ name               │
                    │ locality           │
                    │ district           │
                    │ state              │
                    │ country            │
                    └─────────┬──────────┘
                              │
                              │ 1:N
                              ▼
                    ┌────────────────────┐
                    │    Department      │
                    ├────────────────────┤
                    │ department_id PK   │
                    │ institution_id FK  │
                    │ name               │
                    └─────────┬──────────┘
                              │
                              │ 1:N
                              ▼
                    ┌────────────────────┐
                    │      Program       │
                    ├────────────────────┤
                    │ program_id PK      │
                    │ department_id FK   │
                    │ name               │
                    └─────────┬──────────┘
                              │
                              │ 1:N
                              ▼
                    ┌────────────────────┐
                    │   Academic Year    │
                    ├────────────────────┤
                    │ academic_year_id   │
                    │ year               │
                    └─────────┬──────────┘
                              │
                              │ 1:N
                              ▼
                    ┌────────────────────┐
                    │      Semester      │
                    ├────────────────────┤
                    │ semester_id PK     │
                    │ academic_year_id   │
                    │ semester_number    │
                    └─────────┬──────────┘
                              │
                              │ 1:N
                              ▼
                    ┌────────────────────┐
                    │      Student       │
                    ├────────────────────┤
                    │ student_id PK      │
                    │ name               │
                    │ address            │
                    │ locality           │
                    │ district           │
                    │ state              │
                    │ country            │
                    │ program_id FK      │
                    │ semester_id FK     │
                    └────────────────────┘
```

---

# 📊 Distribution Dashboard

The dashboard summarizes the geographic distribution of all students.

### Example

```text
       STUDENT GEOGRAPHIC DISTRIBUTION
       ───────────────────────────────

       Total Students: 30

       ┌─────────────────────────────┐
       │ Local             │    6    │
       ├─────────────────────────────┤
       │ District          │    7    │
       ├─────────────────────────────┤
       │ Within State      │    8    │
       ├─────────────────────────────┤
       │ Other State       │    6    │
       ├─────────────────────────────┤
       │ International     │    3    │
       └─────────────────────────────┘

       Total = 30 Students
```

### Dashboard Features

* Total student count
* Locality category counts
* Percentage distribution
* Search
* Category filtering
* Student-level details
* Updated classification
* Report/insight generation

---

# 🧪 Dummy Dataset

The MVP should contain **at least 30 students**.

The dataset must cover all five geographic categories.

| Category      | Example Count |
| ------------- | ------------: |
| Local         |             6 |
| District      |             7 |
| Within State  |             8 |
| Other State   |             6 |
| International |             3 |
| **Total**     |        **30** |

The dataset should contain realistic addresses from different localities, districts, states, and countries.

---

# ⚙️ MVP Features

## 1. Create

Create a new student record with:

* Student name
* Address
* Locality
* District
* State
* Country
* Academic information

The locality category is determined automatically.

## 2. View

Open any student and view:

```text
Student Name
Address
District
State
Country
-------------------------
Locality Classification
-------------------------
LOCAL / DISTRICT /
WITHIN STATE /
OTHER STATE /
INTERNATIONAL
```

## 3. Search

Search students using:

* Student ID
* Student name
* District
* State
* Country

## 4. Filter

Filter students by:

* Local
* District
* Within State
* Other State
* International

## 5. Update

Update student address/origin information.

The classification should be recalculated after geographic data changes.

## 6. Report / Insight

Generate a geographic distribution report showing:

* Total students
* Category-wise student count
* Category percentages
* Geographic distribution insights

---

# 🔍 Acceptance Test

The system should satisfy the following:

### Test 1 — Student Classification

A reviewer opens any student record.

**Expected:**

The student's correct locality classification is displayed.

### Test 2 — Classification Update

A student's geographic information is updated.

**Expected:**

The locality classification is recalculated correctly.

### Test 3 — Dashboard Accuracy

The reviewer opens the distribution dashboard.

**Expected:**

The sum of all locality categories equals the total number of student records.

```text
Local
+ District
+ Within State
+ Other State
+ International
        =
Total Students
```

### Test 4 — Search / Filter

The reviewer filters students by locality category.

**Expected:**

Only students belonging to the selected category are displayed.

---

# 🛠️ Technology Stack

> Update this section according to the technologies actually used by the team.

### Frontend

* HTML
* CSS
* JavaScript

### Backend

* Python / Flask

### Database

* SQLite / MySQL

### Data Visualization

* Chart.js / Matplotlib

### Development Tools

* Git
* GitHub
* VS Code

---

# 📁 Suggested Repository Structure

```text
student-locality-classification/
│
├── README.md
│
├── docs/
│   ├── technology-decision.md
│   └── er-diagram.png
│
├── src/
│   ├── app.py
│   ├── models/
│   ├── routes/
│   ├── services/
│   └── database/
│
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
│
├── data/
│   └── students.csv
│
├── tests/
│   └── test_classification.py
│
└── requirements.txt
```

---

# 📚 Documentation

The repository should contain:

### `README.md`

Project overview, architecture, setup instructions, features, and team information.

### `docs/technology-decision.md`

Major engineering decisions, including:

* Why the selected technology stack was used
* Locality classification approach
* Database design
* Why locality category is calculated
* Scalability considerations
* Data validation strategy

### `docs/er-diagram.png`

Entity Relationship Diagram for the vertical extension.

---

# 🚀 Getting Started

## Clone the Repository

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
cd student-locality-classification
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Run the Application

```bash
python app.py
```

Then open the application in your browser.

> Replace these commands if your actual project uses a different framework or technology stack.

---

# 🔐 Data Validation

The system should validate:

* Required student fields
* Valid country
* Valid state
* Valid district
* Valid address
* Duplicate student records
* Missing geographic information

Invalid or incomplete geographic data should not silently produce an incorrect classification.

---

# 📈 Future Enhancements

Possible future improvements include:

* Interactive geographic maps
* State/district-wise visualization
* CSV/Excel import
* PDF report generation
* Advanced analytics
* Geographic heatmaps
* Role-based access
* Automated data validation
* API integration for address verification
* Historical geographic distribution reports

---

# 🎓 Project Deliverables

The project delivers:

* [x] Working MVP
* [x] Student CRUD operations
* [x] Search and filtering
* [x] Automatic locality classification
* [x] Distribution dashboard
* [x] Dummy dataset with 30+ students
* [x] ER diagram
* [x] Database schema
* [x] Technology decision documentation
* [x] GitHub repository
* [x] Clear commit history
* [x] Live demonstration
* [x] Engineering decision defense

---

# 👥 Team Members

| Name                | Student ID |
| ------------------- | ---------- |
| **Thejes Santhosh** | 25190149   |
| **Nithin Thomas**   | 25190135   |
| **Melbin**          | 25190120   |
| **Shashidhara**     | 25190148   |

---

# 🏁 Conclusion

The **Student Locality & Geographic Classification** system provides a structured way for institutions to understand where their students come from.

By deriving locality classification from geographic information rather than relying on manual category selection, the system improves **data consistency, accuracy, and reporting reliability**.

The MVP demonstrates the complete workflow:

```text
Create
  ↓
View
  ↓
Search / Filter
  ↓
Classify
  ↓
Update
  ↓
Dashboard
  ↓
Report / Insight
```

---

## 📌 Project

**V02 — Student Locality & Geographic Classification**

**Purpose:** Accreditation, geographic student analysis, and institutional outreach planning.

**Team:** Thejes Santhosh · Nithin Thomas · Melbin · Shashidhara

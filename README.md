# 📚 Digital University Library
## Workshop No. 2 — Data System Architecture and Information Retrieval

**Course:** Databases II  
**University:** Universidad Distrital Francisco José de Caldas  
**Program:** Computer Engineering  
**Authors:**  
- David Stiven Muñoz Amaya — 20202020071  
- Janeth Oliveros Ramírez — 20182020100  
- Daniel Felipe Páez Mosquera — 20202020070  
**Date:** October 2025  

---

##  1. Introduction
The project proposes the creation of an Academic Digital Library Platform designed to complement the university’s physical library.  
It allows students and faculty to search, consult, and download DRM-free institutional content such as theses, research papers, and digital books.  

Core characteristics:  
- Institutional access (students, professors, admins, librarians).  
- Role-based permissions and secure authentication.  
- Hybrid access model (local + external licensed content).  
- Focus on scalability, reliability, and 24/7 availability.

---

##  2. Canvas Business Model
The Business Model Canvas defines:  
- **Value Proposition:** Efficient access to academic materials.  
- **Key Resources:** Digital content, metadata, and user management.  
- **Key Partners:** Collaboration with faculty for acquisition requests.  
- **Customer Segments:** Students, professors, librarians, and administrators.  
*(See Figure 1 in the original document.)*

---

##  3. Requirements Documentation

### 3.1 Functional Requirements
Defines 15 key system functionalities, including:  
- User registration and authentication.  
- Role-Based Access Control (RBAC).  
- Resource ingestion and approval workflow.  
- Metadata management and advanced search.  
- Reviews, ratings, notifications, and BI reports.  

### 3.2 Non-Functional Requirements
Specifies performance, scalability, availability, and security criteria:  
- Response times under 1–2 seconds.  
- 24/7 availability with controlled access.  
- Data protection and minimal personal data storage.  
- Use of relational + NoSQL databases.

---

##  4. Data System Architecture
A **hybrid architecture** integrating:
- **PostgreSQL** for structured, transactional data.  
- **MongoDB** for flexible and denormalized documents.  
- **Elasticsearch** for full-text search and filtering.  
- **Object Storage (GCS/MinIO)** for file management.  
- **ETL and BI Layers** for analytics and reporting.  

This ensures modularity, performance, and academic data integrity.

---

##  5. Information Requirements

### 5.1 Information Types and Relationships
Defines 9 key information types (IR1–IR9), linking each to user stories and the business model canvas (e.g., searches, metadata, logs, reviews, acquisitions, etc.).

### 5.2 Functional Scope and Query Examples
Provides functional areas with example SQL/NoSQL queries for:
- User behavior analytics.  
- Resource popularity and authorship.  
- Recent activity logs and license tracking.

### 5.3 Information Flow Overview
Describes *Operational Information* (user activity) and *Administrative Information* (validation, licensing, requests), ensuring both performance and consistency.

### 5.4 Reflection
Notes key design decisions:
- Separation between operational and analytical data.  
- Balance between functionality and privacy.  
- Metadata consistency and copyright compliance.

---

##  6. User Stories
Nine user stories (US1–US9) describing interactions for:
- Searching, downloading, and reviewing resources.  
- Professors suggesting acquisitions.  
- Librarians validating uploads and managing licenses.  
- Administrators handling user accounts and the catalog.  
Each includes priority, estimation, and acceptance criteria.

---

##  7. Entity–Relationship (ER) Model

### 7.1 General Description
Organized into five functional domains:  
1. Users and Roles  
2. Digital Content  
3. Suggestion Workflow  
4. Audit and Logging  
5. Support and Referential Integrity  

### 7.2 Main Improvements from Workshop 1
- Standardized entity names and data types.  
- Added `author_order` and restructured N:M relationships.  
- Improved semantic clarity between structural and transactional entities.

### 7.3 Graphical Representation
Final ER diagram, ensuring logical clarity and referential integrity.

---

##  8. Database Implementation (SQL)
Developed in **PostgreSQL** following the refined ER model.  
Includes:  
- DDL schema creation (primary/foreign keys, indexes).  
- Data population (10–20 sample records).  
- Referential integrity validation using pgAdmin 4.  

The design ensures normalization (up to 3NF) and extensibility.

---

##  9. Query Proposals (SQL)
Three main SQL queries demonstrate analytical capabilities:  
1. **Most Downloaded Resources** – ranks top resources.  
2. **Most Prolific Authors** – counts author publications.  
3. **Downloads by Program** – measures usage by department.  

Each query includes purpose, explanation, and validation results.

---

##  10. NoSQL Model
Implemented using a **MongoDB** schema with four collections:  
- `users`  
- `resources`  
- `suggestions`  
- `logs`  

The model supports full-text search, recommendations, and activity tracking through embedded JSON structures, improving read performance and scalability.

---

##  11. Query Proposals (NoSQL)
Three representative MongoDB queries:  
1. **Full-text Search** by title or author using `$regex`.  
2. **Recommendations** based on shared authors using `$lookup`.  
3. **Recent Download Activity** sorted by timestamp for real-time insights.  

These queries complement SQL operations and enable flexible, fast data retrieval.

---

##  12. Conclusions
The Digital University Library implements a hybrid data architecture combining PostgreSQL and MongoDB:  
- SQL ensures consistency and normalization.  
- NoSQL provides speed and flexibility for modern academic needs.  
Together, they enable a scalable, reliable, and data-rich platform for the university’s digital ecosystem.

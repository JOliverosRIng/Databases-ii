# 📚 Workshop N°1 – Project Definition and Database Modeling

**University:** Universidad Distrital Francisco José de Caldas  
**Program:** Computer Engineering  
**Date:** September 2025  

**Authors:**  
- David Stiven Muñoz Amaya – 20202020071  
- Janeth Oliveros Ramírez – 20182020100  
- Daniel Felipe Paez Mosquera – 20202020070  

---

## 📖 Overview
This project defines the architecture and requirements of an **Academic Digital Library Platform** designed to complement the physical library of the university. It covers the business model, functional and non-functional requirements, user stories, and an initial database architecture for managing academic resources and user interactions.

---

## 📑 Sections

### 1. [Introduction](https://github.com/JOliverosRIng/Databases-ii/blob/73f4b718abcac079aa575f04fbae00bc906dab72/Workshop-1/Workshop-1.pdf#page=1)
- Defines the purpose of the Digital University Library.  
- Explains the hybrid access model (local vs. licensed resources).  
- Describes the roles: students, professors, administrators, and librarians.  

### 2. [Canvas Business Model](https://github.com/JOliverosRIng/Databases-ii/blob/73f4b718abcac079aa575f04fbae00bc906dab72/Workshop-1/Workshop-1.pdf#page=2)
- Identifies **key partners**, **activities**, and **resources**.  
- Defines **value propositions**, **customer segments**, and **revenue streams**.  
- Outlines **customer relationships**, **channels**, and **cost structure**.  

### 3. [Requirements Documentation](https://github.com/JOliverosRIng/Databases-ii/blob/73f4b718abcac079aa575f04fbae00bc906dab72/Workshop-1/Workshop-1.pdf#page=3)
- **Functional Requirements:**  
  - Registration and authentication  
  - Role-based access control (RBAC)  
  - Resource ingestion, metadata management  
  - Search, recommendations, reviews, notifications, etc.  
- **Non-Functional Requirements:**  
  - Performance, scalability, availability  
  - Security, privacy, and data management  

### 4. [User Stories](https://github.com/JOliverosRIng/Databases-ii/blob/73f4b718abcac079aa575f04fbae00bc906dab72/Workshop-1/Workshop-1.pdf#page=4)
- Defines scenarios for:  
  - Searching and downloading resources  
  - Leaving reviews and ratings  
  - Professors suggesting acquisitions  
  - Librarians validating uploads and managing licenses  
  - Administrators managing users and catalog  

### 5. [Initial Database Architecture](https://github.com/JOliverosRIng/Databases-ii/blob/73f4b718abcac079aa575f04fbae00bc906dab72/Workshop-1/Workshop-1.pdf#page=6)
- Describes the **4-layer architecture model**:  
  1. Presentation Layer  
  2. Application Layer  
  3. Domain Layer  
  4. Infrastructure Layer  
- Details **data flow and storage solutions**: PostgreSQL, MinIO, OpenSearch.  
- Discusses replication, partitioning, and data pipelines for analytics.  
- Includes an **Entity–Relationship Diagram** with core entities (User, Resource, Author, Download, License, Provider).  
---

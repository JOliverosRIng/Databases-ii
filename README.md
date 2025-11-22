# 📚 Digital University Library
## Workshop No. 2 — Data System Architecture and Information Retrieval

**Course:** Databases II  
**University:** Universidad Distrital Francisco José de Caldas  
**Program:** Computer Engineering  
**Authors:**  
- David Stiven Muñoz Amaya — 20202020071  
- Janeth Oliveros Ramírez — 20182020100  
- Daniel Felipe Páez Mosquera — 20202020070  
**Date:** November 2025  

---

# Digital University Library – Data Architecture (Workshops 3)

This repository contains the documentation and related artefacts for the **data architecture design of the Digital University Library**, developed as part of the *Databases 2* course.

The main goal of the work is to specify how the platform stores, manages and processes information in a consistent, scalable and efficient way, addressing both functional requirements and non-functional aspects such as performance, concurrency and availability.

---

## Repository Contents

- `WORKSHOP3.pdf`  
  Consolidated report for Workshop 3. This is the main document and includes:
  - Refined scope and adjustments based on the Workshop 2 submission.
  - Concurrency analysis (scenarios and anomalies).
  - Concurrency solutions (isolation levels, locking, OCC, MVCC, retry/backoff).
  - Parallel and distributed database design (polyglot architecture, data distribution, parallel queries).
  - High-level diagrams of the architecture and data distribution.

- `WORKSHOP2.pdf` 
  Original Workshop 2 report, used as the starting point for the extended design in Workshop 3.

- `figures/`
  Folder containing the diagrams used in the report, for example:
  - High-level distributed architecture.
  - Data distribution across nodes.
  - Parallel search and recommendation query flow.

---

## Document Structure (WORKSHOP3.pdf)

The main report is organised into three conceptual parts:

1. **Refined Requirements and Conceptual Model**  
   - Review and refinement of the scope defined in Workshop 2.  
   - Description of the business context and main functional and non-functional requirements.  
   - Information requirements expressed as representative queries.  
   - Conceptual data model for the Digital University Library and its connection to user needs.

2. **Concurrency Analysis and Concurrency Solutions**  
   - Identification of critical concurrency scenarios in:
     - The relational metadata layer (resources, users, reviews, licences).
     - The NoSQL activity-log layer (downloads, search logs).  
   - Analysis of potential anomalies (lost update, non-repeatable read, phantom read, write skew).  
   - Proposed concurrency-control mechanisms:
     - Transaction isolation levels.
     - Row-level locking versus table-level locking.
     - Optimistic Concurrency Control (OCC) using version columns.
     - Use of MVCC (Multi-Version Concurrency Control) in PostgreSQL.
     - Retry/backoff strategies for conflicts and transient failures.

3. **Parallel and Distributed Database Design**  
   - Design of a parallel and distributed data architecture following a polyglot persistence approach:
     - PostgreSQL as the relational core for authoritative metadata.
     - Sharded MongoDB for high-volume activity logs and behavioural data.
     - Parallel search engine for full-text search and recommendations.
     - Distributed object storage for PDF/EPUB files.
     - Data warehouse layer for analytics and BI dashboards.  
   - Distribution and replication of data across nodes (Node A, B, C, D, search cluster, object storage, data warehouse).  
   - Parallel execution of queries:
     - Search queries across index shards.
     - Metadata retrieval from PostgreSQL read replicas and cache.
     - Aggregations on logs to support recommendations and analytics.

---

##  Conclusions
The Digital University Library implements a hybrid data architecture combining PostgreSQL and MongoDB:  
- SQL ensures consistency and normalization.  
- NoSQL provides speed and flexibility for modern academic needs.  
Together, they enable a scalable, reliable, and data-rich platform for the university’s digital ecosystem.

---
title: "AudioAvenue: Music Streaming Database Design and Implementation"
excerpt: "Design and implementation of a relational database for a music streaming service, including ER modeling, SQL queries, procedures, and triggers."
collection: research_projects
permalink:
share: false
related: false
---

## Project Overview

This project presents the design and implementation of **AudioAvenue**, a music streaming service database.

The goal was to build a robust and scalable relational database system capable of managing users, artists, songs, albums, playlists, and subscription plans.

The project covers the full pipeline from **conceptual modeling to SQL implementation**, simulating a real-world application similar to modern music streaming platforms.


---

## Problem Statement & Motivation

Music streaming platforms must efficiently manage:

- Large volumes of **users and content**
- Complex relationships between **artists, songs, albums, and playlists**
- Different **subscription plans and pricing models**

Key challenges include:

- Designing a **normalized and consistent schema**
- Supporting **many-to-many relationships** (e.g., playlists and songs)
- Ensuring **data integrity and constraints**
- Enabling efficient **data retrieval through SQL queries**

---

## System Design

### 1. Conceptual Design (ER Model)

We designed an **Entity-Relationship (ER) model** including:

- **User**: platform users with personal information  
- **Artist**: music creators  
- **Song**: individual tracks  
- **Album**: collections of songs  
- **Playlist**: user-created collections  
- **Genre**: classification of music  
- **SubscriptionType**: pricing plans  
- **Country**: geographical information  

📌 Key relationships:

- Artists **produce** songs (many-to-many)  
- Albums **contain** songs (one-to-many)  
- Users **create** playlists (one-to-many)  
- Playlists **contain** songs (many-to-many)  
- Users **subscribe** to a subscription type (many-to-one)  

---

### 2. Logical Database Design

The ER model was translated into relational schemas with:

- Primary keys for each entity  
- Foreign keys enforcing relationships  
- Junction tables for many-to-many relations:
  - `Produce`
  - `PlaylistContains`

📌 Example:

- A song references:
  - a **genre**
  - an optional **album**
- A user references:
  - a **country**
  - a **subscription type**

---

## Implementation

The database was implemented using SQL with:

### Tables
- `User`, `Artist`, `Song`, `Album`
- `Playlist`, `Genre`, `Country`
- `SubscriptionType`
- Relationship tables (`Produce`, `PlaylistContains`)

### Key Features

- **Foreign key constraints** for referential integrity  
- **ON DELETE CASCADE / SET NULL** policies  
- Structured schema supporting real-world use cases  

---

## SQL Queries & Operations

We implemented a variety of SQL queries, including:

- Retrieving all entities (users, songs, artists, etc.)
- Aggregations:
  - Number of songs per artist  
  - Number of artists per country  
- Conditional queries:
  - Filtering by genre or artist name  

📌 Example insights:

- Count of songs produced per artist  
- Distribution of artists across countries  
- Revenue estimation by subscription type  

---

## Advanced SQL Programming

### Functions

- `getAge(date)` → computes user age  
- `Artists_by_genre(genre)` → counts artists per genre  

### Stored Procedures

- Retrieve number of songs by artists from a given country  

### Triggers

- Prevent duplicate songs in playlists  
- Enforce minimum age (13+) for users  

---

## Key Results

- Successfully designed a **normalized relational database**
- Modeled complex real-world relationships
- Implemented **advanced SQL logic** (functions, triggers, procedures)
- Ensured **data integrity and consistency**

---

## Insights & Contributions

- Demonstrated how to design scalable databases for real applications  
- Highlighted the importance of **normalization and constraints**  
- Showed how SQL can handle both:
  - Data storage  
  - Business logic  

---

## Discussion

### Strengths
- End-to-end database design (ER → SQL)  
- Realistic application scenario  
- Strong use of SQL features beyond basic queries  

### Limitations
- No indexing or query optimization analysis  
- No performance benchmarking  
- Static dataset (no real-time streaming data)  

### Future Work
- Add indexing and performance tuning  
- Integrate with a backend application (API)  
- Extend to recommendation systems  
- Incorporate user listening history analytics  

---

## Resources

- **Report**: [AudioAvenue - Music Streaming Database Project](/files/AudioAvenue.pdf)

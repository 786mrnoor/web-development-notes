# 💡 What is MongoDB?

**MongoDB** is a **NoSQL, document-oriented database** that stores data in a flexible, JSON-like format called **BSON** (Binary JSON). It is designed for **high performance**, **high availability**, and **easy scalability**.

---

## 🔍 Key Features:

| Feature                | Description                                                          |
| ---------------------- | -------------------------------------------------------------------- |
| **Document-based**     | Stores data in documents (like JSON), not rows and columns.          |
| **Schema-less**        | You don't need to define the structure in advance (flexible schema). |
| **Scalable**           | Supports horizontal scaling using **sharding**.                      |
| **Indexing**           | Allows indexes on any field to improve query performance.            |
| **Replication**        | Provides high availability with **replica sets**.                    |
| **Aggregation**        | Powerful data processing and transformation pipeline.                |
| **Geospatial Queries** | Built-in support for location-based data.                            |

---

## 📦 MongoDB Data Structure

```json
{
  "_id": "60a6f9e46d1b8e001f56e1ef",
  "name": "Noor Mohammad",
  "email": "noor@example.com",
  "skills": ["HTML", "CSS", "JavaScript"],
  "age": 23
}
```

* Stored in a **collection** (like a table in SQL).
* This whole object is a **document**.
* Each document has a unique `_id` field automatically created.

---

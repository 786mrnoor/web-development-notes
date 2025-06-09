# 🔍 NoSQL vs SQL — What's the Difference?

| Feature                   | **SQL (Relational DB)**                  | **NoSQL (Non-Relational DB)**                              |
| ------------------------- | ---------------------------------------- | ---------------------------------------------------------- |
| **Data Structure**        | Tables with rows & columns               | Documents, key-value pairs, wide-columns, or graphs        |
| **Schema**                | Fixed schema (predefined columns)        | Flexible schema (can vary from document to document)       |
| **Query Language**        | Structured Query Language (SQL)          | Custom query syntax (e.g., JSON-style in MongoDB)          |
| **Relationships (JOINs)** | Supports complex JOINs between tables    | Limited or no JOINs; usually uses embedding or references  |
| **Examples**              | MySQL, PostgreSQL, Oracle, SQL Server    | MongoDB, CouchDB, Redis, Cassandra, Neo4j                  |
| **Data Integrity**        | Strong ACID compliance                   | Often uses eventual consistency (but can support ACID too) |
| **Best Use Case**         | Structured data with clear relationships | Unstructured or semi-structured data, scalability needed   |
| **Scalability**           | Vertical scaling (scale-up)              | Horizontal scaling (scale-out across servers)              |
| **Storage Format**        | Row-based                                | Document-based (JSON/BSON), key-value, columnar, or graph  |
| **Transactions**          | Full support for complex transactions    | Limited transaction support (some modern NoSQL support it) |

---

### 🧪 Quick Example

#### 🔷 SQL (MySQL)

```sql
SELECT name, email FROM users WHERE age > 18;
```

#### 🔶 NoSQL (MongoDB)

```js
db.users.find({ age: { $gt: 18 } }, { name: 1, email: 1 });
```

---

### 📌 When to Use What?

| Use SQL When ✅                            | Use NoSQL When ✅                                      |
| ----------------------------------------- | ----------------------------------------------------- |
| You need complex queries and transactions | You need fast development and flexibility             |
| Your data structure doesn't change often  | You expect schema to evolve frequently                |
| Relationships between data are important  | You’re working with unstructured/semi-structured data |
| You need strong consistency               | You need high availability and scalability            |

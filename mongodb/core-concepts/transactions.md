# Transactions in MongoDB

A transaction in MongoDB lets us group multiple read and write operations into a single atomic unit.

Transactions provides data **consistency** by ensuring that either all the transaction within the transaction are commited to the database, or none of them are.

MongoDB transactions ensure ACID properties:

- **Atomicity**: All or nothing.
- **Consistency**: Database remains valid before and after.
- **Isolation**: Other operations don’t see intermediate states.
- **Durability**: Once committed, changes persist.

👉 Transactions are available in replica sets (MongoDB 4.0+) and sharded clusters (MongoDB 4.2+).

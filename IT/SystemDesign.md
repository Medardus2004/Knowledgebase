# System Design

## ACID - Atomicity Consistency Isolation Durability
ensure reliable database transaction. 
- **Atomicity** means all or nothing
- **Consistency** means the transaction must follow all the rules and leave the database in a good state
- **Isolation** means concurrent transactions are isolated from each other
- **serializable** makes transaction run one after another, as if they were in a single file

## Sevan strategies to scale database
- **Indexing:** Analyze the query patterns of your application and create the right indexes
- **Materialized Views:** precompute complex query results and store them for faster access
- **Denormalization:** reduce complex joins to improve query performance
- **Vertical Scaling**: add CPU, RAM, Storage
- **Caching**: Store frequently accessed data in a faster storage layer
- **Replication:** Create replicas of your primary database
- **Sharding:** Load resources that the page will need before they are needed

# Database Schema & Entity-Relationship Diagram

## Database: PostgreSQL/MongoDB

### Tables / Collections

### 1. Users Table

| Column Name | Type            | Description           |
| ----------- | --------------- | --------------------- |
| id          | UUID (PK)       | Unique user ID        |
| username    | STRING          | Unique username       |
| email       | STRING          | User email (unique)   |
| password    | STRING (hashed) | User password         |
| created_at  | TIMESTAMP       | Account creation date |

### 2. Photos Table

| Column Name | Type      | Description        |
| ----------- | --------- | ------------------ |
| id          | UUID (PK) | Unique photo ID    |
| user_id     | UUID (FK) | Owner of the photo |
| url         | STRING    | Cloud storage URL  |
| title       | STRING    | Optional title     |
| uploaded_at | TIMESTAMP | Upload timestamp   |

### 3. Galleries Table

| Column Name | Type      | Description            |
| ----------- | --------- | ---------------------- |
| id          | UUID (PK) | Unique gallery ID      |
| user_id     | UUID (FK) | Owner of the gallery   |
| title       | STRING    | Gallery name           |
| theme       | STRING    | Selected gallery theme |
| created_at  | TIMESTAMP | Gallery creation date  |

### 4. Gallery_Photos (Join Table)

| Column Name | Type      | Description       |
| ----------- | --------- | ----------------- |
| gallery_id  | UUID (FK) | Linked gallery ID |
| photo_id    | UUID (FK) | Linked photo ID   |

## Entity-Relationship Diagram (ERD)

```plaintext
[Users] 1---M [Photos]
[Users] 1---M [Galleries]
[Galleries] M---M [Gallery_Photos] M---M [Photos]
```

## Notes:

- **Indexes** will be used on `email`, `user_id`, and `gallery_id` for fast lookups.
- **Foreign keys** enforce relational integrity.
- **Cloud storage** (AWS S3/GCP) will store images; only URLs are stored in the database.

This schema ensures efficient storage and retrieval while maintaining scalability for future features.

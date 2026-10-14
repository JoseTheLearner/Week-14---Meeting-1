# Capstone Project Proposal

## Project: Engine Tuning Shop Management System

### 1. Business Idea

The Engine Tuning Shop Management System manages customers and the engine tuning jobs they request for their vehicles. It records customer information, vehicle details, tuning services, costs, and job statuses to help the shop organize its transactions and monitor service progress.

### 2. Database Schema

#### Table 1: customers

Stores information about customers who use the engine tuning shop.

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key; uniquely identifies each customer |
| name | TEXT | Customer's full name |
| phone | TEXT | Customer's mobile number |
| vehicle_model | TEXT | Vehicle make and model |
| plate_number | TEXT | Vehicle license plate number |

#### Table 2: tuning_jobs

Stores the engine tuning services requested by customers.

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key; uniquely identifies each tuning job |
| customer_id | INTEGER | Foreign key referencing customers.id |
| service_type | TEXT | Type of tuning service requested |
| description | TEXT | Details of the requested work |
| cost | REAL | Estimated or final service cost |
| status | TEXT | Job status: Pending, In Progress, or Completed |
| created_at | TEXT | Date and time the job was created |

#### Relationship

One customer can have multiple tuning jobs. Each tuning job belongs to one customer through the `customer_id` foreign key.

The customers table stores customer and vehicle information, while the tuning_jobs table stores the services performed or requested for those customers.

### 3. API Routes

#### Customers Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | /api/customers | Retrieves all registered customers |
| GET | /api/customers/:id | Retrieves a specific customer by ID |

#### Tuning Jobs Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | /api/tuning-jobs | Retrieves all tuning jobs |
| GET | /api/tuning-jobs/:id | Retrieves a specific tuning job by ID |
| POST | /api/tuning-jobs | Creates a new tuning job for an existing customer |
| PUT | /api/tuning-jobs/:id/status | Updates the status of a tuning job |
| DELETE | /api/tuning-jobs/:id | Deletes a tuning job |
| GET | /api/customers/:id/tuning-jobs | Retrieves all tuning jobs belonging to a specific customer |

#### Additional Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | / | Confirms that the API server is running |
| GET | /api/health | Checks whether the API is operational |

### 4. Technologies

- Node.js
- Express.js
- SQLite using better-sqlite3
- CORS
- dotenv
- express-rate-limit
- Git and GitHub

### 5. Project Scope

The system will initially focus on managing customer records and engine tuning jobs. Planned operations include retrieving records, creating tuning jobs, updating job statuses, and deleting tuning jobs.

The database will use a foreign key to connect tuning jobs to customers. Future development will implement database initialization, input validation, error handling, authentication if required, and deployment.
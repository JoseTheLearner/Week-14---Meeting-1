# Database Schema Plan

## Project: Engine Tuning Shop Management System

The system manages customers and the engine tuning jobs they request for their vehicles.

### Table 1: customers

Stores information about customers who use the engine tuning shop.

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key; uniquely identifies each customer |
| name | TEXT | Customer's full name |
| phone | TEXT | Customer's mobile number |
| vehicle_model | TEXT | Vehicle make and model |
| plate_number | TEXT | Vehicle license plate number |

### Table 2: tuning_jobs

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

### Relationship

One customer can have multiple tuning jobs. Each tuning job belongs to one customer through the `customer_id` foreign key.

The customers table stores customer and vehicle information, while the tuning_jobs table stores the services performed or requested for those customers.
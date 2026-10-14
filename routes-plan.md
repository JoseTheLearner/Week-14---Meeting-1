# API Routes Plan

## Project: Engine Tuning Shop Management System

The API will manage customers and the engine tuning jobs they request.

### Table 1: Customers Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | /api/customers | Retrieves all registered customers |
| GET | /api/customers/:id | Retrieves a specific customer by ID |

### Table 2: Tuning Jobs Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | /api/tuning-jobs | Retrieves all tuning jobs |
| GET | /api/tuning-jobs/:id | Retrieves a specific tuning job by ID |
| POST | /api/tuning-jobs | Creates a new tuning job for an existing customer |
| PUT | /api/tuning-jobs/:id/status | Updates the status of a tuning job |
| DELETE | /api/tuning-jobs/:id | Deletes a tuning job |
| GET | /api/customers/:id/tuning-jobs | Retrieves all tuning jobs belonging to a specific customer |

### Additional Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | / | Confirms that the API server is running |
| GET | /api/health | Checks whether the API is operational |

### Notes

- GET retrieves information from the server.
- POST creates a new record.
- PUT updates an existing record.
- DELETE removes a record.
- The `:id` parameter identifies a specific customer or tuning job.
- The `customer_id` foreign key connects each tuning job to its customer.
# Leaves Subsystem – API Endpoints (Milestone 1)

Base path: `/leaves`

## Policy

### `POST /leaves/policy/leave-types`
Create a leave type.  
Body: `Partial<LeaveType>`

### `GET /leaves/policy/leave-types`
List all leave types.

### `POST /leaves/policy/vacation-packages`
Create a vacation package.

### `GET /leaves/policy/vacation-packages`
List all vacation packages.

## Requests

### `POST /leaves/requests`
Create a new leave request.

### `GET /leaves/requests/employee/:employeeId`
Get all requests for an employee.

### `PATCH /leaves/requests/:id/status`
Update the status of a leave request.

## Tracking

### `GET /leaves/tracking/employee/:employeeId`
Get all balances for an employee.

### `POST /leaves/tracking/balances`
Create or seed an employee balance document.

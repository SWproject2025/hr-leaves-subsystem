# Leaves Subsystem – Integration Notes (Milestone 1)

## Upstream Inputs

- Employee Profile
  - `employeeId`, `employmentType`, `hireDate`, `grade`, `location`
  - `vacationPackageCode`
- Organizational Structure
  - `managerId` for each employee
- Time Management
  - Work schedule (work days, weekends)
  - Calendar code per employee
- Payroll
  - Daily salary rate
  - Paycodes per leave type

For Milestone 1, these come from `backend/src/integration/dummy/*.dummy.ts` only.  
No real HTTP or message bus integration is implemented yet.

## Downstream Outputs

- Leaves subsystem will later send:
  - Updated leave balances to Payroll
  - Absence events to Time Management
  - Notifications to the Notification subsystem

In Milestone 1, we only persist data locally in MongoDB and ensure the IDs are prepared for future integration.

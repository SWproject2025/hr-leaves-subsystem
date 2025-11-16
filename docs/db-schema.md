# Leaves Subsystem – DB Schema (Milestone 1)

## Collections

### `leave_types`
- `code` (string, unique)
- `name` (string)
- `category` (enum: ANNUAL_BALANCE, OTHER)
- `isPaid` (boolean)
- `payCodeId` (string, optional)
- `requiresDocument` (boolean)
- `maxDurationDays` (number, optional)
- `trackCumulative` (boolean)
- `metadata` (object)

### `vacation_packages`
- `code` (string, unique)
- `name` (string)
- tenure / grade / location filters
- `entitlements[]`:
  - `leaveTypeCode`
  - `annualDays`
  - `maxCarryForwardDays`
  - `encashable`

### `leave_settings`
- `employmentType`
- `accrualFrequency`
- `roundingMethod`
- `resetCriterion`
- `defaultMaxCarryForwardDays`
- `carryForwardExpiryYears`
- `pauseAccrualDuringUnpaidLeave`
- `pauseAccrualDuringSuspension`

### `calendars`
- `code` (string, unique)
- `name` (string)
- `holidays[]` (date, name)
- `blockedPeriods[]` (startDate, endDate, reason)

### `leave_requests`
- `employeeId`
- `leaveTypeCode`
- `calendarCode`
- `startDate`, `endDate`
- `requestedDaysRaw`, `requestedDaysRounded`
- `justification`
- `attachmentIds[]`
- `status`
- `managerId`
- `hrOwnerId`
- flags: `isPostLeaveRequest`, `isUnpaidPartially`, `unpaidDays`

### `leave_approval_history`
- `leaveRequestId`
- `actorId`
- `actorType`
- `action`
- `comment`

### `leave_attachments`
- `leaveRequestId`
- `fileName`
- `fileUrl`
- `contentType`

### `leave_balances`
- `employeeId`
- `leaveTypeCode`
- `cycleStartDate`, `cycleEndDate`
- `accruedDaysRaw`, `accruedDaysRounded`
- `takenDays`, `pendingDays`
- `carryOverDays`, `encashedDays`, `unpaidDays`
- `cumulativeSickDaysOver3Years`
- `maternityLeaveCount`

### `leave_manual_adjustments`
- `employeeId`
- `leaveTypeCode`
- `daysDelta`
- `reason`
- `hrUserId`
- `balanceId`

### `leave_accrual_jobs`
- `type`
- `runDate`
- `status`
- `processedCount`
- `errorCount`
- `errorMessage`

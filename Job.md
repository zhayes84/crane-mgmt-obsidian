# Data Fields

- **Job Name** (text, unique, required)
	- `Job Name` will be the name given when job is scheduled and viewed in `/schedule`.
- **Customer** (select, required)
- **City**
- **State**
- **Job Status** (select, required)
	- Options
		- Not Started
		- Quoted
		- Scheduled
		- In Progress
		- Completed
- **Quoted Date** (datetime, not required)
- **Scheduled** (yes or no, required)
	- Can be auto populated if scheduled date is present.
- **Scheduled Date** (datetime, not required)
- **Arrival Time** (datetime, not required)
	- Not required but **strongly advised** to populate
- **Object(s) to be lifted** (not unique)
	- Can be free text since I don't think businesses will need to track this over time
- **Maximum lift radius** (not unique)
- **Lift radius units** (select, not unique, not required)
- **Weights for objects to be lifted** (not unique)
- **Weight Units** (select, not unique, not required)
- Time allotted for job - 8 hours, 3 days, 4 weeks, etc.
- Any `/equipment` needed - spread bars, man basket, extra duty blocks, etc.
- `/personnel` 
	- Personnel assigned to the job (crane ops, helpers, mechanics, etc.)

Page will have a map and/or images with annotations depicting the job's details.

Page could also show directions and expected weather.

We need to track where jobs are in their lifecycle.

Potentially need to track whether a lift plan has been submitted or is that part of the quoting step?
# Job Lifecycle

- Started but not quoted
- Quoted and waiting on customer approval
- Scheduled
- In Progress
- Completed
- Billed?
- Paid?
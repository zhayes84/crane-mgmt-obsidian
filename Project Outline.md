SaaS for crane service businesses.

**Business** - our SaaS customers
**Customer** - our SaaS customer's customer
# Features

Each of our Businesses will have all of these features unique to them. So likely, `business_id` will be a column in each db table to separate each customer's data.
## CRM
- Customer Name 
- Address
- Contacts (many per customer)
- Jobs
# Routes

## `/` - Home Dashboard

Default view 
## `/customers` - Customers

Default view is the Customer table.

Clicking on a customer takes user to a `/customer/[slug]` view. 
### `/customers/[slug]` - Individual [[Customer]]

This page shows Customer information plus: 

- Jobs - of all statuses
- Contacts - of all persons associated with the selected customer
## `/jobs` - Jobs

This page contains a data table consisting of jobs of all statuses. Job statuses include:

1. Not Started
2. Quoted
3. Scheduled
4. In Progress
5. Completed

Most likely, upcoming jobs would be the default sort order but filters and sortable column headers would easily allow the user to navigate to the desired job view.

Clicking on a job takes user to a `/jobs/[slug]` view.
### `/jobs/[slug]` - Individual [[Job]]

This page contains all relevant job information:

- Job Name - `Job Name` will be the name given when job is scheduled and viewed in `/schedule`.
- Customer
- Job Status (Not Started, Quoted, Scheduled, In Progress, Completed)
- Date
- Object(s) to be lifted
- Maximum lift radius
- Weights for objects to be lifted
- map drawing w/ annotations
    - directions and expected weather
- Time alotted for job - 8 hours, 3 days, 4 weeks, etc.
- Any `/equipment` needed - spread bars, man basket, extra duty blocks, etc.
- `/personnel` - Personnel assigned to the job (crane ops, helpers, mechanics, etc.)
## `/contacts` - Contacts

Table or list view of all individual contacts on one page.
### `/contacts/[slug]` - Individual [[Contact]]

- First name
- Last name
- Email
- Phone number(s)
- Socials
- Jobs 
## `/schedule` - Main Schedule

Primarily shows Jobs scheduled. Is used as a "dashboard" for everyone in operations to view and plan around.
### `/schedule/[slug]` - Individual [[Schedule]]

Individual schedules can be made or "shown" per:

- Employee - as a personal schedule for meetings, jobs, etc.
- Equipment - showing what jobs a specific piece of equipment will be due to work and when

More individual schedules may be needed as planning progresses.
## `/equipment` - [[Equipment]] Needed for Jobs

Cranes, slings, hooks, spread bars, man basket, equipment basket, etc.

- Name
- Type
- Make
- Model
## `/personnel` - Business Personnel

Crane operators, helpers, sales staff, supervisors, etc.
### `/personnel/[slug]` - Individual [[Business Personnel]]

- First name 
- Last name 
- Email
- Phone number(s)
- Socials
- Jobs 
# Workflow Example

1. Potential or existing customer calls needing quote for a crane lift. 
2. The salesman answers the phone and gathers potential customer's details such as:
    - Business Name
    - PoC Name
    - PoC Phone Number
    - Date of Service Needed
    - Dimensions of items to be lifted (height, width, weight)
    - Site address or location
    - Estimated number of days crane is needed
    - PO Number
    - Any additional details (notes)
3. Salesman/Estimator goes on site to determine site access and crane radius
4. Salesman/Estimator determines proper crane for lift
5. Salesman/Estimator produces quote and sends to potential customer
6. Customer accepts quote
7. Salesman/Supervisor schedules crane, personnel, and equipment needed on designated date
8. Crane operator and support personnel observe schedule, gather any special/additional equipment needed for lift on scheduled date & time, and perform lift.
9. Personnel complete lift -> Salesman/Operations review job details and hand over job details to financial/accounting department.

# Dev Ops

This site will use Sveltekit 3, Svelte 5, tailwindcss, Directus CMS, Umami Analytics, and potentially Twenty CRM. 

I don't know if basing the site's functionality on Twenty and using Twenty's API is the right move or not. The alternative is building our own CRM from scratch.

## Data Relationships

- Customers can have many:
	- Contacts
	- Jobs
	- Equipment
	- Schedules

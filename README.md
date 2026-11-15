# Fernwood time-off tracker

Build an internal time-off request tracker for our team.

Small fictional demo: mock login, localStorage only. No live Slack, Google Workspace or Calendar integration. Do not use with real employee data.

## Requirements and sources

- Managers approve up to 5 consecutive days; Anything over 10 consecutive days needs the CEO. No more than 2 people out on the same team at once. — amara.okonkwo@fernwoodlabs.io
- PTO accrues at about 1.67 days per month; Balances currently live in a Google Sheet called PTO Balances; Unused days above the carryover cap are forfeited on Dec 31. — sophie.lindgren@fernwoodlabs.io
- Internal tools should be a single-page web app in TypeScript with Google Workspace login; No new paid vendors; Employee data must not be exposed publicly; Keep the codebase small and tested. — hannah.cho@fernwoodlabs.io
- Suggested data model: requests(id, employee_email, start_date, end_date, type, status, approver_email, created_at); Status values: pending, approved, denied, cancelled; Prefers a small repo with unit tests for the day-counting and balance logic. — marcus.webb@fernwoodlabs.io
- Wants a team calendar view showing who is out, with a mobile-friendly layout and keyboard accessibility; Counting days must skip weekends and company holidays. — leila.farouk@fernwoodlabs.io
- Brand: teal accent (#0F766E), Inter font, lots of white space; Status colors: pending amber, approved green, denied red; One primary action per screen. — tom.aldrich@fernwoodlabs.io
- At least one Customer Success person must be working at all times; She needs to see overlaps on a team calendar before approving. — nina.alvarez@fernwoodlabs.io
- Sales cannot take PTO during the last two weeks of each quarter without his approval; He wants to see the sales team's requests before approving. — raj.patel@fernwoodlabs.io

## Unresolved questions

- What is the exact PTO carryover cap? (Not specified in Sophie's answer)
- How should the system handle requests between 6 and 10 consecutive days? (Approval path not specified)
- Which teams are considered 'Customer Success' and 'Sales' for coverage rules? (Not defined)
- Are company holidays to be manually entered or pulled from a source? (Not specified)
- Is there a maximum number of PTO days an employee can accrue? (Not specified)
- Who approves requests of 6–10 consecutive days? The supplied policy specifies only up to 5 and over 10.
- What are the specific rules for approving time-off requests that exceed 5 consecutive days, and how do you handle overlapping approvals within the same team?

## Run

`npm install` · `npm run dev` · `npm test` · `npm run build`

Requires Node >=22.6. Holidays and balances are demo configuration, not company records.
For this demo, notice uses business days for request length and calendar days for the notice period. Approval for 6–10 days must be clarified; do not autoapprove it.

## Research sources


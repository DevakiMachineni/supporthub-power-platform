1. What is SupportHub?
SupportHub is a simple customer support (case management) system that I built using Microsoft Power Platform and Dataverse. Support agents can log customer problems (called "cases"), follow them through a clear process, and close them when they are solved. Managers can see how many cases are open and how urgent they are. Agents can also use a mobile app to work on cases on the go. I built this project to practice and show my hands-on skills in Power Platform and Dynamics 365.
2. Tools Used- What I used it for
Microsoft Dataverse- Store all data (tables, relationships, security roles)
Model-driven app- Main app for agents ("SupportHub Agent")
Business Process Flow- Guide a case through its steps
Dashboards and charts- Show open cases by priority and status
Canvas app- Mobile app for agents ("SupportHub Mobile")
Power Fx- Formulas for filtering, saving data, and error handling
Security roles- Control who can see and do what
Power Automate Flow- Sends an email to the manager when a high priority case is created.
Power BI- Report that shows case trends, priority, and resolution time.
3. Key Design Decisions
Dataverse instead of SharePoint or Excel: Dataverse gives me real relationships between tables and built-in security.
Two apps for two needs: The model-driven app is best for office work with lots of data. The canvas app is best for a simple mobile screen.
Business Process Flow: It guides agents step by step, so no one skips a step.
Three security roles: Agents do daily work, managers see more, and read-only users can only look. This follows the "least access" rule.
Status choices without "Closed": I use New, In Progress, Waiting on Customer, and Resolved. [Explain why in one sentence.]
Named formula for theme colors: I change colors in one place, and the whole canvas app updates.
Role-based screen: The manager screen is hidden from agents so they cannot see it.
4. What was Delivered
A. Data Model (Dataverse)
Created 5 tables: Product, Customer Account, Case, Case Note, SLA Policy
Set up relationships between the tables
Created 3 security roles: Agent, Manager, Read-only
Case Status choices: New, In Progress, Waiting on Customer, Resolved
B. Model-driven App ("SupportHub Agent")
Built the app navigation (sitemap), forms, and views
Built a Business Process Flow with these stages: Open → Investigate → Resolve → Close
Built a dashboard that shows open cases by priority and status
Views Case form Business process flow Dashboard
C. Canvas App ("SupportHub Mobile")
Screens: case list, case details, new case form, photo attachment
Power Fx used for: filtering, Patch, Collect, error handling, and a named formula for theme colors
A manager-only screen that is shown based on the user's role
Case list Case details New case Photo attachment Manager screen
D. Automation (Power Automate)
Cloud flow (new case): When a case is created, the flow picks an owner based on product and priority, then sends a Teams or email message.
Approval flow: If a refund or escalation is above a set amount, the flow sends it to the manager to approve or reject.
Scheduled flow: Every day, the flow sends a summary of open cases and overdue cases.
Error handling: Used Scopes (Try / Catch), "Run after" settings, and retry settings. Every action has a clear name.

Results: Tested with 10 sample cases. All owners were assigned correctly.
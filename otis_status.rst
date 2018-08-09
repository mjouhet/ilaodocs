==========================
Triage & Intake Statuses
==========================

Triage statuses
=================
Triage statuses capture the user from the first `get legal help <https://www.illinoislegalaid.org/get-legal-help>`_ page to either intake or referrals.

Triage statuses include users who were given the modal in legal content or started on Get Legal Help.

+--------------------------+-----------------------------------------+
|    Name                  | Definition                              |
+==========================+=========================================+
| Modal                    | User was shown the modal but closed it  |
+--------------------------+-----------------------------------------+
| Modal - intake available | User entered zip in modal& shown intake |
|                          | was available but did not proceed       |
+--------------------------+-----------------------------------------+
| Modal - intake not       | User was shown the modal, provided zip  |
|         available        | but intake was not available            |
+--------------------------+-----------------------------------------+
| Started                  | User submitted the main form & stopped  |
+--------------------------+-----------------------------------------+
| Legal issue and top of   | User accessed 1 of 2 pages to determine |
| triage tree              | what their legal issue is and stopped   |
+--------------------------+-----------------------------------------+
| Out of area              | User entered a non-IL address           |
+--------------------------+-----------------------------------------+
| Program triage           | Users started program triage rules.     |
+--------------------------+-----------------------------------------+
| Referrals                | Users were given legal aid referrals.   |
|                          | User never saw online intake.           |
+--------------------------+-----------------------------------------+
| Over-income Referrals    | Users were given over-income referrals. |
|                          | User never saw online intake.           |
+--------------------------+-----------------------------------------+
+ Program triage completed | User completed program triage           |
+--------------------------+-----------------------------------------+

Intake statuses
=================

Intake statuses are specific to OTIS.  This means a user has at least seen a program triage rule page.

+--------------------------+---------------------------------------------+
| Name                     | Definition                                  |
+==========================+=============================================+
| Bypass intake            | the user completed the program's triage     |
|                          | rules and was taken to the bypass intake    |
|                          | message. They did not complete an intake    |
|                          | application.                                |
+--------------------------+---------------------------------------------+
| Diverted                 | user completed the program's triage rules   |
|                          | and was diverted because of legal issue.    |
+--------------------------+---------------------------------------------+
| Offered                  | user completed the program's triage rules   |
|                          | and was offered intake. The user did not    |
|                          | start the intake form.                      |
+--------------------------+---------------------------------------------+
| Started                  | user completed the program's triage rules,  |
|                          | was offered intake and completed at least   |
|                          | one page in the intake form but did not     |
|                          | complete the application.                   |
+--------------------------+---------------------------------------------+
| Eligible                 | user completed the program's triage rules,  |
|                          | began intake and finished any financial     |
|                          | information screen, was eligible but did    |
|                          | not complete the contact information.       |
+--------------------------+---------------------------------------------+
| Over-income              | user completed the program's triage rules,  | 
|                          | was offered intake, completed an intake     |
|                          | application but was over-income.            |
+--------------------------+---------------------------------------------+
| Over-asset               | user completed the program's triage rules,  | 
|                          | was offered intake, completed an intake     |
|                          | application but was over-asset (and not     |
|                          | over-income).                               |
+--------------------------+---------------------------------------------+
| Etransferred             | user completed the program's triage rules,  |
|                          | offered intake, completed an intake         |
|                          | application that was eTransferred to the    | 
|                          | program.                                    |
+--------------------------+---------------------------------------------+

Last Screen Viewed
===================

We try to capture the last page the user viewed.  For users who are presented with the
modal and do not continue on, they will see a last page viewed that corresponds to the
piece of content.  These are represented by /node/[nid], /es/node/[nid], /legal-information/[node-title],
or /informacion-legal/[node-title].

If the user gets past Get Legal Help and into OTIS, the last screen viewed is captured as:

+--------------------------+----------------------------------------------+
| Name                     |  Description                                 |
+==========================+==============================================+
| Program triage           | User completed program triage.  They may     |
|                          | have been diverted, offered intake, or       |
|                          | bypassed intake                              |
+--------------------------+----------------------------------------------+
| Intake start             | User submitted the demographic page only     |
+--------------------------+----------------------------------------------+
| Intake household         | User submitted their household size info     |
+--------------------------+----------------------------------------------+
| Income questions,        | User submitted the form for the specific     |
| Expense questions,       | category and may have exited as started,     |
| Asset questions          | eligible, over-income, over-asset based on   |
|                          | program configuration.                       |
+--------------------------+----------------------------------------------+
| Address form             | User completed address form.  This will only |
|                          | show if the user then fails to wait for the  |
|                          | Please call confirm                          |
+--------------------------+----------------------------------------------+
| Callback form            | Issue is set to "we call client"; user did   |
|                          | not select a callback time                   |
+--------------------------+----------------------------------------------+
| Callback confirm         | Successful e-transfer; we call client        |
+--------------------------+----------------------------------------------+
| Please call              | Successful e-transfer; client calls          |
+--------------------------+----------------------------------------------+
| Failure Screen           | Initial e-transfer failed; system retries    |
|                          | for next several hours                       |
+--------------------------+----------------------------------------------+


 
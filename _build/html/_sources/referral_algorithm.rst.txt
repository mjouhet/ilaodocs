===================
Referral algorithm
===================

The referral algorithm relies on a complex database query designed.

Non-bar referral services
==========================
The system checks for non-bar referrals separately from bar referrals and the results the user sees is based initially on their income status:

* Users who are not overincome are given 3 referrals based on the way the service is provided (phone, in person, and online).
* Users who are overincome are given 2 referrals: phone and in person. The only online referral is ILAO's Legal Answers, which is income limited.

Mandatory criteria
-------------------
In order for a service to be a referral for a user it must match the user's query on:

* legal issue
* zip code
* income; for users who are over-income, they only get results that are not marked "free to low-income users"

In addition:
* the service must be open
* the service must provide direct representation
* the service must not be accepting online intakes.
 
Scoring of referrals
---------------------
A score is generated for each referral. All services start with a score of 0.

* .5 is added to the score when the service specifically is limited to a population the user belongs to.
* The score is increased by x/3000 where x is the service's documented capacity.
* The score is increased by .25 if the service has regular weekly hours

For all  referrals:

* Referrals with less than regular weekly hours are only returned if they are open wihtin the next 7 days.  For example, a clinic open only on the 1st of the month will be excluded from being returns between the 2nd and 23rd of the month.

For in-person referrals:

* when multiple walk-in clinics are available, the nearest one geographically is returned.


Bar referrals
===============
Bar referrals are hard-coded as follows:

* Cook county returns the ISBA and CBA referral services
* All other counties return the ISBA and potentially the county bar association.

Other referral programs in our database are never returned.




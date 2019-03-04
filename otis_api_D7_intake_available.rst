==========================
Intake available "API"
==========================

This code is primarily found in the oas_triage_user.intake_available.inc file:

* If the user is overincome, it looks for intake settings where the user is in population where income is waived or where there is no income limit
* If the user is not overincome, it looks for intake settings first where the user matches on a population and if there is no match, looks for intake settings with no population restrictions

If there are any intake settings that match, the system then checks for matching triage rules (see oas_triage_user_get_triage_rules function).


.. note: Special case:  we need to make sure we have the right problem code to check for.  In the current site, there are instances where the legal issue is stored in different ways.  The oas_triage_user_get_child_problem function returns the best child function.


Prioritization when there are multiple intake options
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
=================================
Get Legal Help APIs for Drupal 7
=================================
Technically, we do not have true APIs in Drupal 7 and the functionality and interface are entwined. 

Browser Interfaces
===================

The interfaces that power the front-end of Get Legal Help:

* Get Legal Help form
* Triage issues forms
* Triage rules (webform nodes)
* Intake application form (multi-page form)
* Exit screens


Triage Rules
===============
Triage rules are webforms wrapped in a content type.


Exit Screens
================
There are 4 template files that get populated when the user reaches an exit:

* oas--bypass.tpl.php is our bypass template file for users who start OTIS and then get told to call instead of applying online.
* oas--please-call.tpl.php is our "Please call" template file for users who complete intake and are directed to call
* oas--we-call-you.tpl.php is our "We call you" template file for users who complete intake and have scheduled a callback.
* oas--referrals.tpl.php is our template file for users who are given referrals to content, forms, and/or organizations.



 
 

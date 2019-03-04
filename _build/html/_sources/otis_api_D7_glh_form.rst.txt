=======================================
Initial Evaluation APIs
=======================================


Get Legal Help form
====================
The Get Legal Help form is a piece of the OAS triage user entity.  
That entity is based in the oas_triage_user module and extended via features for ILAO.

Our `custom configuration <https://www.illinoislegalaid.org/admin/structure/triage/manage/oas_triage_user/fields>`_ includes:

+------------------------------+-------------+-------------------------------------+
|  Field                       | Type        |  Purpose                            |
+==============================+=============+=====================================+
|  oas_triage_help_type        | List        | Captures whether the user wants     |
|                              |             | a lawyer, forms, or content         |
+------------------------------+-------------+-------------------------------------+
| field_triage_search          | Text        | Captures search input from the user |
|                              |             | describing their problem.  Supports |
|                              |             | auto-suggest of legal issue terms   |
+------------------------------+-------------+-------------------------------------+
| field_triage_problem         | Term        | Lowest level term related to the    |
| (legal issues taxonomy       | reference   | user's search                       |
+------------------------------+-------------+-------------------------------------+
| field_limited_populations    | Term        | Determines if the user falls into a |
| (intake population           | reference   | population served by a specific     |
| taxonomy)                    |             | service                             |
+------------------------------+-------------+-------------------------------------+
| field_triage_problem_history | Term        | Captures the drill down of user's   |
| (legal issues taxonomy)      | reference   | legal problem                       |
+------------------------------+-------------+-------------------------------------+
| field_opt_in_sms             | Boolean     | Has the user opted in for SMS?      |
+------------------------------+-------------+-------------------------------------+
| field_mobile_phone           | Text        | User's mobile number                |
+------------------------------+-------------+-------------------------------------+
         

Data collection
-----------------
The get legal help form (oas_triage_user_edit_form, altered via ilao_intake_settings.module) collects initial input data:

* Displays a description of Get Legal Help
* User's zip code (prepopulated if user is logged in)
* Household size
* Whether the user is likely over-income.  This looks up a value based on the provided household size:
  
  * The function can be found at oas_triage_user_get_maximum_income r
  * Relies on the ilao_oas_income_standard module to get the `current federal poverty levels <https://www.illinoislegalaid.org/admin/structure/ilao_oas_income_standards>`_.
  * Calculates the monthly poverty level, multiplies by 3.5 (350%) and adds 500
  * Rounds to the nearest lowest $1000.  For example, if the maximum monthly income is $5,300, the system will return $5000. 

* Whether the user is a member of a special population.  This data comes from the limited population taxonomy

Form submission
-----------------
When the form is submitted, the system:

* Creates a session variable that stores the household size (in $_SESSION['oas'])
* Creates an oas_triage_user entity which stores:

   * Current time stamp
   * User's ID if known
   * Last screen viewed of "get-legal-help"
   * The user's zip code
   * The county associated with the zip code
   * The state associated with the state
   
* Routes the user to initial results

Initial Results Evaluation
============================
The logic for the initial results is in the oas_triage_user.evaluate_triage.inc file.

Initial step
--------------

* set the legal issue (as field_triage_problem) if the user picked a legal term using autosuggest
* routes the user to the top of the `get legal help tree <https://www.illinoislegalaid.org/get-legal-help/triage-start>`_ to pick from the top 8 topics if their search can't be matched.
* routes the user into the legal issues triage tree if the user didn't pick a low enough category.
* routes the user to a list of legal issues that match their search term if they didn't pick from the taxonomy and there are matches. 
* routes the user to results if the user picked a bottom level category

Results
---------
Once the user ends up at the lowest level category for their problem, the system determines the appropriate results.
This is in the oas_triage_user_determine_resources function.

* If the user is only seeking content and forms, they are directed to the referrals page.
* If the user is seeking a lawyer in any combination, the system evaluates to see if `online intake is available </otis_api_DR_intake_available.html>`_.




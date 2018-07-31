======================================
OTIS Database Tables & Relationships
======================================

The documentation below references specific queries and tables generated for reporting purposes and the relationship between them.

OAS Triage User
=================
Fields
--------

+-------------------------+-------------------------------------+
|  Field                  |  Notes                              |
+=========================+=====================================+
| triage_id               | Unique ID for the session           |
+-------------------------+-------------------------------------+
| uid                     | If logged in, the user's ID         |
+-------------------------+-------------------------------------+
| age                     | Intake only                         |
+-------------------------+-------------------------------------+
| triage_changed          | Time of last triage activity        |
+-------------------------+-------------------------------------+
| citizenship             | Intake only if asked                |
+-------------------------+-------------------------------------+
| county                  | Intake, computed from zip code      |
+-------------------------+-------------------------------------+
| triage_started          | Time Get Legal Help form submitted  |
+-------------------------+-------------------------------------+
| ethnicity               | Intake only if asked                |
+-------------------------+-------------------------------------+
| gender                  | Intake only if asked                |
+-------------------------+-------------------------------------+
| household_adults        | Intake only                         |
+-------------------------+-------------------------------------+
| household_children      | Intake only                         |
+-------------------------+-------------------------------------+
| household_size          | May be empty if user skipped        |
|                         | on Get Legal Help form              |
+-------------------------+-------------------------------------+
| immigrant_status        | Intake only if asked                |
+-------------------------+-------------------------------------+
| intake_started          | Time of first intake page saved     |
+-------------------------+-------------------------------------+
| intake_changed          | Time of last intake activity        |
+-------------------------+-------------------------------------+
| last_screen_viewed      | Last page viewed by user            |
|                         | If node/number user declined modal  |
+-------------------------+-------------------------------------+
| marital_status          | Intake only if asked                |
+-------------------------+-------------------------------------+
| primary_language        | Intake only if asked                |
+-------------------------+-------------------------------------+
| overincome              | null = user skipped on GLH form     |
|                         | 0 = No                              |
|                         | 1 = Yes (Triage only)               |
|                         | 2= Over income (Intake only)        |
|                         | 3 = Over asset (Intake only)        |
+-------------------------+-------------------------------------+
| race                    | Intake only if asked                |
+-------------------------+-------------------------------------+
| state                   | Intake only; computed from zip      |
+-------------------------+-------------------------------------+
| total_income            | Intake only if asked; computed      |
+-------------------------+-------------------------------------+
| total_assets            | Intake only if asked; computed      |
+-------------------------+-------------------------------------+
| total_expenses          | Intake only if asked; computed      |
+-------------------------+-------------------------------------+
| triage_status           | Last triage status reached          |
+-------------------------+-------------------------------------+
| zip_code                | User's zip code                     |
+-------------------------+-------------------------------------+
| service_id              | Node ID of the service              |
+-------------------------+-------------------------------------+
| intake_settings_id      | ID the intake settings used         |
+-------------------------+-------------------------------------+

Triage user legal issue
-------------------------

The legal issue is the lowest level term in the legal issue taxonomy.

+--------------------------+-------------------------------------+
|  Field                   |   Notes                             |
+==========================+=====================================+
|  triage_id               |  Triage ID of the session           |
+--------------------------+-------------------------------------+
|  legal_problem           | Term ID from legal issues           |
+--------------------------+-------------------------------------+
|  legal_problem_name      | Name of the legal issue             |
+--------------------------+-------------------------------------+

OAS Intake Settings
====================

Intake settings is the key data structure for a program's intake parameters for a service
or subset of legal issues within a service. 

These settings power the intake section once the user completes ILAO's triage
and program triage without getting diverted.

All Yes/No values are stored as 0 (No) or 1 (Yes).


+--------------------------+-----------------------------------------+
|  Field                   |   Notes                                 |
+==========================+=========================================+
|  service                 |  Name of the service tied to settings   |
+--------------------------+-----------------------------------------+
|  service_id              | Node ID of the service                  |
+--------------------------+-----------------------------------------+
|  intake_settings_id      | Intake settings unique id               |
+--------------------------+-----------------------------------------+
|  name                    |  Name of the intake settings            |
+--------------------------+-----------------------------------------+
|  allow_prisoners         | Yes/No if people in jail can apply      |
+--------------------------+-----------------------------------------+
|  apply_asset_limit       | Yes/No                                  |
+--------------------------+-----------------------------------------+
|  apply_income_limit      | Yes/No                                  |
+--------------------------+-----------------------------------------+
|  callback_number         | Phone number for callbacks              |
+--------------------------+-----------------------------------------+
|  callback_type           | We call client or client calls          |
+--------------------------+-----------------------------------------+
|  last_updated            | Time of last update to these settings   |
+--------------------------+-----------------------------------------+
|  collect_citizenship     | Yes/No to ask for citizenship           |
+--------------------------+-----------------------------------------+
|  collect_country         | Yes/No to ask for country of origin     |
+--------------------------+-----------------------------------------+
|  collect_language        | Yes/No to ask for primary language      |
+--------------------------+-----------------------------------------+
|  collect_gender          | Yes/No to ask for gender                |
+--------------------------+-----------------------------------------+
|  collect_race            |  Yes/No to ask for user's race          |
+--------------------------+-----------------------------------------+
|  collect_ethnicity       | Yes/No to ask for user's ethnicity      |
+--------------------------+-----------------------------------------+
|  collect_income          | Yes/No to ask for income information    |
+--------------------------+-----------------------------------------+
|  collect_assets          | Yes/No to ask user for assets           |
+--------------------------+-----------------------------------------+
|  collect_expenses        | Yes/No to ask for expense info          |
+--------------------------+-----------------------------------------+
|  created                 | Time of intake settings created         |
+--------------------------+-----------------------------------------+
|  enabled                 | Are these settings active?              |
+--------------------------+-----------------------------------------+
|  intake_limit            | Max number of intakes; 0 = unlimited    |
+--------------------------+-----------------------------------------+
|  maximum_allowed_income  | Maximum percent of allowed income       |
+--------------------------+-----------------------------------------+
|  maximum_allowed_assets  | Dollar amount of allowed assets         |
+--------------------------+-----------------------------------------+
|  maximum_callbacks       | Maximum number of callbacks that can be |
|  _per_slot               | scheduled for a particular hour slot    |
+--------------------------+-----------------------------------------+
|  minimum_minor_age       | Lowest allowed age to apply online      |
|                          | Default is 18; minimum allowed is 13    |
+--------------------------+-----------------------------------------+
|  minimum_senior_age      | Lowest age to be considered a senior    |
+--------------------------+-----------------------------------------+
| reset_limit_frequency    | How often intake limits are reset       |
+--------------------------+-----------------------------------------+
|  personal_exemption      | Dollar amount of personal property that |
|  _amount                 | is deducted from assets before          |
|                          | calculating asset eligibility.          |
+--------------------------+-----------------------------------------+
| income_standard          |  Income standard to apply               |
+--------------------------+-----------------------------------------+
| geographic_reach         | Indicates whether intake settings are   |
|                          | limited at the city or county level or  |
|                          | are statewide.                          |
+--------------------------+-----------------------------------------+

Intake settings & Geographic Eligibility
-----------------------------------------
Programs can set intake settings to be available to the same geographic
region as the associated service or they can limit intake to a different
region.

The `three queries <otis_queries.html#queries-for-geographic-reach>`_ under geographic reach can be used to generate the
list of zip codes for services by geographic_reach.

Financial Categories
-----------------------
If the program wants to collect income, assets, and/or expenses, we then ask them to pick
from a list of financial categories in each class.  This information is stores in its
own tables. 

Assets
^^^^^^^

+--------------------------+-----------------------------------------+
|  Field                   |   Notes                                 |
+==========================+=========================================+
|  intake_settings_id      | Intake settings id                      |
+--------------------------+-----------------------------------------+
|  intake_settings_name    | Name of the intake settings             |
+--------------------------+-----------------------------------------+
|  financial_id            | ID of the asset                         |
+--------------------------+-----------------------------------------+
|  asset                   | Name of the asset to be collected       |
+--------------------------+-----------------------------------------+
|  subcategory             | Grouping the asset belongs to when      |
|                          | displayed to the user.                  |
+--------------------------+-----------------------------------------+

Income
^^^^^^^

+--------------------------+-----------------------------------------+
|  Field                   |   Notes                                 |
+==========================+=========================================+
|  intake_settings_id      | Intake settings id                      |
+--------------------------+-----------------------------------------+
|  intake_settings_name    | Name of the intake settings             |
+--------------------------+-----------------------------------------+
|  financial_id            | ID of the income item                   |
+--------------------------+-----------------------------------------+
|  income                  | Name of the income item to be collected |
+--------------------------+-----------------------------------------+
|  subcategory             | Grouping the income item belongs to     |
|                          | when displayed to the user.             |
+--------------------------+-----------------------------------------+

Expenses
^^^^^^^^^

+--------------------------+-----------------------------------------+
|  Field                   |   Notes                                 |
+==========================+=========================================+
|  intake_settings_id      | Intake settings id                      |
+--------------------------+-----------------------------------------+
|  intake_settings_name    | Name of the intake settings             |
+--------------------------+-----------------------------------------+
|  financial_id            | ID of the expense                       |
+--------------------------+-----------------------------------------+
|  expense                 | Name of the expense to be collected     |
+--------------------------+-----------------------------------------+
|  subcategory             | Grouping the expense belongs to         |
|                          | when displayed to the user.             |
+--------------------------+-----------------------------------------+

Population Parameters
----------------------




Location Services
==================    




.. code:: sql

  LECT field_data_oas_asset_categories.entity_id as intake_settings_id, oas_asset_categories_target_id as financial_id, oas_intake_settings.name as settings_name, ilao_oas_financial_category.name as asset FROM field_data_oas_asset_categories inner join oas_intake_settings on oas_intake_settings.intake_settings_id = field_data_oas_asset_categories.entity_id inner join ilao_oas_financial_category on ilao_oas_financial_category.ilao_oas_financial_category_id = oas_asset_categories_target_id order by oas_intake_settings.intake_settings_id, delta
================================
OTIS-related queries
================================

Legal issues with any triage rules
===================================
Returns all triage rules with their associated taxonomy terms.

.. code-block:: sql

   Select distinct taxonomy_entity_index.entity_id,
   taxonomy_entity_index.tid,
   taxonomy_term_data.name,
   field_data_title_field.title_field_value
   from taxonomy_entity_index
   inner join taxonomy_term_data
   on taxonomy_entity_index.tid = taxonomy_term_data.tid
   inner join node on nid = taxonomy_entity_index.entity_id
   inner join field_data_title_field on field_data_title_field.entity_id = nid
   where taxonomy_entity_index.bundle = 'triage_rules'
   and field_name = 'field_legal_issues'

Legal issues with published triage rules
=========================================
.. code-block:: sql

   SELECT DISTINCT taxonomy_entity_index.entity_id,
   taxonomy_entity_index.tid,
   taxonomy_term_data.name,
   field_data_title_field.title_field_value
   from taxonomy_entity_index
   inner join taxonomy_term_data
   on taxonomy_entity_index.tid = taxonomy_term_data.tid
   inner join node on nid = taxonomy_entity_index.entity_id
   inner join field_data_title_field
   on field_data_title_field.entity_id = nid
   where taxonomy_entity_index.bundle = 'triage_rules'
   AND field_name = 'field_legal_issues' 
   AND node.status = 1

Legal issues with no triage rules, regardless of level
=======================================================
The tid not in clause excludes terms under About Lawyers, Courts & Hearings, and Practice Resources.

.. code-block:: sql

   SELECT tid, name from taxonomy_term_data where tid not in
   (SELECT taxonomy_entity_index.tid from taxonomy_entity_index
   inner join taxonomy_term_data
   on taxonomy_entity_index.tid = taxonomy_term_data.tid
   inner join node on nid = taxonomy_entity_index.entity_id
   inner join field_data_title_field on field_data_title_field.entity_id = nid
   WHERE taxonomy_entity_index.bundle = 'triage_rules'
   AND field_name = 'field_legal_issues' and node.status = 1)
   AND vid = 61 and tid not in
   (517836, 517841, 517846, 524176, 524156, 524161, 524221,
   524171, 524211, 524181, 524236, 524306, 517851, 517856,
   517866, 517896, 517906, 517901, 522986, 517911, 517861,
   517921, 517936, 517926, 517916, 517931, 517941, 517946,
   522646, 517951, 517956, 517966, 517976, 517961, 517971,
    517871, 517876, 517886, 517891, 517881) 


Legal issues with no triage rules, lowest level terms only
==========================================================
The tid not in clause excludes terms under About Lawyers, Courts & Hearings, and Practice Resources. Only taxonomy terms that are not parent terms are included.  This means only those terms that are the lowest level terms are returned.

.. code-block:: sql

   SELECT tid, name from taxonomy_term_data where tid not in
   (SELECT taxonomy_entity_index.tid from taxonomy_entity_index
   inner join taxonomy_term_data
   on taxonomy_entity_index.tid = taxonomy_term_data.tid
   inner join node on nid = taxonomy_entity_index.entity_id
   inner join field_data_title_field on field_data_title_field.entity_id = nid
   WHERE taxonomy_entity_index.bundle = 'triage_rules'
   AND field_name = 'field_legal_issues' and node.status = 1)
   AND vid = 61 and tid not in
   (517836, 517841, 517846, 524176, 524156, 524161, 524221,
   524171, 524211, 524181, 524236, 524306, 517851, 517856,
   517866, 517896, 517906, 517901, 522986, 517911, 517861,
   517921, 517936, 517926, 517916, 517931, 517941, 517946,
   522646, 517951, 517956, 517966, 517976, 517961, 517971,
   517871, 517876, 517886, 517891, 517881) 
   and tid not in (SELECT parent from taxonomy_term_hierarchy)
   
Queries for Geographic Reach
-------------------------------   

Gets all intake settings by zip code when coded by city
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..  code-block:: sql

    SELECT tid, name, entity_id from field_data_field_cities 
    inner join taxonomy_term_data
    where entity_type = 'oas_intake_settings' and tid in
    (SELECT tid from taxonomy_term_hierarchy
     where parent = field_data_field_cities.field_cities_target_id)

Gets all intake settings by zip code when coded to counties
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: sql

   SELECT tid, name, entity_id
   FROM field_data_field_counties
   INNER JOIN  taxonomy_term_data
   WHERE  entity_type = 'oas_intake_settings' AND  tid in
   (SELECT tid from taxonomy_term_hierarchy where parent in 
   (Select tid from taxonomy_term_hierarchy where parent in
   (Select tid from taxonomy_term_data
    where tid = field_data_field_counties.field_counties_target_id)))

Gets all Illinois zip codes; use for statewide intake settings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


.. code-block:: sql

   Select * from taxonomy_term_hierarchy 
   inner join taxonomy_term_data
   on taxonomy_term_data.tid = taxonomy_term_hierarchy.tid
   WHERE parent in
   (select tid from taxonomy_term_hierarchy
      where parent in
      (select tid from taxonomy_term_hierarchy where parent =
      (Select tid from taxonomy_term_data where name = 'Illinois')))
   and taxonomy_term_data.vid = 76

Intake settings by geographic reach
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: sql

   SELECT intake_settings_id,
   CASE
    WHEN intake_settings_id in (Select entity_id from field_data_field_statewide where entity_type = 'oas_intake_settings' and field_data_field_statewide.field_statewide_value = 1) THEN 'statewide'
    WHEN intake_settings_id in (Select entity_id from field_data_field_cities where entity_type = 'oas_intake_settings') THEN 'city-limited'
    WHEN intake_settings_id in (Select entity_id from field_data_field_counties where entity_type = 'oas_intake_settings') THEN 'county-limited'
   ELSE 'localized'
  END  
  from oas_intake_settings

Triage User 
================

.. code:: sql

   Select 
   triage_id,
   oas_triage_user.uid, 
   age, 
   from_unixtime(oas_triage_user.changed) as triage_changed,
   citizenship, 
   county,
   from_unixtime(oas_triage_user.created) as triage_started, 
   ethnicity, 
   gender,   
   household_adults, 
   household_children,
   household_size, 
   immigrant_status, 
   from_unixtime(intake_created) as intake_started, 
   from_unixtime(intake_changed) as intake_changed,
   last_screen_viewed, 
   marital_status, 
   overincome, 
   primary_language, 
   race,
   state, 
   total_income, 
   total_expenses,
   total_assets, 
   triage_status, 
   zip_code,
   oas_intake_settings.entity_id as 'service', 
   oas_intake_settings.intake_settings_id 
   from oas_triage_user
   left outer join oas_intake_settings 
   on oas_intake_settings.intake_settings_id = oas_triage_user.intake_organization
   where oas_triage_user.uid not in (2, 4486, 4646, 1) 
   and oas_triage_user.created > 1470064821

Triage user legal problem
---------------------------

.. code:: sql

   Select triage_id,
   CASE
   WHEN triage_id in (Select entity_id from field_data_field_triage_problem_history
     where entity_type = 'oas_triage_user' order by delta desc) THEN 
     (Select field_data_field_triage_problem_history.field_triage_problem_history_tid 
      from field_data_field_triage_problem_history where entity_type = 'oas_triage_user' order by delta desc LIMIT 1)
   ELSE
    (Select field_data_field_triage_problem.field_triage_problem_tid from 
     field_data_field_triage_problem where entity_type = 'oas_triage_user' limit 1)
   END   
   as legal_problem,
   CASE
   WHEN triage_id in (Select entity_id from field_data_field_triage_problem_history
    where entity_type = 'oas_triage_user' order by delta desc) THEN 
   (Select name from taxonomy_term_data where tid = (SELECT field_data_field_triage_problem_history.field_triage_problem_history_tid from field_data_field_triage_problem_history where entity_type = 'oas_triage_user' order by delta desc LIMIT 1))
   ELSE
    (Select name from taxonomy_term_data where tid =
    (Select field_data_field_triage_problem.field_triage_problem_tid from 
     field_data_field_triage_problem where entity_type = 'oas_triage_user' limit 1))
   END   
   as legal_problem_name
   from oas_triage_user
   where oas_triage_user.uid not in (2, 4486, 4646, 1) 
   and oas_triage_user.created > 1470064821
   
   
Intake Settings
==================

.. code:: sql

   Select title as service, 
   oas_intake_settings.entity_id as service_id, 
   intake_settings_id, 
   oas_intake_settings.name,
   allow_prisoners,
   apply_asset_limit,
   apply_income_limit,
   callback_number,
   callback_type,
   from_unixtime(oas_intake_settings.changed) as 'last_updated',
   collect_assets,
   collect_citizenship, 
   collect_country,  
   collect_language,
   collect_gender,
   collect_race,
   collect_ethnicity,
   collect_income,
   collect_assets,
   collect_expenses,
   collect_expenses_over_income,
   from_unixtime(oas_intake_settings.created) as 'created',
   enabled,
   intake_limit,
   maximum_allowed_income,  
   maximum_allowed_assets,
   maximum_callbacks_per_slot,
   minimum_minor_age,
   minimum_senior_age,
   personal_exemption_amount,
   CASE
    WHEN intake_limit != 0 THEN
    CASE
      WHEN reset_limit_frequency = 1 THEN 'per day'
      WHEN reset_limit_frequency = 7 THEN 'per week'
      WHEN reset_limit_frequency = 30 THEN 'per month'
    END
    ELSE 'unlimited'
  END 
  as reset_limit_frequency,
  CASE
    WHEN intake_settings_id in 
     (Select entity_id from field_data_field_statewide 
     where entity_type = 'oas_intake_settings' 
     and field_data_field_statewide.field_statewide_value = 1) 
     THEN 'statewide'
    WHEN intake_settings_id in 
     (Select entity_id from field_data_field_cities 
      where entity_type = 'oas_intake_settings') THEN 'city-limited'
    WHEN intake_settings_id in 
     (Select entity_id from field_data_field_counties 
     where entity_type = 'oas_intake_settings') 
     THEN 'county-limited'
   ELSE 'localized'
   END
  as geographic_reach,
  ilao_oas_income_standard.name as 'income_standard'
  from oas_intake_settings
  inner join node on 
  oas_intake_settings.entity_id = nid
  inner join field_data_oas_income_standard ON
  field_data_oas_income_standard.entity_id = intake_settings_id
  inner join ilao_oas_income_standard on 
  ilao_oas_income_standard.id = 
  field_data_oas_income_standard.oas_income_standard_target_id

Financial Categories per Intake Setting
=========================================

Assets
^^^^^^

.. code:: sql

   SELECT field_data_oas_asset_categories.entity_id as intake_settings_id, 
   oas_intake_settings.name as intake_settings_name, 
   oas_asset_categories_target_id as financial_id, 
   ilao_oas_financial_category.name as asset,
   subcategory 
   FROM field_data_oas_asset_categories 
   inner join oas_intake_settings 
   on oas_intake_settings.intake_settings_id = 
    field_data_oas_asset_categories.entity_id 
   inner join ilao_oas_financial_category 
   on ilao_oas_financial_category.ilao_oas_financial_category_id = 
   oas_asset_categories_target_id 
   order by oas_intake_settings.intake_settings_id, delta

Income
^^^^^^

.. code:: sql

   SELECT field_data_oas_income_categories.entity_id as intake_settings_id, 
   oas_intake_settings.name as intake_settings_name, 
   oas_income_categories_target_id as financial_id, 
   ilao_oas_financial_category.name as income,
   subcategory
   FROM field_data_oas_income_categories 
   inner join oas_intake_settings 
   on oas_intake_settings.intake_settings_id = 
    field_data_oas_income_categories.entity_id 
   inner join ilao_oas_financial_category 
   on ilao_oas_financial_category.ilao_oas_financial_category_id = 
   oas_income_categories_target_id 
   order by oas_intake_settings.intake_settings_id, delta
   
Expenses
^^^^^^^^^

.. code:: sql

   SELECT field_data_oas_expense_categories.entity_id as intake_settings_id, 
   oas_intake_settings.name as intake_settings_name, 
   oas_expense_categories_target_id as financial_id, 
   ilao_oas_financial_category.name as income,
   subcategory
   FROM field_data_oas_expense_categories 
   inner join oas_intake_settings 
   on oas_intake_settings.intake_settings_id = 
    field_data_oas_expense_categories.entity_id 
   inner join ilao_oas_financial_category 
   on ilao_oas_financial_category.ilao_oas_financial_category_id = 
   oas_expense_categories_target_id 
   order by oas_intake_settings.intake_settings_id, delta

   
   

   
   

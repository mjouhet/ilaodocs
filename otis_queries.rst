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

Gets all intake settings by zip code when coded by city

..  code-block:: sql

    SELECT tid, name, entity_id from field_data_field_cities 
    inner join taxonomy_term_data
    where entity_type = 'oas_intake_settings' and tid in
    (SELECT tid from taxonomy_term_hierarchy
     where parent = field_data_field_cities.field_cities_target_id)

Gets all intake settings by zip code when coded to counties

.. code-block:: sql

   SELECT tid, name, entity_id
   FROM field_data_field_counties
   INNER JOIN  taxonomy_term_data
   WHERE  entity_type = 'oas_intake_settings' AND  tid in
   (SELECT tid from taxonomy_term_hierarchy where parent in 
   (Select tid from taxonomy_term_hierarchy where parent in
   (Select tid from taxonomy_term_data
    where tid = field_data_field_counties.field_counties_target_id)))

All IL zip codes

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

Intake settings by location setting

.. code-block:: sql

   SELECT intake_settings_id,
   CASE
    WHEN intake_settings_id in (Select entity_id from field_data_field_statewide where entity_type = 'oas_intake_settings' and field_data_field_statewide.field_statewide_value = 1) THEN 'statewide'
    WHEN intake_settings_id in (Select entity_id from field_data_field_cities where entity_type = 'oas_intake_settings') THEN 'city-limited'
    WHEN intake_settings_id in (Select entity_id from field_data_field_counties where entity_type = 'oas_intake_settings') THEN 'county-limited'
   ELSE 'localized'
  END  
  from oas_intake_settings



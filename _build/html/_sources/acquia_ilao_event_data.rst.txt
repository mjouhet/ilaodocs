=====================================
ILAO Specific Event data
=====================================

An event is a specific action taken on the website.  An event may be:

* viewing a page
* completing a form
* printing a page
* anything that can be tracked as an event in Google tag manager

`Documentation <https://docs.acquia.com/lift/omni/event/>`_ related to default data collected by Acquia for events

Content types
===============
We have multiple content types on our website (legal content, basic pages, blog posts, etc). 
Within legal content, we also have a primary content format (Easy form, video, text, etc). 

Within Acquia Lift, we capture content type so that we can segment based on both pieces of data.

This table outlines how we store our content types in Lift.  For pages that are not nodes, the content type may be empty.

+-------------------+-----------------------------------------+
| Acquia Lift value | Description                             |
+===================+=========================================+
| event             | calendar event (event content type)     |
+-------------------+-----------------------------------------+
| job               | job posting                             |
+-------------------+-----------------------------------------+
| internship        | internship/fellowship content type      |
+-------------------+-----------------------------------------+
| legal video       | legal content with a primary content    |
|                   | type of "video"                         |
+-------------------+-----------------------------------------+
| legal easy form   | legal content with a primary content    |
|                   | type of "easy form"                     |
+-------------------+-----------------------------------------+
| legal how-to      | legal content with a primary content    |
|                   | type of "how-to"                        |
+-------------------+-----------------------------------------+ 
| legal how-to      | legal content with a primary content    |
|                   | type of "how-to"                        |
+-------------------+-----------------------------------------+ 
| legal guide       | legal content with a primary content    |
|                   | type of "guide"                         |
+-------------------+-----------------------------------------+ 
| legal form        | legal content with a primary content    |
|                   | type of "static form", "form-download   |
|                   | or "form-link"                          |
+-------------------+-----------------------------------------+
| legal lawyer      | ADRM content                            |
| manual            |                                         |
+-------------------+-----------------------------------------+
| legal iicle       | IICLE content                           |
+-------------------+-----------------------------------------+
| legal portal      | Portal main page content                |
+-------------------+-----------------------------------------+
| legal blog        | Blog content type with a blog category  |
|                   | of law changes or Legal Q&A             |
+-------------------+-----------------------------------------+
| ilao blog         | Blog post that is not a legal blog      |
+-------------------+-----------------------------------------+
| faq               | Site FAQ content type                   |
+-------------------+-----------------------------------------+
| ilao page         | Basic page content type                 |
+-------------------+-----------------------------------------+
| triage rules      | Triage rule content type                |
+-------------------+-----------------------------------------+
| organization      | Organization page                       |
+-------------------+-----------------------------------------+
| Location          | Location page                           |
+-------------------+-----------------------------------------+
| service           | Service page                            |
+-------------------+-----------------------------------------+

Content Section
================


Content Keywords
=================


Custom fields
==============
We can have up to 50 event user-defined fields.

+------------------+-------------------------------------------+
| Field            | Definition                                |
+==================+===========================================+
| event_udf1       | Audience.  Options are:                   |
|                  |                                           |
|                  | * All (default)                           |
|                  | * attorney (ADRM, advanced content)       |
|                  | * pro bono (restricted to pro bono)       |
|                  | * advocate (IICLE, restricted to advocate |
|                  | * law student                             |
|                  |                                           |
|                  | Calendar events and site FAQs have        |
|                  | audience settings that are mapped         | 
+------------------+-------------------------------------------+
| event_udf2       | Language.  The current language           |
+------------------+-------------------------------------------+
| event_udf3       | Service type (for locations/services)     |
|                  | Options are:                              |
|                  |                                           |
|                  | * Direct Hotline                          |
|                  | * Direct Advice desk                      |
|                  | * Direct Service                          |
|                  | * Legal information                       |
|                  | * Lawyer referral                         |
|                  | * Legal self-help center                  |
|                  | * Other                                   |
|                  |                                           |
+------------------+-------------------------------------------+
| event_udf4       | Legal position (neutral, plaintiff,       |
|                  | defendant                                 |
+------------------+-------------------------------------------+




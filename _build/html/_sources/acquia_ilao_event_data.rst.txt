=====================================
ILAO Specific Event data
=====================================

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
| event_udf1       | Audience.  Options are: All, public,      |
|                  | advocate, pro bono, attorney, law student |
|                  | The default is All                        |
|                  | except:                                   |
|                  | ADRM content, advanced is attorney        |
|                  | Restricted legal content is 1 of:         |
|                  | attorney, advocate, pro bono              | 
|                  | Calendar events have audience field       |
|                  | Site FAQS have access restrictions        | 
+------------------+-------------------------------------------+
| event_udf2       | Language.  The current language           |
+------------------+-------------------------------------------+
| event_udf3       | Service type (for locations/services)     |
|                  | Options are:                              |
|                  | Direct Hotline                            |
|                  | Direct Advice desk                        |
|                  | Direct Service                            |
|                  | Legal information                         |
|                  | Lawyer referral                           |
|                  | Legal self-help center                    |
|                  | Other                                     |
+------------------+-------------------------------------------+
| event_udf4       | Legal position (neutral, plaintiff,       |
|                  | defendant                                 |
+------------------+-------------------------------------------+




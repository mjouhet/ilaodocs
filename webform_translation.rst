=============================
Enabling webform translation
=============================

To enable translation of a webform, there are 2 steps required.

First, you must create a translation of the node.

* Click on Translate
* Click Add next to the language that does not have a translation
* Save the page

This is required because we do not allow fallback translations so the translation must exist.

Second, go to the webform tab:

* Click on the Localization by string translation section title
* Check the expose webform component strings suitable for translation

.. image:: /assets/webform-translation.png

Depending on the content type:

* for triage rules, the webform components are sent to Lingotek for translation
* for all other webforms, the translations must be done manually using the Translate interface.  The easiest way to do these is with POedit:

  * Go to `Strings <https://www.illinoislegalaid.org/admin/config/regional/translate/i18n_string>`_ and check "Webform localization" and uncheck Clean up left over strings
  * Go to Export and select "Webform localization" under export translation.  This will download a PO file with all of the strings in all webforms.
  * Open the file in poedit.
  * Find the strings related to the webform(s) you created
  * Translate and save
  * Go to  `Import <https://www.illinoislegalaid.org/admin/config/regional/translate/import>`_ and load the file, check "Webform localization" and mode should be set to "existing string and the plural format are kept; only new strings are added" and import the file.

.. image:: /assets/webform-strings.png 

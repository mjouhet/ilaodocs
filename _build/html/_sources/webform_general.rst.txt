================
Webforms
================

This documentation refers to webforms generally.  We use webforms in 3 content types:

* Webforms. Tthese are standalone pieces of content or are embedded in types of legal content as blocks.
* Triage rules. These are tied into the Get Legal Help platforms
* Surveys.  These are tied into the SMS survey platform.

To create a webform:

* Create your node
* Click on the webform tab
* Add your form components.
* Add any conditionals
* Configure form settings

Form components
================

.. toctree::

   webform_textfield
   webform_select

Summary
-------
 * Text fields. The user can enter one line of text.  Examples: first name.
 * Text areas.  Multiple lines of text.  Examples: Describe your situation.
 * Hidden.  Not exposed to users but passed in the form.  Examples: end point to direct the user to a specific page
 * Markup or message. Text that is displayed to users with no field for them to enter information.  Example: alert texts.
 * Select options.  Asks a question with checkboxes, radio buttons, or select list.  Examples:  Which of these apply to you with list of options, What country are you in? with list of countries
 * Number: Text fields that validates that the value entered is a number.
 * Date: Includes a date picker to select a specific date.
 * Email:  Text fields that validates user input as an email.
 * File: Allows users to upload a file attachment to their webform
 
.. note:: Not all form components are available on every content type.  The Yes/No component only works on the triage rules content type.

Webform conditionals
=====================

You can attach conditions to control the display of form components.

.. warning:: Conditionals control only the display.   Every form component will be included in the results.  Components that do not display are empty.  When creating conditionals, testing for "empty" may be required.

 

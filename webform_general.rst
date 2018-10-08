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

.. figure:: /assets/webform-conditionals.png

   Sample conditional form

With webform conditionals you can set up a condition in the format of IF [form element] [condition] then [another form element] is or isn't [shown, required, or set to]

Supported conditions
---------------------

For selects:

* is 
* is not
* is before
* is not before
* is after
* is not after
* is empty
* is not empty

For textfields, textareas, email, hidden:

* is
* is not
* contains
* does not contain
* begins with
* ends with
* is blank
* is not blank

For dates:

* is on [date formatted as m/d/Y]
* is not on 
* is before
* is on or before
* is after
* is on or after

For numbers:

* is equal to
* is not equal to
* is less than
* is less than or equal to
* is more than
* is more than or equal to
* is blank
* is not blank
 
.. warning:: Conditionals control only the display.   Every form component will be included in the results.  Components that do not display are empty/blank.  When creating conditionals, testing for "is not empty" or "is not blank" may be required.

Supported actions
------------------

* Is shown - this will cause a form element to be displayed
* Is not shown - this will cause a form element to be hidden
* Is required - this will cause a form element to be displayed and be required.  The form element must already be marked required
* Is not required - this will make a form element optiona
* Is set to - this will set a specific value for an element. In triage rules, we use set to to set an endpoint.  For example, if [x is true] then set end point to intake

Customizations
===============
Triage rules as a content type will process a hidden element of "end point" to route a user to intake, bypass intake, or referrals.

For webforms, we have another customization that will handle a hidden element of "end point" to:

* If numeric, redirect the user to a specific node. For example if I set an end point to 119321, it will direct the user to "Post judgement forms" after submitting the form
* If not numeric, it will direct the user to an internal path.  For example, if I set an end point to get-legal-help, it will direct the user to illinoislegalaid.org/get-legal-help.  *Do not include the forward slash at the beginning*
* External links are not currently supported in end points


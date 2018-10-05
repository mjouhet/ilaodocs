========================
Webform Select Options
========================

The webform select options form field type handles all three of the following:
 
* radio buttons (where the user can only choose 1 option)
* checkboxes (where the user can choose more than 1 option)
* select lists (where the user can only choose 1 option)
* listboxes (where the user can choose multiple options)

By default, the select options field wil result in radio buttons.  To get checkboxes, check the Multiple checkbox in the Options section. To get the Select list, do not check multiple but select Listbox in the Display setitngs.  To get a list box, check both Multiple under options and Listbox under Display.

When creating a webform select option, you must:

* Provide a label.  This is displayed to users
* Provide a form key. The default should be fine, but may need edited if duplicated in the form already.
* Optionally provide a description (help text) that displays below the field.
* Set your options

Setting options
================

.. image:: /assets/webform-options.png

Options support 2 characteristics:  a key, which is what is saved in the form submisison, and a value, which is the label displayed to the user.

For best results, check the customize keys option to set your own keys.  Otherwise, the system will create numerical keys for you.  

For example, you may want to set keys of 10, 11, 12 with values of October, November, and December or keys of adult_expungement, juvenile_expungment with labels of "I was charged as an adult" and "I was charged as a juvenile"

Checking the "multiple" checkbox will convert the field to checkboxes vs radio buttons.

Drupal provides a few pre-built lists that you can use instead of your own options for:

* Days of week
* States
* Countries

There is also an option to allow for other in a select list. This will show a text field and allow the user to enter their own option.  The entered option can not be evaluated for in the conditionals however.
 

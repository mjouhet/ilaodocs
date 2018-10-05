======================
Webform textfield
======================
A textfield in a webform is a single line with a maximum of 255 characters.  If you need multiple lines or more characters, use the textarea type.

When adding a textfield, you:

* MUST provide a label
* MUST provide a form key but this is pre-filled automatically and does not usually need changed
* May provide any other additional values:

  * Default value will prepopulate the field with a value and will remain if the user does not change it.  Default value also supports tokens.  Sample tokens may include the current user's username, email address or the current page url.
  * Description will appear below the field as help text

* May provide validation parameters:

  * Is required.  If checked, the user will be required to enter a value.  If a default value is provided, then that will satisfy the requiredness of the field.
  * Is unique.  If checked, the form can not re-use a value used in any previous submission.
  * Maximum length.  Will enforce a length limit.  In no event will the system allow more than 255 characters.
  * Minimum length.  Will enforce a minimum length.  If the field is not required, an empty field is still allowed regardless of this setting.  Example uses: minimum length of 5 for a zip code field.

* May provide display parameters.  Ignore any not listed below.

  * Prefix text before the field.  For example, when asking for a dollar amount, a prefix of $ may be useful.
  * Postfix text after the field.  For example, when asking for a percentage, a postfix of % may be useful.



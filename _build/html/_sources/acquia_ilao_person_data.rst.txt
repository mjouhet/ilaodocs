===============================
ILAO person custom data
===============================

ILAO captures the email address of users as the identity piece.  Email comes from:

  * Mail field for registered users
  * From email fields for anonymous users:

    * Contact us form
    * Online intake contact form
    * Newsletter subscription form
    * Blog subscription form

We can have up to 50 additional user defined variables for "person."  
We have defined the following as additional user-defined variables:

+---------------+-------------------------------------------------+
| Variable name | Definition                                      |
+===============+=================================================+
| person_udf1   | Year born.                                      |
|               | Available for online intake and registered users|
+---------------+-------------------------------------------------+
| person_udf2   | Primary registered user role                    |
|               | Available for registered users only.            |
|               | We store the best role for a user:              |
|               | Intern, if has intern role                      |
|               | Staff if has staff role and not intern          |
|               | All others: advocate, pro bono, law student,    |
|               | navigator, public                               |
+---------------+-------------------------------------------------+
| person_udf3   | User testing status (registered users only      |
+---------------+-------------------------------------------------+
| person_udf4   | Organization/Company/Law school (registered)    |
+---------------+-------------------------------------------------+
| person_udf5   | Content editor role                             |
|               | Indicates whether the user is a SME or has      |
|               | edited a piece of legal content                 |
+---------------+-------------------------------------------------+
| person_udf6   | Organization role                               |
|               | Indicates whether user is org admin, OTIS admin,|
|               | or both.                                        |
+---------------+-------------------------------------------------+



  

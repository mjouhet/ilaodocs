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

UDF 1 to 3 are already in use by the default configuration.

+---------------+-------------------------------------------------+-------------+
| Variable name | Definition                                      | Type and    |
|               |                                                 | Location    |
+===============+=================================================+=============+
| person_udf4   | Organization/Company/Law school (registered)    | String      |
| Company       |                                                 | Profile     |                    
+---------------+-------------------------------------------------+-------------+
| person_udf5   | Content editor role                             | Boolean     |
| Editor        | Indicates whether the user is a SME or has      | Profile     |
|               | edited a piece of legal content                 |             |
+---------------+-------------------------------------------------+-------------+
| person_udf6   | Organization role                               | Comma-list  |
| Organization  | Indicates whether user is org admin, OTIS admin,| Profile     |
| Role          | or both.                                        |             |
+---------------+-------------------------------------------------+-------------+
| person_udf7   | Zip code                                        | String      |
| Zip code      |                                                 | Profile     |
+---------------+-------------------------------------------------+-------------+
| person_udf8   | Gender                                          | String      | 
| Gender        |                                                 | Profile     |
+---------------+-------------------------------------------------+-------------+
| person_udf9   | Populations                                     | Comma-list  |
| Population    |                                                 | Profile     |
| Segments      |                                                 |             |
+---------------+-------------------------------------------------+-------------+
| person_udf10  | Notification preferences                        | Comma-list  |
| Notification  | For logged in users whether they want email/sms | Profile     |
| Preferences   |                                                 |             |
+---------------+-------------------------------------------------+-------------+
| person_udf11  | Year born.                                      | Integer     |
| Year born     | Available for online intake and registered users| Profile     |       
+---------------+-------------------------------------------------+-------------+
| person_udf12  | Primary registered user role                    | String      |
| Primary role  | Available for registered users only.            | Profile     |
|               | We store the best role for a user:              |             |
|               | Intern, if has intern role                      |             |
|               | Staff if has staff role and not intern          |             |
|               | All others: advocate, pro bono, law student,    |             |
|               | navigator, public                               |             |
+---------------+-------------------------------------------------+-------------+
| person_udf13  | User testing status (registered users only      | Boolean     |
| User tester   |                                                 | Profile     |
+---------------+-------------------------------------------------+-------------+
                



  

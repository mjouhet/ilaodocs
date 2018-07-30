===================================
Updating the Google Analytics Data
===================================
To update the Google Analytics data after pulling it, you must run a sql script in it.  To do that, you will need an instance of MySQL.

Create database to work with
=============================
In MySQL, create a database named rec-ga.

Page path data
-------------------------------------

Create a new table named ga_page_path_duration_all_time.  Create 6 columns for the table:

+---------------------+-------------+-----------------+
| Name                | Type        |  Params         |
+=====================+=============+=================+
| row_number          | int         | Auto-increment  |
+---------------------+-------------+-----------------+
| pagepath            | varchar     | Length: 1000    |
+---------------------+-------------+-----------------+
| sessions            | int         |                 |
+---------------------+-------------+-----------------+
| avgsessionduration  | float       |                 |
+---------------------+-------------+-----------------+
| start_date          | date        |                 |
+---------------------+-------------+-----------------+
| end_date            | date        |                 |
+---------------------+-------------+-----------------+

Import the CSV file into this new table:

* Strip out header row from the CSV
* Enusre that start and end dates are formatted as yyyy-mm-dd

Landing page path data
------------------------

Create a new table named ga_landing_page_path_duration_all_time. Create 8 columns for the table:

+---------------------+-------------+-------------+
| Name                | Type        |  Params     |
+=====================+=============+=============+
| landingpagepath     | varchar     | Length: 1000|
+---------------------+-------------+-------------+
| pagepath            | varchar     | Length: 1000|
+---------------------+-------------+-------------+
| secondpagepath      | varchar     | Length: 1000|
+---------------------+-------------+-------------+
| previouspagepath    | varchar     | Length: 1000|
+---------------------+-------------+-------------+
| sessions            | int         |             |
+---------------------+-------------+-------------+
| avgsessionduration  | float       |             |
+---------------------+-------------+-------------+
| start_date          | date        |             |
+---------------------+-------------+-------------+
| end_date            | date        |             |
+---------------------+-------------+-------------+

Import the CSV file into this new table:

* Strip out header row from the CSV
* Enusre that start and end dates are formatted as yyyy-mm-dd

Execute SQL script
====================
Run the ilao_avg_session_duration_recs.sql file by importing it into the database.
 

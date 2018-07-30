=============================
Technical Overview
=============================

This is the code used to generate a static set of recommendations for ILAO web pages
from a snapshot of Google Analytics data, downloaded from the Google Analytics API.
Recommendations are generated from a set of python and SQL scripts based on logic from events and session duration.


The folder structure is as follows:

/rec_csvs   - final recommendations in csv format.

/sql 	    - sql query generating a new set of recommendations based on AVG SESSION DURATION.

/python     - 3 python notebooks for generating recommendations. This includes our final script for recommendations based on EVENTS, and 2 other approaches we tried.

/data 	    - a snapshot of data from Google Analytics and our scrape used in python notebooks. The data that corresponds to the SQL scripts is in a subfolder called /data_for_sql. The data that corresponds to the python scripts is in a subfolder called /data_for_python. You may need to update the file location in the python notebook.

To generate new recommendations, the python notebooks and SQL queries must be run on new data pulled from Google Analytics. The format of this data is described below:


Required to run recommendations for events:
Exports from Google Analytics (Window on our export was Aug 1, 2016 - May 2017)
- Landing page path, event category, event label, total events, sessions with event
- Page path, event category, event label, total events, sessions with event

Table of page URL, page category, and cluster that we pulled from the scrape (This would be static unless new URLs are added).

Required to run recommendations for session duration:
Exports from Google Analytics (Window on our export was Aug 1, 2016 - May 2017)
- Landing page, page path, second page, avg session duration, sessions
- Page path, avg session duration, sessions

Table of page URL, page category, and cluster that we pulled from the scrape (This would be static unless new URLs are added).

========================
Adding non-node pages
========================

To add non-node pages go to `the Apache not-a-node configuration <https://www.illinoislegalaid.org/admin/config/search/apachesolr-nan>`_.

On this page, you'll want to add another item:

..  image:: assets/search-apache-nan.png

Fill in:

* The path to index.  The path should be the url without the https://www.illinoislegalaid.org and should not include the leading /.  Examples include get-legal-help, form-library.
* Set the language to English
* Enter the page title as the Indexed Title
* Enter a page description.  This is what will be shown to users as the snippet in search results
* Enter the time between indexes.  For content-based views, leave this as daily.  For pages that are mostly static (like the Get Legal Help page), weekly or even monthly is okay to use.

Submit the form

It will take a cron run for the pages to start to show up, which is scheduled to run at the top of each hour.

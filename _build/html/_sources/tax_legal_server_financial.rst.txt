=================================
Legal Server Financial Mappings
=================================
The legal server financial mappings taxonomy maps Legal Server financial categories to OTIS financial categories.  The list of terms is made up of those labels that match Legal Server's incoming financial category labels as defined in their `XML lookup <https://iloi.legalserver.org/static/external_xml_intake/lookup.xsd>`_.

Fields
------
For each taxonomy term, there is a:

 * field to map to one or more OTIS financial terms
 * field to enter text to append to case notes.

.. note:: For example, Legal Server accepts an incoming value of "Work-Related Expenses" but OTIS collects those as individual elements for child care, transportation expenses, and other work-related expenses.  In the system, we map those 3 OTIS items to Work-Related Expenses and add notes that say "May include child care, transportation or other work-related expenses."

Permissions
-----------
Only users with the site architect or developer roles may add, edit, or delete terms in this taxonomy.

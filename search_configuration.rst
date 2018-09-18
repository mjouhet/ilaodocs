==========================
Search Configuration
==========================

Drupal Modules
===============
ILAO currently uses an array of Apache Solr modules to construct our site search. 

ILAO’s search is build on Acquia’s Search, which is a Solr-based configuration hosted, managed, and secured by Acquia.  

For Drupal 7, Acquia recommends that we use Apache Solr and does not recommend the use of the Search API module, which is more powerful, when using their search platform. 
When we migrate to Drupal 8, that will change.

Acquia Connector Module
-------------------------
The Acquia connector module is required to connect ILAO’s website to Acquia’s search as it provides the security authentication that is required.

We do not have access to any of the configuration files provided by Acquia’s Solr search including:

* Synonyms
* Spellings 
* Stopwords
* Protected words


Apache Solr Module
-------------------

The Apache Solr module provides the bulk of the configuration options.  
Drupal sites can use either the Apache Solr module OR the Search API module but not both.  

Apache Solr Exclude
---------------------

The Apache Solr Exclude module allows us to exclude nodes from the search index on a per-node basis. 
It adds a field to each node where we can mark “yes, exclude from search” where needed on content types where we have implemented it.  
It is implemented on our website for:

* Legal content
* Basic pages

Apache Solr Multilingual
--------------------------

The Apache Solr multilingual module adds support for multilingual websites.  

Apache Solr Paragraphs
-------------------------

The Apache Solr paragraphs module is needed to accommodate ILAO’s use of the paragraphs module throughout the site.  

FacetAPI
----------

The FacetAPI module is installed but minimally used on ILAO’s website.  

We support the following facets:

* node type


The FacetAPI module would allow us to add filters/facets to searches for most fields in our database.  
Facets can be restricted by roles (for example, allowing only advocate users to filter by last updated date) and by bundle attached to (for example, allowing searches on legal issue only for legal content and not for events).

Apache Solr Views
--------------------
Apache Solr Views allows one to completely configure the search results pages using Views.  This is far superior to the built in search page that is provided by the ApacheSolr module.   

Search Autocomplete
---------------------

The Search Autocomplete module allows us to include an autocomplete feature in our search bar.  
This module allows us to define, either a static list of results  or a view. 
 
We use a search autocomplete view.

Configuration
===============

Basic Settings
---------------

Minimum word length:  3 characters (words with less than 3 characters are ignored)
Logs searches (should disable this)
Translitateration enabled (allows searching of accented and unaccented characters as the same character)

Apache Solr Configuration
---------------------------

Index Configuration
^^^^^^^^^^^^^^^^^^^^

Content types included in search:

* Basic pages
* Blog posts
* Events
* Internships/Fellowships
* Job postings
* Legal content
* Site FAQ
* Volunteer opportunities
* Portal main page (?)


Bias Configuration
^^^^^^^^^^^^^^^^^^^
**Result Biases**
More recently created content gets weighted slightly higher

**Type Biases**
Legal content is weighted slightly heavier with a .2 boost

**Field Biases** 

We use field biases to boost the weight of certain fields as exposed by the Apache Solr module: 

+-------------------------+-----------+
| Field                   | Boost     |
+=========================+===========+
| Title                   |   5       |
+-------------------------+-----------+
| H1 tag                  |   3       |
+-------------------------+-----------+
| H2, H3 tag              |   3       |
+-------------------------+-----------+
| H4 - H6 tag             |   2       |
+-------------------------+-----------+
| EM or strong tags       |   1       |
+-------------------------+-----------+


The following field biases are available but are not currently implemented:

* Full rendered body (to be considered given paragraphs)
* Text in A tags
* Taxonomy term names
* In total or by vocabulary
* Author names
* Extra rendered content or keywords 
* Comments
* Path alias








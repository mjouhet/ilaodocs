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

The FacetAPI module allows us to offer faceted search.  See `Faceted search </search_facet_configuration.html>`_ for more information. 


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

* Attorney manuals
* Basic pages
* Blog posts
* Events
* Internships/Fellowships
* Job postings
* Legal content
* Site FAQ
* Toolboxes and tools



Bias Configuration
^^^^^^^^^^^^^^^^^^^
**Result Biases**
More recently created content gets weighted slightly higher

**Type Biases**
Legal content is weighted slightly heavier with a .2 boost

**Field Biases** 

We use field biases to boost the weight of certain fields as exposed by the Apache Solr module: 

.. note::  Each setting is per language.

+-------------------------+-----------+
| Field                   | Boost     |
+=========================+===========+
| Full rendered content   |   10      |
+-------------------------+-----------+
| Title                   |   12      |
+-------------------------+-----------+
| H1 tag                  |   9       |
+-------------------------+-----------+
| H2, H3 tag              |   8       |
+-------------------------+-----------+
| H4 - H6 tag             |   6       |
+-------------------------+-----------+
| EM or strong tags       |   3       |
+-------------------------+-----------+
| Taxonomy term names     |   1       |
+-------------------------+-----------+
| Extra rendered content  |  .5       |
+-------------------------+-----------+
| Rendered comments       |  .4       |
+-------------------------+-----------+
| Unstemmed path alias    |   .3      |
+-------------------------+-----------+
| Unstemmed title         |   5       |
+-------------------------+-----------+
| Unstemmed teaser        |   2       |
+-------------------------+-----------+


The following field biases are available but are not currently implemented:

* Text in A tags
* Author names


Special content types
^^^^^^^^^^^^^^^^^^^^^^

Views
========

By default, searches only search "content," or nodes.  Views are generally treated as "reports or lists of content" rather than searchable entities.

To that end, we have created a way to index the following pages for Solr to include in its index:

* /form-library
* /get-legal-help/lshc-directory


Files
=========

Files are not indexed separately from nodes in our search configuration.  The full-text of files are included in the search index for the node to which it is attached.

For example, the application PDF for a job posting will never show as a file in the search results, but the full text of that application PDF would be included in the "body" of the job posting node.

 




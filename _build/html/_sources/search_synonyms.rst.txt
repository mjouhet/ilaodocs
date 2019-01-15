=========================
Search synonym taxonomy
=========================

The synonyms module relies on the search synonyms taxonomy.

Adding terms
===============
Add a term by entering the search term as the name and the replacement/expansion in the description.  Then select the synonym type:

* Replace - replaces the search term with the new term. 
* Expand - expands the search term to add an "OR [new term]"

.. note::  
   A replacement will remove the original search term and replace it with a new term.  This is helpful to:
   * fix common typos, for example dvorce => divorce
   * rewrite queries that result in 0 results to something that might get the user what they need; for example "can you take my kids" => dcfs

..note:: 
  An expansion will add new terms to the original search term. This is helpful to:
  * handle advanced stemming; for example guardian => guardian OR guardianship (-ship terms are not easily stemmed like -ed and -ing words)
  * expanding a search term to include both legal jargon and plain language; for example, dissolution => dissolution OR divorce

How it works
==============

First, the system looks for an exact match. If there is an exact match, the system will either expand or replace based on that term's settings.

If there is no exact match, the system strips out stopwords and then loops through each individual remaining word looking for an exact match and replaces or expands those terms. Partial phrase matching is not supported.

.. note::
   For example, the system has taxonomy terms as follows:
   * dissolution => expand to divorce OR dissolution
   * dvorce => replace as divorce
   * can i get a divorce if I am in jail => replace with divorce AND jail
   * difficult spouse => expand to include contested divorce 
   
   The user searches for:
   
   +-------------------------+-----------------------------+
   | Searches for            |  System rewrite             |
   +=========================+=============================+
   | dvorce                  | divorce                     |
   +-------------------------+-----------------------------+
   | can i get a divorce if  | divorce AND jail            |
   | I am in jail            |                             |
   +-------------------------+-----------------------------+
   | can you get divorced    | no changes made             |
   |  from jail              |                             |
   +-------------------------+-----------------------------+
   | can you get a dvorce    | can you get a divorce       |
   +-------------------------+-----------------------------+
   | difficult spouse        | difficult spouse OR         |
   |                         |   uncontested divorce       |
   +-------------------------+-----------------------------+
   | dissolution of marriage | divorce OR dissolution      |
   | with difficult spouse   |   difficult spouse          |
   +-------------------------+-----------------------------+
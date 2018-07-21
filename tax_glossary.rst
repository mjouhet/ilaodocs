=======================
Glossary
=======================
The glossary taxonomy is used by Lexicon to manage our glossary.

.. seealso:: See also .. `Glossary & Lexicon <lc_glossary.html>`_

The glossary also has fields for:

* Related terms:  these can be used to populate "See also" in the Glossary
* Synonyms:  these can be used by Lexicon to refer users to a glossary term when the text is a different term.  For example, if the glossary has a definition for lawyer but the content uses the word attorney.  If attorney is listed as a synonym, the user will see the lawyer definition.

Translation Notes
------------------

The glossary uses a different form of translation management than other terms.  Other taxonomies use the "localize" option which allows for one-to-one translation between English and other languages.  The glossary uses "translate" which allows for different terms per language.  This is required by the Lexicon module.  What this means is that we can have a term in just one language.  For example, we can have "No" in English and a separate glossary term for "No" with a different definition in Spanish.  

Unless they are not English terms, new terms should be added with the language set to "English."  That will then display the "Save and translate" button and the term can then be translated into other languages.

It is easiest to manage the translation of the glossary through the `Drupal Core taxonomy interface <https://www.illinoislegalaid.org/admin/structure/taxonomy/glossary>`_  rather than the taxonomy manager.

On that page, you will see the language selector (with options for language neutral, English, and Spanish) and if set to anything but language neutral, you'll see a Save and Translate button and a Translate tab.




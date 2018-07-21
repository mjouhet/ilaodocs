===========================
Content Format Taxonomy
===========================
The `content format taxonomy <https://www.illinoislegalaid.org/admin/structure/taxonomy_manager/voc/content_category>`_ is used to manage the different types of legal content.  The content format is set automatically by the system.

.. warning::  Do not add new terms to this taxonomy without telling Gwen.  They will not be automatically associated to legal content without a code update.

The content format is added to legal content in the "primary content type" field based on the content blocks used in the piece of content.  The rules for determining primary content type are as follows and once a match is found, the system stops processing (so an article that meets rule 1, no other rules can overwrite it).

The content type is set to:

#. IICLE if it contains an IICLE block
#. Easy form if it contains an automated document block
#. Teach me if it contains a teach me block
#. Guide if it contains a legal bundle block
#. How-to if it contains a process step
#. Form - download if it contains a static form block AND that form has a file attached
#. Form - link if it contains a static form block AND that form has a URL field in it
#. Link - if it contains a link content block
#. File - if it contains a file content block
#. Video - if it contains a video block
#. Text article - if no other rule has fired, it is treated as a text article.

.. note:: These rules stop with the first match.  So an article that contains an IICLE block, a video, and a file will be classified as an IICLE; an article with a video and a text block will be treated as a video.  An article with a process step and a text block would be treated as a How-to but an article with a process step and a legal bundle would be treated as a Guide.

These content formats are then used as labels on the legal information and search results pages.

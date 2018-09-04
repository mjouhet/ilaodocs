=============================
Creating the toolbox portal
=============================

Groups of related toolboxes should be planned to be grouped together in a
single portal. 

There are 2 portal pages that need to be created:

* A page that uses the "main page" portal type.  This will be the initial landing page for the portal. This page can have whatevef page elements the creator wants to include but should not have a toolbox selector form.

* A page that uses the toolbox selector page type.  On this page, you must include a Toolbox Selector Form.  The only element on the form to add is a title.  The rest will be populated by the associated toolboxes.

.. note::

   On production, a staff member needs to update the block configuration so that the blue block does not appear on the portal pages.  This is done by updating the (Mobile) Displays blue block for location & icon and (Desktop) Displays blue block for location & icon to exclude the subdomain and subdomain/* paths (for example, voc and voc/* for the Victim of Crime portal

.. warning::

   While we use the term subdomain, we don't actually want to use subdomains.  For consolidated reporting purposes, we want to use https://www.illinoislegalaid.org/[subdomain] as the primary url.
   

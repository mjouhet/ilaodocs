==========================
Portal content
==========================

What is a portal?
------------------
A portal has a defined structure to bundle a set of related issues together with a common subdomain.

There are three types of portal pages:

+----------------------+-------------------------------+------------------+
|  Page type           |   Description                 | Number per portal|
+======================+===============================+==================+
|  Main                | Home page for the portal      | 1 per portal     |
+----------------------+-------------------------------+------------------+
|  Toolbox selector    | Generates a form to select    | 1 per portal if  |
|                      | toolboxes to work on          | toolboxes used   |
+----------------------+-------------------------------+------------------+
| Sub page             | All other portal pages        | Unlimited        |
+----------------------+-------------------------------+------------------+

Each portal requires:

* A subdomain.  This must be unique to the site and binds the portal pages together.  The subdomain will be set up as https://www.illinoislegalaid.org/[subdomain]
* Page type.  See table above.
* Title.  The page title.
* Meta description.  This is used in our search engine optimization.
* Image, for use in social media.
* Hero image.  

  * The hero image should be 1920x1280.  
  * A title is required.  This appears on the image on portal main pages and should be the same across portal pages within the same portal.
  * A subtitle is required.  This appears beneath the title on the image.  It should also be the same across pages within the same portal.
  
* A primary legal category and legal category.  These helps control where the portal displays within site navigation.
* One or more portal paragraphs.  See the portal components on this page.


Portal components
-------------------

.. toctree::
  :maxdepth: 1

  portal_admin_grid
  portal_admin_timeline
  portal_admin_summary
  portal_admin_webform
  portal_admin_structured_content
  portal_admin_sidebar
  portal_admin_split_column
  portal_admin_toolbox_selector_form

=====================
XML Sitemaps
=====================

Sitemaps are generated using Screaming Frog and loaded into the website with code releases.

Sitemap Names
==============

Sitemaps are named as follows:

 * sitemaps-index.xml contains the list of sitemaps
 * sitemap.xml contains the general English pages sitemap
 * sitemap-en-lc contains English legal content and anything with a /node path
 * sitemap-es contains all of our Spanish pages

Screaming Frog Configurations
==============================

Copies of the configuration files are on the `Team Drive <https://drive.google.com/drive/u/0/folders/1OyLKlkddNqUAW_-Ei-fzlHrE0yJrBtqB?ogsrc=32>`_.

English-lc.seospiderconfig
---------------------------
This configuration will spider English content as follows:

 * anything containing legal-information/
 * anything that begins with /node/

It specifically excludes:

 * anything beginning with /es
 * anything in the user or www paths

ILAO-English-General.seospiderconfig
--------------------------------------
This configuration file spiders English pages other than those indexed by the English-LC configuraiton.

It specifically excludes:

 * anything beginning with es
 * anything in the user or www paths
 * anything cotnaining legal-information
 * anything with /email/ in the path (common for event contact forms)
 * anything with /sites/ in the path (file attachments and the like attached to content but also theme files, Javascript and CSS)
 * anything with /misc/ in the path (used primarily for Javascript)
 * anything with an old legacy fuseaction tag
 * any of the calendar day or month pages beyond the standard /calendar page.  For example, it does not index each month that we've ever had events

Spanish.seospiderconfig
--------------------------
This configuration file spiders Spanish pages.

It specifically includes only:

* pages that contains /es/legal-information
* pages that contain /es/informacion-legal
* pages that contain /es/node.

  

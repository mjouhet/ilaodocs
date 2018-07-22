========================
Google Analytics Events
========================

Form Submissions
-----------------
The following forms are tracked when a user submits them:

* `Get Legal Help <https://www.illinoislegalaid.org/get-legal-help>`_
* Triage starting point (/triage-start)
* `User registration <https://www.illinoislegalaid.org/get-legal-help/triage-start>`_

Form Abandonment
------------------
We track abandonment of the user registration form.

Outbound Links
---------------
We track all outbound links.  The hostname is saved as the event action and the url as the event label.  For example, a link to https://www.lawhelpinteractive.org/form would be saved with an action of lawhelpinteractive.org and the event label would be https://www.lawhelpinteractive.org/form.

File Downloads
----------------
We track all file downloads, whether from our website or directly linked to from our site (for example, if we directly link to a PDF on another site).  URLS that include sites/default are ILAO-hosted files.

Print Intents
--------------
We track print intents.  Print intents occur whenever the user hits the print button or uses control+P, etc.  We refer to these as intents because there is no way to determine if the user actually printed or not.

The print icon on our site is tied to AddThis and is tracked under the AddThis stats.

AddThis Events
---------------
We track usage of the AddThis toolbar that appears on various content pages.  This tracks clicks for:

* printing
* email
* post to Facebook
* share on Twitter
* share on LinkedIn
* share on Google+

YouTube Events
---------------
We have integrated Google Analytics with YouTube so that we can track how users interact with our videos.  We have actions for:

* Playing the video
* Pausing the video
* Exiting the video
* Percentage completion (0%, 25%, 50%, 75%, 90%, and 100%)

The event label is the YouTube ID and title. 

.. note:: As an example, we can see how many users watched the Going to Small Claims Court and how far they got in the image below.

.. image:: assets/youtube-example.png

Page Not Found (404) errors
-----------------------------
We capture Page not found errors.  The event action is the referring URL and the event label is the 404 page.  If the user did not click a link on our website, the event action may be undefined.

  

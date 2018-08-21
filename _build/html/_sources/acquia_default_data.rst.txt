======================================
General data collected by Acquia Lift
======================================

Acquia Lift collects a lot of data automatically for each user that we can segment on.  

Full documentation is available `here <https://docs.acquia.com/lift/profile-mgr/segment/category/>`_.

Client Time and Server Time
=============================
We can segment on users who visit on a specific:

* day of the month
* day of the week
* hour of the day
* month of the year

.. note::
   Example: To get all weekend visitors, I can create a segment with criteria of 
    
    * a client time: day of week of Saturday 
    * a client time: day of week of Sunday
    * set the criteria to "any" to capture users who visit either day
    
The difference between client time and server time is whose time zone is used:

* Our website (server time) is always Central time
* Client time may vary based on their time zone   

.. note::
   Example:  I want to target all users who visit ILAO during business hours. 
   Using server time set to 9am - 5pm, a user in California accessing the site at 7am will be included as it is 9am Server time while that same user would not be counted using client time.
   
   Example: I want to pop up a "Good morning" message to all who visit ILAO between 8am and 12pm.
   A user in NY would see the Good morning if they accessed the site at 1pm Eastern using server time but not if the segment used client time.
   

  
Content History
================
By default, we can segment on keyword count and section count.  

Examples:

.. note::
  
   Example: to get all users who viewed content in the about us section this week, I can create a 
   segment with a category name of "content history: section count" and enter the correct section name,
   and set the time period to past 7 days.
   
   Other time options include: current touch (session), today, last 30 days, last 60 days, last 90 days, last 24 hours
   
Current Location
=================
Location is automatically captured at the following levels:

* City
* State (Region)
* Country
* DMA code

Current System
================
We can segment automatically on the user's:

* Browser (supports options for: Chrome, Firefox, IE, Opera, and other)
* Platform (desktop, laptop, game console, tablet, other)
* System (no look up provided)

Event
=======
By default, we can segment on event count.  For this, we need to:

* Filter on website
* Filter on event
* Filter on time period (current session, today, last [x] days, etc.
* Set the count.  Options include less than, greater than,  equal to, etc.

.. image:: assets/eventcount.png

External campaign
===================
We can create segments based on the standard Google analytics external campaign parameters below:

* utm_source
* utm_medium
* utm_term
* utm_content
* utm_campaign


Page Content
===================
We can create segments based on:

* Article keywords
* Content section
* Content title
* Page type
* Page URL
* Persona

Person Properties
==================

* Anonymous (yes/no)
* Days since last visit
* Do not track (yes/no)
* Engagement score
* Favorite content section (defined as "most visited content section")
* Favorite content type
* Favorite keyword
* First time visitor (yes/no)
* Persona

Person Ranking
===================

* Article keywords
* Content section
* Content type
* Engagement score
* Events
* Persona
* Platform

.. notes::
   For example, maybe we create a segment for users who more often use a desktop over 
   other platforms or we create a segment where users view video content frequently.



Touch
===================
Touch is the current session.  We can create segments based on the current touch:

* Engagement score
* Number of page views
* Duration
* Duration in seconds

Visit Source
===================
We can segment based on where the user came from:

* Domain
* Referrer domain
* Search engine
* Search terms (note:  Google typically no longer provides these)
* URL: first webpage that the visitor accessed on our website




============================
Toolboxes
============================

Toolbox structure
-------------------

* Portal main page:  a container that holds grid of toolboxes associated with a specific legal issue.  Additional content may also be included as sub pages.

* Portal main page with a toolbox selector form.  For portals that contain more than one toolbox, users need to be able to pick which one they want to start with.

* Toolbox:  a container that holds one or more tools designed to address a set of related legal issues.  Toolboxes should be able to fit within one level 2 legal issue. 

* Tools:  a content type that drives a user through a single process.  The process does not have to be linear. 

* Tool pages:  this is the content type for each page in a tool.  Each page represents either a step in the process or a decision point. 

.. Note::  As an example, a user who has had their drivers license revoked may have lost their license for any number of reasons (DUI, back child support, unpaid parking tickets), each with its own process to get the license back.  The toolbox would be "Getting my Drivers License back" and it would contain tools for "I lost my license because of a DUI", "I lost my license because of unpaid child support" and "I lost my license due to unpaid parking tickets."  Within each of these tools are a set of pages to guide the user through the steps (for example, an overview step, a fill out your forms step, a file your forms step, a do you have a court date scheduled? decision point which can then direct the user to a "Going to court" step.

To create a portal for toolboxes:

* Create a portal main page with type "main page."  This is the main portal page.
* Create a portal main page with type "toolbox selector."  This is the evaluator form for portals that have multiple toolboxes.

Toolbox components 
----------------------

.. toctree::
   :maxdepth: 2

   toolbox_portal.rst
   toolbox_admin.rst
   tool_admin.rst
   tool_steps_admin.rst
   toolboxes_user_interactions.rst
   toolbox_reporting.rst


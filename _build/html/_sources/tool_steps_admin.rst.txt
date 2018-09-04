==========================
Tool Step Content Type
==========================

The tool step is the most granular page in the Toolbox framework.  Tool steps are either:

* a discrete step in the process
* a decision point

A tool step should contain:

* A title
* A yes/no as to whether the step is always required.  If the step is not always required, an explanation of when the step is/is not required must be provided.
* A step type.  This is the main body of the page and should be limited to one per page. A step type would be one of the following:

  * Webform
  * Single form
  * Multiple form
  * Process step

* Optionally, one or more tool step components.  These include:
  
  * Callout
  * Key terms component
  * Short answer component
  
* Tickler settings.  This allows us to set reminders via SMS and/or email.  Each tickler must include:

  * Trigger date.  This is either [x] days from the completion timestamp of the previous step or [x] days from the completion of the current timestamp.
  * An SMS message.  This will get sent to users who have opted in to SMS based on the trigger date.
  * An email message, with subject and body.  This will get sent to users who have opted in to email notifications based on the trigger date.

* An indication if this is the last step in the process.
* Whether to include a learn more component

Step Types
=============

Process Step
-------------

The basic step type is the **process step**.  This is similar to the process step used in legal content.  

A tool step should **never** have more than one process step. 

.. figure:: assets/toolbox-process-step.png

Webform
---------

The webform option allows you to embed an existing webform into the page to support basic branching within the tool.

Fill out forms (single)
------------------------

.. warning:: Because of field sharing, this will technically allow you to add more than one form.  **Don't**.  The page will render badly if you do.  Use the multiple form if you need more than one required form.


..figure:: assets/toolbox-single-form.png

Fill out forms (multiple)
--------------------------



Tool Step Components
=======================



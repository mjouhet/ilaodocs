==========================
Tool Step Content Type
==========================

The tool step is the most granular page in the Toolbox framework.  Tool steps are either:

* a discrete step in the process
* a decision point

Required Elements
-------------------
The following are required for each step in a tool:

* A title
* A yes/no as to whether the step is always required.  If the step is not always required, an explanation of when the step is/is not required must be provided.
* A step type.  This is the main body of the page and should be limited to one per page. A step type would be one of the following:
* An indication if this is the last step in the process.
* Whether to include a learn more component

Step Types
^^^^^^^^^^^^
The system supports 4 step types:

  * Webform
  * Single form information
  * Multiple form information
  * Text

Optional Elements
--------------------

In addition to providing the main step, we have options for:

Page components
^^^^^^^^^^^^^^^^

Page components include:
   
   * Callout
   * Key terms component
   * Short answer component
   * Portal CTA
   * Portal CTA/image
 
Contact Tickler
^^^^^^^^^^^^^^^^^^
The contact tickler is an optional component that allows us to set up reminders.

A tool step may have multiple ticklers.  Each tickler must include:

* Trigger date.  This is either [x] days from the completion timestamp of the previous step or [x] days from the completion of the current timestamp.
* An SMS message.  This will get sent to users who have opted in to SMS based on the trigger date.
* An email message, with subject and body.  This will get sent to users who have opted in to email notifications based on the trigger date.




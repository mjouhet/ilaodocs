======================
Toolbox Content Type
======================

Toolboxes are attached to portals and tools are attached to toolboxes. 

The primary purpose of the toolbox content type is to allow a user to pick from the tools associated with a toolbox that match their problem. 
 A toolbox page can also provide additional information to the user.

A toolbox must contain:

* A title.  The system will automatically add "Let's focus" to the page title.
* A reference to an existing portal.  **Create the portal page first**
* A content description, limited to 200 characters for use on the website.
* A meta description, limited to 300 characters for use on social media and in SERPs
* Purpose description, selector form label, and overall level of effort.  These are used in a webform on the portal page to help the user select which toolboxes in a portal apply to them.

   * Purpose description - text that displays on the webform results page.  Purpose descriptions should begin with "Getting your [x] will help you by [y]"
   * Overall level of effort - easy, medium or hard.  The guideline here is how long it takes and whether a court appearance is required.  Select "easy" if the user can complete most of the issues in 1-3 days; select "medium" if the issues generally don't require a hearing and can be completed in 7-14 days; select "hard" if the issues generally require a hearing or take longer than 14 days to complete.
   * Selector form label - this appears on the webform itself next to a checkbox for the user to pick.
   
* A yes/no to encourage the user to seek legal help.  This will display a standard block encouraging the user to use Get Legal Help.  Defaults to yes when the overall level of effort is hard.
* Page components.  On a toolbox page, we can add block-styled components similar to those used on portal content including:

  * Portal layout webform
  * Portal layout sidebar
  * Portal layout split column

.. figure:: assets/r2w_purpose_description.png

The image above displays the purpose description and level of effort on the evaluator confirmation page.

.. figure:: assets/r2w_evaluator.png

The image above is the evaluator form for the Ready to Work portal.  Each toolbox in the portal is represented by a single checkbox and label.  The label is pulled from the Selector form label.


======================
Legal Issue Taxonomy
======================

The `legal issue taxonomy <https://www.illinoislegalaid.org/admin/structure/taxonomy_manager/voc/legal_issues>`_ is the heart of ILAO's information architecture and defines the vocabulary we use to describe a user's legal problem and tie that legal problem back to resources within our products.  

The legal issue taxonomy is used to:
 * Tag legal content, ADRM, portal pages to substantive terms down to lowest possible level
 * Tag triage rules and referral services to the legal topics that the programs handle to any level
 * Tag blog posts to a level 1 or level 2 term
 * Provide the front-end structure for the legal information drill-down
 * Provide a front-end user interface for classifying user's legal issues for Get Legal Help
 * Provide two custom use cases for About Lawyers and Practice Resources

The legal issue taxonomy should not be used to describe a resource's:
 * content type
 * format
 * audience

Structure
------------
.. image:: assets/legal-issues-taxonomy.png

The taxonomy has 11 top level headings.  9 of these are used in the main legal information  navigation:
 * Court & Hearings
 * Family & Safety
 * House & Apartment
 * Money & Debt
 * Business & Work
 * School & Education
 * Citizens & Immigration
 * Health & Benefits
 * Crime & Traffic

The remaining 2 are special use cases:  About Lawyers and Practice Resources.

About Lawyers
^^^^^^^^^^^^^^
About Lawyers is a special legal issue taxonomy term that is used exclusively to populate an About Lawyers block on the Get Legal Help pages.

Practice Resources
^^^^^^^^^^^^^^^^^^^^
This taxonomy term was added to allow us to create the practice resources page.  Some of the topics (professional responisbility, working with clients, lawyering skills) are substantive. Other terms are designed to "hold" specific types of information:

  * Forms that are restricted to lawyers (Forms for Lawyers)
  * IICLE smartbooks
  * MCLE onDemand (video content that has MCLE available)  

.. warning:: We will redo the practice resources section in fall 2018 and the specific types of information will be removed from the taxonomy and additional data points will allow us to capture that information.

Fields within the Legal Issues Taxonomy
----------------------------------------
There are a few fields associated with the taxonomy.  Note that fields **are not translatable**.

* Use in autosuggest - this is a yes/no field that allows us to exclude terms from the Get Legal Help autosuggest lookup
* Alternatives - this field is used to add additional words that can be used to match against if the user types in the Get Legal Help auto suggest.  For example, car repo is an alternative to A repossessed car to accommodate users who start typing car first.
* Image - this is used currently for level 1 and 2 headings to associate an image with the term for use in the legal information pages and eUpdates.
* Top content - used in the top level categories to select 3 pieces of content to display on the main `legal information <https://www.illinoislegalaid.org/legal-information>`_ page.

Tagging Implications
----------------------
On legal content and portal content, tagging happens at the lowest level term.  The system then automatically tags everything above it.  For example, Applying for food stamps is a child of each of the following and those terms are automatically included when I check "Applying for food stamps" in the legal issues taxonomy:

* Money & Debt
* Unpaid bills
* Food and cash benefits
* Getting food stamps
* Health & Benefits (food and cash benefits is a 2nd level term here and a 3rd level term for Money & Debt)

On location services and triage rules, child terms are selected automatically but parents are not.  For example, using the same Applying for Food stamps term, if I select that no other terms would be selected automatically since it is the lowest level term.  However, if I selected "Getting food stamps," then all of the child terms, Applying for food stamps, Getting an answer on my food stamps application, being denied food stamps, another food stamps application issue, would be selected automatically.  This is too allow for more granular tagging of referral information than what is needed for legal information.


Usage
-------
Within Legal Information
^^^^^^^^^^^^^^^^^^^^^^^^^
Legal content displays based on legal issue in four contexts:
  
  * On top level heading pages (for example, `Family & Safety <https://www.illinoislegalaid.org/legal-information/family-safety>`_), when it is one of the three most popular pieces of content. 
  * On subcategroy pages (for example, `Divorce <https://www.illinoislegalaid.org/legal-information/divorce>`_)
  * On related content blocks, when the legal content is tagged to the exact same lowest level term as the page being viewed
  * On related form blocks, when the legal content is tagged to the exact same lowest level term as the page being viewed.

**Examples**
An article tagged to  Family & Safety -> Divorce -> Custody & Parenting -> Child custody -> Getting custody:
  
  * will appear on Family & Safety on the Divorce card if it is one of the 3 most popular articles
  * will appear on the Divorce page
  * will appear as a related article on other Getting custody content
  * will not appear as a related article on Changing custody content (a sibling term to Getting custody)

.. Note:: In this example, the article will also appear on the Child Custody card on the Family & Safety page if popular enough because the taxonomy is **polyhierarchical** and some terms appear in multiple places. It will also appear on the Family & Safety -> Child custody page. Child custody is a term directly under Family & Safety and is a child term under Divorce -> Custody & Parenting 

An article tagged to Family & Safety -> Safety from abuse or assault -> Restraining or protective orders -> Getting an order of protection (which is also replicated under Crime & Traffic):

  * will appear on Family & Safety and Crime & Traffic if it is one of the 3 most popular articles in those top level
  * will appear on the Family & Safety -> Safety from abuse or assault page
  * will appear on the Crime & Traffic -> Safety from abuse or assault page

Within Get Legal Help
^^^^^^^^^^^^^^^^^^^^^
The legal issues taxonomy powers Get Legal Help as much as it does the Legal Information section. The "what is your problem?" look up uses a subset of the legal issues taxonomy.  It strips out any term that is not marked "Yes" in the "Use in autosuggest" field.  

.. note:: We use the "Use in autosuggest" field to exclude terms like "another food stamps issue" or "about lawyers" from appearing in the what is your problem? lookup.

.. image:: assets/get-legal-help-drilldown.png

It is also used to power the drilldown if the user types or selects a term that can not be matched to a lowest-level term.  Get Legal Help requires the user to get to the lowest level.  It then uses the user's selected issue to route them through triage to intake and referrals.


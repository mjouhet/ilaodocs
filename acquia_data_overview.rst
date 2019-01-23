==============================
Profile Data Overview
==============================

At its core, Acquia Lift stores profiles using a persistent tracking cookie.  We unify these cookies using an email address.  Email addresses are captured from:

* when the user registers and/or logs in.  
* when the user completes an OTIS application and we capture their email
* when the user signs up for a newsletter or blog notification on our About ILAO pages

At the "person" level, we collect and store the following:

* the user's email, if known
* if the user is logged in, their primary role on the website.  Because our website allows users to have multiple roles, the primary role is selected based on the highest of intern, staff, legal aid, navigator, law student, pro bono, public.  Using this hierarchy:

   * a user with both intern and staff roles will be treated as "intern"
   * a user with the staff and legal aid role will be treated as "staff"
   * a user with the legal aid and pro bono roles will be treated as "legal aid"
 
* whether the user is a content editor or not.  This is true or false
* gender, if provided in the user registration form or via OTIS (if collected)
* year born, if provided in the user registration form or via OTIS
* notification preferences, if provided in the user registration form.  Captures whether the user likes email, SMS, or no notifications
* whether the user is signed up to be a user tester in the user registration form
* Favorite content section (this is from the `Content section <https://www.illinoislegalaid.org/admin/structure/taxonomy_manager/voc/content_section>`_ taxonomy.
* Favorite content type (this is the machine name from Drupal of the content type the user has viewed.  Content types include legal_content, toolbox, toolbox_tool, toolbox_tool_step, article (for blog posts), page (for basic page) etc.
* Favorite keyword (this is from the `Content keyword <https://www.illinoislegalaid.org/admin/structure/taxonomy_manager/voc/content_keywords>`_ taxonomy.
* Engagement score (currently each content view increases the engagement score by 1)
* Whether they are a new or returning user
* Whether they are logged in or not
 
At a session ("touch") level:

* their postal code
* referring url
* referrer domain
* country
* state (region)
* city
* geolocation (latitude and longitude)
* IP address
* Operating system
* Platform (desktop, mobile)
* Browser
* Session duration (touch duration in seconds)

At an event level:

For content views (pages):

* If they matched an existing segment
* Referrer
* Page url accessed
* Language of the page
* Legal position for legal content (plaintiff, defendant, neutral)
* Content title
* Content section (if mapped)
* Page type (node page)
* Content type (legal_content, article, etc)
* Content keyword (if mapped)
* Content audience (if mapped); events, IICLE and restricted content will have audience values.

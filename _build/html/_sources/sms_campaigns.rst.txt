============================
SMS Campaigns
============================

Campaigns are groupings of SMS keywords that are configured to return a specific message when received.  

For example, our renters' rights campaign had keyword for rent, lease, and other terms related to landlord/tenant law.

When a user texts ILAO's number a keyword the system:

* First processes out any potential survey responses to determine that it is a campaign keyword
* Looks for a matching keyword; if the keyword is found, it returns the built-in response
* If no keyword is found, it returns the error message, as configured on the website in the SMS configuration.

.. note:: Sample error message: That keyword was not found. It may be an auto correct issue. Please try again. Or go to IllinoisLegalAid.org 24/7 for legal help. 

Restricted keywords
====================

The following keywords can never be used in campaigns because they have special usage in SMS generally:
* STOP
* STOPALL
* UNSUBSCRIBE
* CANCEL
* END
* QUIT
* START
* YES
* UNSTOP
* HELP
* INFO 

Campaign keywords should never be numbers.

Campaign Keywords
===================

Campaign keywords:

* be single words or phrases without spaces (for example secdep, rent)
* are not case sensitive (secdep is the same as SECDEP, SecDep, etc)
* may return a custom string or legal content 





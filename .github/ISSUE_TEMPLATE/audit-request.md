---
name: Audit Request
about: Suggest a project to audit
title: ''
labels: ''
assignees: Zyther

---

AUDIT REQUEST:

# Project Meta

* PROJECT NAME -- $PROJECT_NAME
* PROJECT BITCLOUT URL -- $PROJECT_BITCLOUT_URL
* PROJECT_EXTERNAL_URL -- $PROJECT_EXTERNAL_URL
* PROJECT TYPE[S]  -- $PROJECT_TYPES
  * (?) List all types that apply: 
      * $WEB_APPLICATION
      * $CHROME_EXTENSION
      * $NATIVE_APPLICATION_COMPILED_DESKTOP
      * $NATIVE_APPLICATION_COMPILED_MOBILE_IOS[or ANDROID]
      * $AUTH_TYPE_[ IDENTITY|| SELF_SIGN || OTHER || NONE ]

* AUTHOR/REPRESENTATIVE NAME -- $AUTHOR_OR_REP_NAME
* AUTHOR/REPRESENTATIVE PROJECT AFFILIATION -- $AUTHOR_OR_REP_AFFILIATION
* AUTHOR/REPRESENTATIVE BITCLOUT URL -- $AUTHOR_OR_REP_URL


# Project Detail
`<< explain the project, and where your bitclout user touchpoints are >>`

# Auth Implementation
* Do you need bitclout user data? Y/N

* If yes, describe how you authorize users, or describe where your bitclout backend data is coming from 

* Any other means of authenticating clients? (OAuth/SAML/SSO, AD,  Other) 
If yes, describe


## Identity (ID, self signing, etc)
* Do you use BitClout Identity? 
Y/N (if N skip this section

* Access level, and describe usage as much as possible (stored locally, saved in own app backend) 

# AM I SELF SIGNING?
Yes/No -- if yes, would you be willing to guarantee private key info is not stored in log, telemetry, or otherwise accessible outside of normal, authorized application usage by a user?

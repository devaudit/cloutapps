# Clout Cast

* [$Clout_Cast on bitclout](https://bitclout.com/u/Clout_Cast) 
* https://cloutcast.io
---
* 1. [TL;DR](#TLDR)
* 2. [Auditor Edtails](#AuditorEdtails)
* 3. [Synopsis](#Synopsis)
* 4. [Legitimacy](#Legitimacy)
	* 4.1. [Proof of Ownership](#ProofofOwnership)
	* 4.2. [Proof of Development](#ProofofDevelopment)
	* 4.3. [Technical Overview](#TechnicalOverview)
* 5. [Authentication](#Authentication)
	* 5.1. [Identity](#Identity)
* 6. [Frontend](#Frontend)
* 7. [Infrastructure](#Infrastructure)
* 8. [Additional notes/findigs](#Additionalnotesfindigs)
---
##  1. <a name='TLDR'></a>TL;DR

This project **met** DevAudit's "Trust in Transparency" guidelines. (2020-06-18)

* AUTH_TYPE: Identity Level 2

---
##  2. <a name='AuditorEdtails'></a>Auditor Edtails

@smartalec

Verified By: `!!! NEEDS REVIEW !!!`

---

##  3. <a name='Synopsis'></a>Synopsis

CloutCast.io allows users to promote their content, by paying others to engage with their content. The website operates with a PWA/JS frontend, a serverside middleware component, and a backend API. The website also requires users to sign in using their BitClout account, where it asks for accessLevel 2 from identity.bitclout.com.

##  4. <a name='Legitimacy'></a>Legitimacy

###  4.1. <a name='ProofofOwnership'></a>Proof of Ownership

@JasonDevlin @awesome_dev and @smartalec

###  4.2. <a name='ProofofDevelopment'></a>Proof of Development

* @smartalec and @awesome_dev

    * @smartalec: UI/UX, DevOps, and Infrastructure
    * @awesome_dev: Architecture and Backend

###  4.3. <a name='TechnicalOverview'></a>Technical Overview

* Frontend
    * Compiled Javascript (Svelte)
    * identity payload stored in **localStorage**
        * docs.bitclout.com recommended action: https://docs.bitclout.com/devs/identity-api#login
* Backend
    * .NET Core (C#)
    * MSSQL database
##  5. <a name='Authentication'></a>Authentication
Type - Identity


###  5.1. <a name='Identity'></a>Identity
* Access Level: 2

All activity must be approved by the user. This is the least amount of access a website can ask for.

Explanation from application author:
```
At this time, CloutCast does not use identity to write back to the blockchain, thus we only require accessLevel 2.  
```

##  6. <a name='Frontend'></a>Frontend

* General Overview

CloutCast is a javascript frontend, written in Svelte. It is designed to eventually be a PWA. 

* User Data Handling

CloutCasts stores your username, public key, and any activity you perform on CloutCast. 

* Frontend Data Sources
    * Main Node (api.bitclout.com)
    * API Backend (api.cloutcast.io)
    * CloutCast node (proxied private)



##  7. <a name='Infrastructure'></a>Infrastructure

* General Overview
    * Containerized runtime
    *  Auto Scaling based on volume


* SSL?
    * SSL from frontend, to backend
        * frontend: https://cloutcast.io
        * backend: https://api.cloutcast.io


##  8. <a name='Additionalnotesfindigs'></a>Additional notes/findigs

`!!! NEEDS REVIEW !!! `

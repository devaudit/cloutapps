# CloutMegazord

    $CloutMegazord (https://bitclout.com/u/CloutMegazord)


---
## TL;DR

This project **met** DevAudit's "Trust in Transparency" guidelines.

* AUTH_TYPE: Self-Signing (Custom, Multi)
---


## Audit Details

This brief audit reviewed browser security, and service-level security as it pertained to your BitClout identity. 

It is to be noted that the nature of CloutMegazord is unique in that they themselves aren't signing transactions on behalf of a BitClout you log in with, but rather, CloutMegazord allows groups of individuals to create, and maintain bitclout users as a group, where every individual only has a piece of the puzzle to sign any transaction. 

The use case for this kind of application is ultra-secure shared accounts where one would need multiple users to authorize transactions.




### Legitimacy
Alec Ghazarian, one of the DevAudit auditors, had the pleasure of speaking with the owner of this project, Bogdan (or transhumanist on BitClout) 

#### Proof of Ownership
Verified

#### Proof of Development
Owned, and developed in house, confirmed via github and serverless infrastructure

### Technical Overview

GCP hosted, mostly serverless functionality utilizng GCP CloudRun to facilitate self identity-related tasks. Nothing pertaining to a user's private key is logged server side. 

### Authentication
Identity to log in, self signing shared multi-keys for shared accounts. 


#### Identity

* Access Level: 2
```
 CloutMegazord 
```


#### Self Signing Authentication
If the developer is signing his own calls using the private key, extra precautions should be looked into

* Seed Phrase Managament
```
Is the seed/private key sent to an API? -- no
Is the seed logged anywhere? -- no
Is the seed captured in APM? -- no
Is seed client side ONLY? -- YES
Kept in App? If so, How? -- localStorage, using similar practices that BitClout identity uses
```

#### Additional notes/findings


CloutMegazord is a very unique application to audit, as it creates BitClout accounts that no one user has the full private key to. In addition to this, it is written in such a way that would make it difficult for an engineer to steal one's private key during the transaction signature process, because everyone must show up at the same time, submit their piece of the puzzle. Once all the pieces are together, a GCP Task is executed, with a fulfilled, encrypted private key. 

This key is not stored, or logged, and is proven by GCP access provided to DevAudit. 



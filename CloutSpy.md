# CloutSpy and BitWatcher Security Incident - Trojan

## TOC
1. [Contributors](#Contributors)
2. [Synopsis](#Synopsis)
3. [TL;DR](#TLDR)
4. [Mechanism](#Mechanism)
5. [Decompilation](#Decompilation)
6. [IF YOU ARE AFFECTED](#IFYOUAREAFFECTED)
6. [Known Affected/Compromised Accounts](#AFFECTEDACCOUNTS)

##  1. <a name='Contributors'></a>Contributors
* [@dgsus](https://bitclout.com/u/dgsus)
* [@tijn](https://bitclout.com/u/tijn)
* [@smartalec](https://bitclout.com/u/smartalec)
* [@automatic](https://bitclout.com/u/automatic)
* [@maebeam](https://bitclout.com/u/maebeam)
* [@HPaulson](https://bitclout.com/u/HPaulson)
* [@paulburke](https://bitclout.com/u/paulburke)
* [@Taonaya](https://bitclout.com/u/Taonaya)
* [@ItsAditya](https://bitclout.com/u/ItsAditya)
* [@Dvorkin](https://bitclout.com/u/Dvorkin)
* [@nikmcfly](https://bitclout.com/u/nikmcfly)


##  2. <a name='Synopsis'></a>Synopsis 

This is a security bulletin about CloutSpy and BitWatcher. The following document will reference both of these applications as "CloutSpy/BitWatcher"

CloutSpy/BitWatcher a malicious desktop application that claims to show users various on-chain interactions between other bitclout users that one could specify. The application also **attempts to steal bitclout identity information** by scanning for browser data on the victim's hard disk, and sending them to a specific endpoint. The details of this mechanism are below.  

**If you have used CloutSpy or Bitwatcher at any time in the past, and don't care about the technical details, please [CLICK HERE](https://bitstoday.medium.com/special-edition-xx4-emergency-alert-f78fd54063ec)**

##  3. <a name='TLDR'></a>TL;DR

CloutSpy/BitWatcher scans your local browser's files for BitClout related login data, and upon finding stored login info, attempts to send it to an outpost server.

This means if you've ever used CloutSpy/BitWatcher on a computer that you've also logged into BitClout with, your BitClout account may have been compromised. Please go to the bottom of this page for information on how you can secure your BitClout account.

At this time, it does not appear that CloutSpy/BitWatcher continues to execute in the background after the foreground application is killed. **This note should be taken with caution**

It is to be noted that the repository's codebase itself never contained the trojan's code that was found in the binaries. May this be a reminder that the **only** way you 100% know what is running is if you examine the code, and build it yourself. There are many safe third party applications on BitClout, however one should always be very cautious with their identities in general. 

##  4. <a name='Mechanism'></a>Mechanism

CloutSpy/BitWatcher claims to be an open source project on GitHub, however upon decompiling versions `2.2`, `2.1`, and `2.0` of CloutSpy, (and `2.0` of BitWatcher) one can find an attempt to read files that may contain cookies, and/or localStorage of the most popular browsers, like the Chrome/Chromium suite (Chrome, Chromium, Brave, Edge, etc), FireFox, and Opera. The application iterates through each potential browser installed on the victim's PC, and upon finding specific strings, adds them to a mass payload, and sends a payload to a specific endpoint, `https://en3mfgye4nnl68d.m.pipedream.net`


![Diagram](CloutSpy.png)


```mermaid
sequenceDiagram
  participant 0 as Victim
  participant 1 as CloutSpy/Bitwatcher.exe
  participant 2 as CloutSpy UI
  participant 3 as get_localstorage
  participant 4 as Victim Browser Data on Disk
  participant 5 as 68d.m.pipedream.net

  0->>1: User Executes CloutSpy.exe/BitWatcher.exe
  par [Starts UI]
    1->>2: Get App UI
    2->>1: Show App UI to User
    1->>0: Show UI
  and [Starts Scan Thread]
    1->>3: Start
    3->>4: Scan for BitClout User Data
    4->>5: Send Payload With scan result
  end

```


##  5. <a name='Decompilation'></a>Decompilation

The single binary was created with `PyInstaller`, and was decompiled using `decompyle3`


##  6. <a name='IFYOUAREAFFECTED'></a>IF YOU ARE AFFECTED

If you have ever used CloutSpy/BitWatcher in the past, it is important to follow these instructions: 

* **Delete CloutSpy.exe/BitWatcher.exe**
* Create a new BitClout Account
* Transfer all of your holdings to the new account
* Rename the previous account and reclaim your username on the new account.


## 7. <a name="AFFECTEDACCOUTS"></a>Known Affected/Compromised Accounts

The following accounts are known to have been compromised:

* BC1YLfomjxzbu4eHr3pRWiK1gEX2j5obtxEEwUKRS1zgeNnJdQtt22m
  https://bitclout.com/u/danielwilson
* BC1YLfhcHSJzEAwVS8Msp2DBghkbnL81CmgmsPngaiyyP4JK93terBV
  https://bitclout.com/u/klesh
* BC1YLhVWfCQAiF8K1VqKSmjPETJ2Ptv4QKfv2VJqgS7pQS1i6aCcnxo
  https://bitclout.com/u/syrtsov
* BC1YLhkET4cWsU8MZy2j2xXhkKMfp9dveQ9NkSNQ7U2SVWJ9523278S
  https://bitclout.com/u/bitcloutprice
* BC1YLig7n2p8ZrAmQkSfC7Wri9hSmKuDVHAacHW1eKEg2q2J2iyBs7s
  https://bitclout.com/u/Deaththirst
* BC1YLgK3wLpTWdfXUU9ajKyE8n1f2Wbu6BxxzKRhZMxakQdAnc7hPbg
  https://bitclout.com/u/Football_Clout
* BC1YLhcezyV3Xy8gFbshoaAGuD3AFxuHKQo9LtZped5Ue8YNKKpMB69
  https://bitclout.com/u/Affiliated_Clout
* BC1YLh8AK9WcwmEfiqu4NcAMDWUXLf8wZokeMPmad1mnKrUdn9U7DoG
  https://bitclout.com/u/BitCloutBrothers
* BC1YLhuo698QYqMcAggQ7rV2hypKbxrLnYVmvAr2aKYNLdH4meDc2mG
  https://bitclout.com/u/chalid
* BC1YLiS23747tXn3gEKep8s6TBRmwVqte3bSi82CPuVnrsyf3JQN2iH
  https://bitclout.com/u/adillitto
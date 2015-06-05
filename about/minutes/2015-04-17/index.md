---
title: OpenAFS Foundation Meeting Notes  2015-04-17
nav: [about]
---

## OpenAFS Foundation Meeting Notes  2015-04-17 ##

## In Attendance ##

 Daria Brashear,
 Dave Botsch,
 David Boldt,
 Margarete Ziemer,
 Thomas Keiser,
 Todd DeSantis

## Topics ##

* IRS response on hold
* it is proposed that agenda/meeting notes will be maintained online, Margarete will select a location on the Foundation Website
* pending Microsoft security implementation; Jeff's posting in the open AFS mail group brought to the community's attention that required Microsoft certifications for AFS are anticipated
  + is FUSE an option?
  + this is a fiscal responsibility much larger than OpenAFS has ever had to deal with
  + how can funding on that scale be raised?
* Dave Botsch has offered to contact Roman for PayPal account information.
  Post meeting, Roman responded:
  > I can provide this to anyone, but we do need a way to transfer the password
  > securely.  I could put some kind of encrypted file in the AFS repository
  > with all the various passwords; if anyone has any preferences on the
  > methodology, let me know.
* interest was expressed in establishing the chain of authority from the OpenAFS elders to the Foundation (no specific action item) Post meeting, Roman responded:
  > I believe this essentially rested in me, and to a lesser degree, Daria and Todd.  We disbanded the Elders with the intent of the non-gatekeeper related functions (which were only tangential to the elders) resting with the Foundation.  Daria or Todd, please correct me if you think this understanding is incorrect.
* with respect to the open AFS and Kerberos workshop it was agreed that
  + the Foundation will cooperate with the effort already underway for 2015
  + communications will be opened with the organizers
  + David Boldt took the action item to link to the workshop from the Foundation website (task accomplished)
  + Dave Botsch will draft an email followup to the Foundation's original communication on a conference/workshop.

#### Provided post meeting by Thomas: ####

I was there as well, although my audio connection seemed to be simplex--I tried to say something a few times, but it seemingly went into the ether.

I have a few questions that I couldn't pose on the call:

1) When y'all were referencing fuse, were you talking about the google code project "dokan", as Jason Edgecombe mentioned in his message, or did the conversation pertain to some other user-kernel messaging layer that I'm not privy to?

   Post meeting by Daria:

   > This was the Dokan one.  

2) Given Jeff's reservations about viability of a fully-userspace driver based on a fuse/rdbss substrate, I have serious reservations about proceeding down a purely userland path.  Frankly, this sounds like the open client would be a toy, hence all enterprise deployment would have little choice but to purchase the YFS client, regardless of our investment (please note: I do not intend that as a value judgment, but it is something we need to be crystal clear about).

   Post meeting by Daria:

   > I don't think it's viable, either, but obviously my take is conflicted and thus I've not pushed it

3) Moreover, given Jeff's commentary on Microsoft's motivations, going the FUSE route sounds to me like a quixotic endeavor: Microsoft is going to be strongly disinclined to certify something they consider to be, intrinsically, little more than a backdoor into their kernel file system layer.

   Post meeting by Daria:

   > It's the same as the GPL shim for Linux. A backdoor. The difference is Microsoft could actually sue someone over it.

4) I'm guessing Jeff needs to focus his time and money on compliance for YFS; are we soon going to be in need of contractors to deal with the fully open client's road to compliance?  Or, does Jeff believe he has the time and resources to seek compliance for both the partially closed source, and fully open source redirectors (provided we can help him fund the fully-open variant)?  It would certainly be preferable to leverage the relationships Jeff has cultivated with Microsoft, however we need to establish some level of cooperation and commitment before we can go out and seek donations on his behalf.

5) Fundamentally, is it in the Foundation's best interest to devote a great deal of time, energy, and money into the Windows Server client?  I ask this because we have very limited resources.  What do we consider our role here? Those most affected are large enterprises where test mode Windows clients aren't feasible.  If we take actions proving large enterprises are our core constituency, do we undermine our 501(c)3 argument by acting like a 501(c)6?  I worry that we could become a, debatably unethical, conduit for turning tax deductible donations into a guaranteed YFS income stream (given that competitive bidding is unlikely to uncover any viable competition).

6) There was discussion of a need to do recurring payments for donations.  My girlfriend does major philanthropic gifts for a living.  I cannot agree more strongly.  When it comes to " annual fund" donations, one of the key aspects is engraining habitual donation amongst your community.  As much as we all may hate the near-constant asks, they are an essential tool in the life of any nonprofit.  If we want to succeed, we need to be straightforward--and never sheepish--about our need for money to keep the lights on.

   Post meeting by Daria:

   > My wife is grappling with this for an opera company she works with. I can only concur.

7) Regarding the Elders discussion, I do not understand the motivation to grandfather their decisions.  Given the lack of a record of decision, how could we meaningfully accomplish this, and to what end?  I was under the impression the dissolution of--rather than merger with--the Elders was to side-step exactly these types of ugly, difficult to adjudicate fairly situations...

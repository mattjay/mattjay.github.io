---
layout: post
title: Raising the CSRF Bar
---

For years, we at WhiteHat have been recommending Tokenization as the number one protection from Cross Site Request Forgery (CSRF). Just having a token is not enough, of course, as it must be cryptographically strong, significantly random, and properly validated on the server. Can't stress that last point enough as the first thing I try when I see a CSRF token is to empty the value out and see if the form submit is accepted as valid.

Historically the bar for "good enough" when it comes to CSRF tokens was if the token was changed at least per session.

**For example:** A user logs in and a token is generated & attached to their authenticated session. That token is used for that user for all sensitive/admininstrative forms that are to be protected against CSRF. As long as when the user is logged out and logged back in they received a new token and the old one was invalidated.

**Not anymore.**

Thanks to some fellow security researchers who are much smarter than I when it comes to crypto chops, (Angelo Prado, Neal Harris, and Yoel Gluck), and their latest attack on SSL which they dubbed [BREACH](http://threatpost.com/breach-compression-attack-steals-https-secrets-in-under-30-seconds).

BREACH is an attack on HTTP Response compression, like gzip, which are *very* popular. Make your giant HTTP responses smaller which makes them faster for your user? No brainer. Well now thanks to the BREACH attack which within around 1000 requests can do pull out sensitive information that is encrypted by SSL from HTTP Responses. Sensitive information such as... **CSRF Tokens!**

The bar must be raised. We now no longer allow Tokens to stay the same for an entire session if response compression is enabled. In order to combat this CSRF Tokens need to be generated for every request/response. This way they can not be stolen with 1000 requests where it stays the same.

###TL;DR
* Old "good enough" - CSRF Tokens unique per session
* BREACH ([BlackHat 2013](https://www.youtube.com/watch?v=CoNKarq1IYA))
* New "good enough" - CSRF Tokens **must** be unique per request if HTTP Response compression is being used.

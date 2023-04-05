---
layout: post
title: iOS 9 TLS Requirements & nginx
image: /images/iphone_vulnu.png
---

This week with the release of iOS 9, Apple has introduced some new requirements for their TLS standards under the label [App Transport Security (ATS)](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/). After going down this rabbit hole a bit for a few days to make sure we were playing nice with the new rules, I figured I'd give a lessons learned for anybody who stumbles across this. I'm using nginx in all of my examples.

## 1 - The server must support at least Transport Layer Security (TLS) protocol version 1.2
No brainer. All modern browsers now support TLS1.2 and so should you. TLS 1.3 has me drooling but TLS 1.2 will help protect from many of the transport layer attacks you've read about in the past few years. The obvious one is POODLE which caused everybody to race to disable SSLv3.

The tricky part to remember here is that even if you support TLS 1.2 but don't explicitly disallow SSLv3, you're susceptible to the POODLE attack which forces a browser to downgrade its connection.

We've gone ahead and stopped allowing TLS 1.0 during this revision in anticipation of future issues and it really doesn't knock off any browser support that we already claim to not support. Our nginx config for this requirement:

```
ssl_protocols TLSv1.1 TLSv1.2;
```

## 2 - Certificates must be signed using a SHA256 or better signature hash algorithm, with either a 2048 bit or greater RSA key or a 256 bit or greater Elliptic-Curve (ECC) key
This one was a sticky one for me for a few reasons. First, and hardest to figure out, was the SHA256 or better signature hash algorithm. Thought this was straightforward, and had my certificate setup properly from our CA but kept failing on this issue in production. Our testing tool (nscurl) was passing in qa though and maybe you've run into this too if you're a Cloudflare customer. Cloudflare only supports SHA1 even for their paying customers. The fix? Go and upload your own certificate as a "Custom Certificate" in the Cloudflare interface. This alone moved me from an A to an A+ on the [SSL Labs](https://www.ssllabs.com/ssltest/) test.

The 2048 bit key part was a bit of a tweak as well. In nginx a small line change will help support this as the default is a 1024 bit key.

First you need to generate a 2048 bit key:

```
openssl dhparam -out dhparam2048.pem 2048
```

Then, tell nginx to use the new key

```
ssl_dhparam /path/to/dhparam2048.pem;
```

## 3 - Invalid certificates result in a hard failure and no connection
Don't be gentle. If it doesn't smell right, drop it.

## 4- Only allow ciphers that provide perfect forward secrecy
This one looks ugly but will up your transport security game a ton. Not only creating a proper priority list of modern cipher suites but explicitly disallowing weak ones is very important. You'll also need to prefer server ciphers in order for forward secrecy to be in place properly.

```
ssl_prefer_server_ciphers on;

ssl_ciphers 'ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES256-GCM-SHA384:DHE-RSA-AES128-GCM-SHA256:DHE-DSS-AES128-GCM-SHA256:kEDH+AESGCM:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:DHE-RSA-AES128-SHA256:DHE-RSA-AES128-SHA:DHE-DSS-AES128-SHA256:DHE-RSA-AES256-SHA256:DHE-DSS-AES256-SHA:DHE-RSA-AES256-SHA:!aNULL:!eNULL:!EXPORT:!DES:!RC4:!3DES:!MD5:!PSK';
```
Bye bye RC4, DES, and MD5.

## Bonus - While you're here - HSTS!
Hey, now that you've got your nginx config cracked open, and your brain is all in TLS land, let's turn on the HTTP Strict Transport Security header to force all connections over HTTPS. *Be Warned* if you do this and you're not ready for it, a lot of things will hit the fan. Make sure that there are no legitimate HTTP connections happening on your website because they will stop working altogether if you enable this.
Read up on all the things you need to worry about with HSTS elsewhere before doing this but if you're familiar with the concept and want to turn it on, its one simple line:

```
add_header Strict-Transport-Security "max-age=15638400; includeSubdomains;";
```

## 6 - Hang your new A+ SSL Labs test grade on your fridge and ask your Mom to bring you to get Pizza




**Edit** - Thanks to [@biosshadow](https://twitter.com/biosshadow) for pointing out an awesome tool by Mozilla which makes this all *very* easy. [Server Side TLS/SSL Config Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/)

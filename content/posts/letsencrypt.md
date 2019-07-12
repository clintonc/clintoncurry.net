---
title: "LetsEncrypt on Netlify with separate DNS"
date: 2019-07-11T22:24:42-07:00
draft: false
---

Netlify seems pretty great.  Use whatever site generator you want, and Netlify
will handle the continuous deployment from a git repository.  They can add even
more value by doing things like automatically giving you HTTPS.  However, you
can't use their automated service if you manage your own DNS.

Here follows a summary of what I had to do to get LetsEncrypt going with
Netlify (aside from the stuff I had to do to get Netlify working with my repo
and Hugo in the first place).  I want to continue using Google Domains to
manage my DNS, so Netlify can't do my certification for me.  Since I don't have
a terminal, I can't run certbot on that machine.  I can use "manual mode",
though, which can do the whole thing in the "traditional" way -- you prove you
own the domain by adding a TXT record.  An alternative is placing a file in a
specific place, but I didn't want to have to figure out how to make that work
with Hugo.  (With regular-old-clone-the-repo-and-serve Netlify, that would have
been pretty easy.).

Anyway, here's the command I ran to start the wizard in the right mode.  I
created some directories so that Certbot wouldn't try to write to places I
would need `sudo` for.

```bash
mkdir -p config work log
certbot certonly \
  --config-dir=config \
  --work-dir=work \
  --logs-dir=log \
  --manual \
  --preferred-challenges=dns \
  -d www.clintoncurry.net
```

At this point I was asked to set a DNS TXT record. I added it, and even though
I wasn't able to verify with a DNS query direct to my nameservers with dig, it
went through fine.  Good for three months.

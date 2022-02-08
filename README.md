HTTP Strict Transport Security Redirect
=======================================

A Docker image that sets the HSTS header and redirects to the HTTPS url.

Use with Synology
=================

I feel like this could be useful for a bunch of things, but I use it on my
Synology NAS to completely shut off port 80. Unfortunately, it's not as easy
as running this container on port 80, since Synology doggedly refuses to
give up that port. What you need to do is have anything _else_ in front of
your nas (like a router, which you should have, don't put your nas on the
open internet) that you can use to forward port 80 to whatever
random port you expose from this container. Then absolutely any outside
traffic that hits port 80 will see nothing but an HTTPS redirect.

HTTP Strict Transport Security Redirect
=======================================

A Docker image that sets the HSTS header and redirects to the HTTPS url.

Use with Synology
=================

I feel like this could be useful for a bunch of things, but I use it on my
Synology NAS to completely shut off port 80. 

Build, Save and Upload the Image
------------------------------------

    docker build -t hsts .
    sudo docker save hsts:latest | gzip > hsts.tar.gz

Launch the Container
--------------------

The only thing to keep in mind here is that you need to select "Use the same
network as Docker Host" in the Synology UI. This is so that the container can
forward LetsEncrypt requests back to Synology.

Forward the Port
----------------

Now you need to forward port 80 at your firewall/router to port 6854 on your
Synology NAS.

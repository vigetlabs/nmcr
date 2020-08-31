# Setup

## Requirements

+ [Docker](https://docs.docker.com/docker-for-mac)
+ [SequelPro](http://www.sequelpro.com/)

## Docker

Docker may conflict over port usage with other local host tools like MAMP. Turn these off before running the site with Docker.

1. Install [Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/).

The configuration has been tested with version 2.2.0.4; if you have an older version (especially pre-2.2), run "Check for updates..." and install.

2. Update `/etc/hosts` to point `nmcr.test` at `localhost`

Open `/etc/hosts` and add a line like so:

```
127.0.0.1 nmcr.test
```

Then run `sudo killall -HUP mDNSResponder` to flush your DNS cache.

[How to edit your Mac's Hosts file and why you would want to](https://www.imore.com/how-edit-your-macs-hosts-file-and-why-you-would-want)

3. Build the containers

Run `docker-compose build`. This will take a little while.

4. Import DB Backup

Run `unzip data/initial.zip` and copy the resulting file to `.docker-config/mysql`.

5. Run the site

Run `docker-compose up`. This will take a little while the first time while it's importing the DB. The site will now be accessible at [https://nmcr.test](https://nmcr.test).

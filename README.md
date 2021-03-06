# Gratipay Bot!

This repo holds the source code for [**@gratipay-bot**](https://github/gratipay-bot).


## What does Gratipay Bot do?

Gratipay Bot kicks off new [project
review](http://inside.gratipay.com/howto/review-projects) tickets.

Gratipay Bot kicks off [payday](http://inside.gratipay.com/howto/run-payday)
each Thursday with a new ticket, copying the description from the previous
week.


## Deployment

Here's how we install Gratipay Bot on a fresh Ubuntu 14.04 server at Digital Ocean:

```bash
apt-get update

apt-get install unattended-upgrades
dpkg-reconfigure unattended-upgrades

apt-get install git
git clone https://github.com/gratipay/bot.git
cd bot

apt-get install python3.4-venv
python3 -m venv env
env/bin/pip install --upgrade pip

./update.sh
```

Configuration lives in `/etc/environment`:

```
GITHUB_REPO=gratipay/inside.gratipay.com
GITHUB_USERNAME=gratipay-bot
GITHUB_PASSWORD=deadbeef-a-personal-security-token
```

Note that Gratipay Bot kicks off team review tickets from inside the [web
app](https://github.com/gratipay/gratipay.com).

Title: Getting Pelican set-up
Date: 2020-05-24 11:25
Category: howto

Getting pelican setup, but read down to the virtualenv section first

https://docs.getpelican.com/en/stable/install.html
```bash
# make a directory
mkdir ~/alittleknowledge
cd ~/alittleknowledge
# setup a python virtualenv
pyenv install 3.8.3
pyenv virtualenv 3.8.3 alittleknowledge
pyenv local myproject
# confirm installation
pyenv which python
# install pelican
pip install Pelican Markdown typogrify

```

## Deploying 


Quite a lot of hassle getting localhost to be visible across the network (i.e. when developing from the ipad); fixed via https://www.bleepingcomputer.com/news/security/wsl2-now-supports-localhost-connections-from-windows-10-apps/ ... where we had to make the server accessible to all addresses. This seems to be the case for both WSL and Mac OS.

```bash
pelican —-listen -b 0.0.0.0:8000
```




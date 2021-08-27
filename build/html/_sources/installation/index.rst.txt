.. IntStream documentation master file, created by
   sphinx-quickstart on Fri Feb 26 02:53:58 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Installation
############

.. contents:: Contents
   :depth: 3
   :backlinks: top


Bash installation
=================

Supported OS: 

* Ubuntu 18

.. code-block:: python

   # install nodejs 11
   curl -fsSL https://deb.nodesource.com/setup_11.x | sudo -E bash -
   sudo apt-get install -y nodejs

   # download package from github intstream releases
   sudo dpkg -i intstream-X.X-X.deb
   

   # setup nginx
   sudo rm /etc/nginx/conf.d/default.conf
   sudo rm -f /etc/nginx/sites-enabled/default
   ln -s /etc/nginx/sites-available/intstream.conf /etc/nginx/sitesenabled/intstream.conf

Docker Installation
===================

Coming Soon


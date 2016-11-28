===================
cert-formula
===================

Creates certificates and manages renewal using the certbot service.

.. note::

    See the full `Salt Formulas installation and usage instructions
    <http://docs.saltstack.com/en/latest/topics/development/conventions/formulas.html>`_.

Available states
================

.. contents::
    :local:

``certbot``
---------------

Installs and configures the certbot cli from git, creates the requested certificates and installs renewal cron job.
This is a shortcut for certbot.install certbot.config and certbot.domains .

``certbot.install``
-----------

Only installs the certbot client. Currently the certbot-auto method is used. This will create a virtualenv in the /root/.config/ directory.
The installation method will be replaced by using packages, as default as soon as they ara stable and available for all major platforms.

``certbot.config``
----------

Manages /etc/certbot/cli.ini config file.

``certbot.domains``
-----------
Creates a certificate with the domains in each domain set (certbot:domainsets in pillar). certbot uses a relatively short validity of 90 days.
Therefore, a cron job for automatic renewal every 60 days is installed for each domain set as well.

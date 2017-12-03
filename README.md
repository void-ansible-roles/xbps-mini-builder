xbps-mini-builder
=================


What is does this role do?
--------------------------

This role installs and manages an xbps miniature builder.  This is sometimes necessary when restricted packages are needed.  This role automates the process of setting up a repo and getting a builder running.  The builder is scheduled to run once per day.

Meta
----

Files Managed:
  * /etc/iptables.d/mini-repo.rules
  * /etc/cron.d/mini-repo
  * /opt/xbps-mini-repo/
  * /opt/xbps-mini-repo/xbps-mini-builder/
  * /opt/xbps-mini-repo/packages.list
  * /opt/xbps-mini-repo/xbps-src.conf
  * /opt/xbps-mini-repo/id_rsa

Defaults Provided:
  * None

Variables Required:
  * xbps_mini_builder_pkgs: file containing the list of packages to be built
  * xbps_mini_builder_conf: file containing configuration for xbps-src
  * xbps_mini_builder_servernames: the nginx server_name list for the repo to serve as

Optional Variables:
  * None

Files Required:
  * packages.list - Listing of packages to be built, one pkg name per line
  * xbps-src.conf - Configuration for xbps-src, in the standard format

Optional Files:
  * None

Conflicting Roles:
  * None

Depends On:
  * [network](https://github.com/void-ansible-roles/network)
  * [nginx](https://github.com/void-ansible-roles/nginx)

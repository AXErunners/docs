.. meta::
   :description: The open-source Axe Insight REST API provides you with a convenient, powerful and simple way to read data from the Axe network and build your own services with it.
   :keywords: axe, insight, API, REST, blockchain, explorer, JSON, HTTP, blocks, index, transactions

.. _insight-api:

========================
Insight API Installation
========================

The open-source Axe Insight REST API provides you with a convenient,
powerful and simple way to read data from the Axe network and build
your own services with it. Simple HTTP endpoints exist for all common
operations on the Axe blockchain familiar from the Bitcore Insight API,
as well as Axe-specific features such as InstantSend transactions,
budget proposals, sporks and the masternode list. This documentation
describes how to set up the 
`Axe Insight API <https://github.com/axerunners/insight-api>`__ server and
(optionally) the 
`Axe Insight UI <https://github.com/axerunners/insight-ui>`__ block 
explorer.

A standard installation of Ubuntu Linux 18.04 LTS will be used as an
environment for the server. We assume you are running as a user with
sudo permissions. First update all packages and install some tools and
dependencies::

  sudo apt update
  sudo apt upgrade
  sudo apt install npm build-essential libzmq3-dev

Download and extract the latest version of Axe Core::

  cd ~
  wget https://github.com/axerunners/axe/releases/download/v0.12.3.3/axecore-0.12.3.3-x86_64-linux-gnu.tar.gz
  tar -xvzf axecore-0.12.3.3-x86_64-linux-gnu.tar.gz
  rm axecore-0.12.3.3-x86_64-linux-gnu.tar.gz

Install `Axecore Node <https://github.com/axerunners/axecore-node>`_ and
create your configuration::

  sudo npm install -g @axerunners/axecore-node
  axecore-node create mynode

Install the Insight API service and (optionally) Insight UI::

  cd mynode
  axecore-node install @axerunners/insight-api
  axecore-node install @axerunners/insight-ui

Change paths in the configuration file as follows::

  nano axecore-node.json

- Change the value of ``datadir`` to ``../.axecore``
- Change the value of ``exec`` to ``../axecore-0.12.3/bin/axed``

Run it::

  axecore-node start

Your Insight API node will start up and begin to sync. Progress will be
displayed on stdout. Once sync is complete, the `API endpoints listed in
the documentation <https://github.com/axerunners/insight-api#api-http-endpoints>`_ 
will be available at::

  https://<ip-address>:3001/insight-api/<endpoint>/

The Insight UI block explorer will be available at::

  http://<ip-address:3001/insight/

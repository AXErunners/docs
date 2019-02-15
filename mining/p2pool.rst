.. meta::
   :description: Guide to setting up a Axe P2Pool node
   :keywords: axe, mining, X11, p2pool, node, pool, software, ASIC, mining pool

.. _p2pool:

======================
Axe P2Pool Node Setup 
======================

This guide describes how to set up a Axe P2Pool node to manage a pool
of miners. Unlike centralized mining pools, P2Pool is based on the same
peer-2-peer (P2P) model as Axe, making the pool as a whole highly
resistant to malicious attacks, and preserving and protecting the
decentralized nature of Axe. When you launch a P2Pool node, it seeks
out, connects with, and shares data with a decentralized network of
other P2Pool nodes (also known as peers). P2Pool nodes share a
cryptographic chain of data representing value, similar to Axe's
blockchain. The P2Pool version is called the sharechain. The
decentralized and fair nature of this mining model means mining with
P2Pool is strongly encouraged. P2Pool for Axe uses the `p2pool-axe
<https://github.com/axerunners/p2pool-axe>`_ software on GitHub, which is
a fork of p2pool for Bitcoin. For more information, see `here
<https://en.bitcoin.it/wiki/P2Pool>`__.

Because of the way P2Pool manages difficulty adjustments on the
sharechain, it is important to maintain low latency between the miners
and the P2Pool node to avoid miners submitting shares too late to enter
the sharechain. When setting up your node, you need to consider its
physical and network location relative to the miners you intend to
connect to the node. If you operate a mining farm, your P2Pool node
should probably be a physical machine on the same local network as your
miners. If you plan to operate a public node, it may be best to set up
your P2Pool node as a virtual machine in a data center with a high speed
connection so geographically close miners can mine to your pool with
relatively low latency.

This following section describes the steps to setup an Ubuntu Server
running P2Pool for Axe. It has been tested with Ubuntu 16.04 LTS and
18.04 LTS and Axe 1.2.1. While a reasonable effort will be made to
keep it up to date, it should be possible to modify the instructions
slightly to support different versions or operating systems as
necessary.

Setting up the host server
==========================

Download a copy of Ubuntu Server LTS from
https://www.ubuntu.com/download/server and install it on your system
according to the steps described `here
<https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-
server>`__. If you are using a VPS such as Vultr or AWS, your provider
will most likely provide an option to install this system during
provisioning. Ensure you enable OpenSSH server during setup so you can
control your server from a remote console. Once you have access to your
server, create a new non-root user if you have not already done so using
the following command, replacing ``<username>`` with a username of your
choice::

  adduser <username>

You will be prompted for a password. Enter and confirm using a new
password (different to your root password) and store it in a safe place.
You will also see prompts for user information, but this can be left
blank. Once the user has been created, we will add them to the sudo
group so they can perform commands as root::

  usermod -aG sudo <username> 

Reboot your server and log in as the new user. At this point it is
recommended to connect remotely using `PuTTY
<https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>`_ (for
Windows) or ssh (for Linux and macOS) if you have not already done so.

Setting up port forwarding
==========================

If you are on a private network behind a router, you will need to set up
port forwarding for at least port 8999 (UDP/TCP) for access to the
sharechain, as well as port 7923 (UDP/TCP) if you want your node to be
accessible to the public. How this is done depends on your particular
network router and is therefore beyond the scope of this documentation.
An example from the popular DD-WRT open source router distribution is
shown below. Guides to setting up port forwarding can be found `here
<https://www.wikihow.com/Set-Up-Port-Forwarding-on-a-Router>`__ and `here
<http://www.noip.com/support/knowledgebase/general-port-forwarding-
guide/>`__.

Take note of your IP address either from your router management
interface or by visiting https://www.whatismyip.com

.. figure:: img/p2pool-ddwrt.png
   :width: 400px

   Setting up port forwarding under DD-WRT

Option 1: Automated script setup
================================

Axe community member **dracocephalum** has generously donated a script
to automatically deploy everything required to run a p2pool-axe node
under Ubuntu Server 16.04 and higher. For more details, see `this forum
post <https://www.axerunners.com/forum/threads/script-to-deploy-p2pool-on-
ubuntu.18376/>`_, or simply follow these instructions to get the script.
To get fetch the script and get started, type::

  sudo apt install git
  git clone https://github.com/axerunners/p2pool-axe-deploy

The files will be created in the p2pool-axe-deploy folder. We now need
to configure a few variables specific to your system::

  nano ./p2pool-axe-deploy/p2pool.deploy.sh

Scroll down to the section labeled ``#Variables`` and enter the
following information, replacing the ``<xxx>`` placeholders after the
``=`` sign. Note that it may also be necessary to update the
``AXE_WALLET_URL``, ``AXE_WALLET_ZIP`` and ``AXE_WALLET_LOCAL``
values if they do not match the current version of Axe:

- ``PUBLIC_IP`` = your public IP address from the previous step
- ``EMAIL`` = your email address
- ``PAYOUT_ADDRESS`` = your AXE wallet address to receive fees
- ``USER_NAME`` = linux user name
- ``RPCUSER`` = enter a random alphanumeric rpc user name
- ``RPCPASSWORD`` = enter a random alphanumeric rpc password

Press **Ctrl + X** to close the editor and **Y** and **Enter** save the
file. Then run the script::

  bash ./p2pool-axe-deploy/p2pool.deploy.sh

The script will carry out all steps necessary to set up P2pool on Ubuntu
Server and start axed synchronisation. When setup is complete, you
should see a message reading **Installation Completed.** You can now
run a second script to start p2pool-axe::

  bash ~/p2pool.start.sh

Your P2Pool node is now running. If you see errors similar to **Error
getting work from axed** or **-10 Axe Core is downloading blocks...**
then you must wait until Axe finishes synchronisation. Once this is
done, you can point your miners to ``<ip_address>:7923`` to begin
mining.

.. image:: img/p2pool-antminer.png
   :width: 400px

.. figure:: img/p2pool-running.png
   :width: 400px

   Example configuration showing a single Bitmain Antminer D3 connected
   to a p2pool-axe node on the local network

Option 2: Manual setup
======================

First update your operating system as follows::

  sudo apt update
  sudo apt upgrade

Setting up axed
----------------

P2Pool requires a full Axe node to be running to get block and
transaction data. To download and install Axe, visit
https://www.axerunners.com/wallets on your computer to find the link to the
latest Axe Core wallet. Click **Linux**, then right-click on **Download
TGZ** for **Axe Core Linux 64 Bit** and select **Copy link address**.
Go back to your terminal window and enter the following command, pasting
in the address to the latest version of Axe Core by right clicking or
pressing **Ctrl + V**::

  cd ~
  wget https://github.com/axerunners/axe/releases/download/v1.2.1/axecore-1.2.1-linux64.tar.gz


Verify the integrity of your download by running the following command
and comparing the output against the value for the file as shown on the
Axe website under **Hash File**::

  sha256sum axecore-1.2.1-linux64.tar.gz

.. figure:: img/setup-manual-download.png
   :width: 250px

   Link to the hash file to verify download integrity

Create a working directory for Axe, extract the compressed archive,
copy the necessary files to the directory and set them as executable::

  mkdir .axecore
  tar xfvz axecore-1.2.1-linux64.tar.gz
  cp axecore-0.12.2/bin/axed .axecore/
  cp axecore-0.12.2/bin/axe-cli .axecore/
  chmod 777 .axecore/axe*

Clean up unneeded files::

  rm axecore-1.2.1-linux64.tar.gz
  rm -r axecore-0.12.2/

Create a configuration file using the following command::

  nano ~/.axecore/axe.conf

An editor window will appear. We now need to create a configuration file
specifying several variables. Copy and paste the following text to get
started, then replace the variables specific to your configuration as
follows::

  #----
  rpcuser=XXXXXXXXXXXXX
  rpcpassword=XXXXXXXXXXXXXXXXXXXXXXXXXXXX
  rpcallowip=127.0.0.1
  #----
  listen=1
  server=1
  daemon=1
  maxconnections=64
  #----


Replace the fields marked with ``XXXXXXX`` as follows:

- ``rpcuser``: enter any string of numbers or letters, no special
  characters allowed
- ``rpcpassword``: enter any string of numbers or letters, no special
  characters allowed

The result should look something like this:

.. figure:: img/p2pool-axe-conf.png
   :width: 400px

   Entering key data in axe.conf on the P2Pool node

Press **Ctrl + X** to close the editor and **Y** and **Enter** save the
file. You can now start running Axe on the masternode to begin
synchronization with the blockchain::

  ~/.axecore/axed

You will see a message reading **Axe Core server starting**. You can
continue with the following steps and check synchronization periodically
using the following command. Synchronization is complete when the number
of ``blocks`` is equal to the current number of blocks in the Axe
blockchain, as can be seen from any synchronized Axe wallet or `block
explorer <https://insight.docs.axerunners.com/insight/>`_::

  ~/.axecore/axe-cli getblockcount

Setting up P2Pool
-----------------

We will now set up the P2Pool software and its dependencies. Begin with
the dependencies::

  sudo apt install python-zope.interface python-twisted python-twisted-web python-dev
  sudo apt install gcc g++ git

Create working directories and set up p2pool-axe::

  mkdir git
  cd git
  git clone https://github.com/axerunners/p2pool-axe
  cd p2pool-axe
  git submodule init
  git submodule update
  cd axe_hash
  python setup.py install --user

We will add some optional extra interfaces to the control panel::

  cd ..
  mv web-static web-static.old
  git clone https://github.com/justino/p2pool-ui-punchy web-static
  mv web-static.old web-static/legacy
  cd web-static
  git clone https://github.com/johndoe75/p2pool-node-status status
  git clone https://github.com/hardcpp/P2PoolExtendedFrontEnd ext

You can now start p2pool and optionally specify the payout address,
external IP (if necessary), fee and donation as follows::

  python ~/git/p2pool-axe/run_p2pool.py --external-ip <public_ip> -f <fee> --give-author <donation> -a <payout_address>

You can then monitor your node by browsing to the following addresses,
replacing ``<ip_address>`` with the IP address of your P2Pool node:

- Punchy interface: http://ip_address:7923/static
- Legacy interface: http://ip_address:7923/static/legacy
- Status interface: http://ip_address:7923/static/status
- Extended interface: http://ip_address:7923/static/ext

.. image:: img/p2pool-antminer.png
   :width: 400px

.. figure:: img/p2pool-running.png
   :width: 400px

   Example configuration showing a single Bitmain Antminer D3 connected
   to a p2pool-axe node on the local network

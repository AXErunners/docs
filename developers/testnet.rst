.. meta::
   :description: Axe testnet and devnets are used by Axe developers for testing using tAXE
   :keywords: axe, masternodes, testnet, devnet, faucet, masternodes, testing, pool, explorer, mining pools, block explorer

.. _testnet:

===================
Testnet and devnets
===================

With the release of Axe Core 12.3, Axe added support for a great new
feature — **named devnets**. Devnets are developer networks that combine
some aspects of testnet (the global and public testing network) and some
aspects of regtest (the local-only regression testing mode that provides
controlled block generation). Unlike testnet, multiple independent
devnets can be created and coexist without interference. For practical
documentation on how to use devnets, see the `developer documentation
<https://axe-docs.github.io/en/developer-examples#devnet-mode>`__ or
this `blog post <https://blog.docs.axerunners.com/axe-devnets-bc27ecbf0085>`__.

Testnet is a fully functioning Axe blockchain with the one key
exception that because the Axe on the network can be created freely, it
has no value. This currency, known as tAXE, can be requested from a
faucet to help developers test new versions of Axe, as well as test
network operations using identical versions of the software before they
are carried out on the mainnet. There are a few other key differences:

- Testnet operates on port 19937 (instead of 9937)
- Testnet addresses start with "y" instead of "X", ADDRESSVERSION is 140
  (instead of 76)
- Testnet balances are denominated in tAXE (instead of AXE)
- Protocol message header bytes are 0xcee2caff (instead of 0xbf0c6bbd)
- Bootstrapping uses different DNS seeds: test.dnsseed.masternode.io,
  testnet-seed.darkcoin.qa, testnet-seed.axerunners.io
- Launching Axe Core in testnet mode shows an orange splash screen

To start Axe Core in testnet mode, find your axe.conf file and enter
the following line::

  testnet = 1

Tools and links
===============

The links below were collected from various community sources and may
not necessarily be online or functioning at any given time. Please join
`Axe Nation Discord <http://axechat.org>`_ or the `Axe Forum
<https://www.axerunners.com/forum/>`_ if you have a question relating to a
specific service.

- **Test builds:** https://jenkins.docs.axerunners.com/blue/
- **Bugtracker:** https://github.com/axerunners/axe/issues/new
- **Discussion and help:** https://www.axerunners.com/forum/topic/testing.53/
- **Masternode tools:** https://test.axeninja.pl/masternodes.html
- **Android wallet:** https://www.axerunners.com/forum/threads/axe-wallet-for-android-v5-testnet.14775/
- **Testnet for Bitcoin:** https://en.bitcoin.it/wiki/Testnet

Faucets
-------

- http://test.faucet.masternode.io - by coingun
- http://faucet.test.axe.crowdnode.io - ndrezza

Explorers
---------

- http://insight.test.axe.crowdnode.io
- https://testnet-insight.axerunners.org/insight

Pools
-----

- https://test.pool.docs.axerunners.com [stratum+tcp://test.stratum.docs.axerunners.com] - by flare
- http://test.p2pool.axe.siampm.com [stratum+tcp://test.p2pool.axe.siampm.com:17903] by thelazier
- http://p2pool.axeninja.pl:17903/static - by elbereth
- http://test.p2pool.masternode.io:18998/static - by coingun

Masternodes
===========

Installing a masternode under testnet generally follows the same steps
as the :ref:`mainnet masternode installation guide <masternode-setup>`,
but with a few key differences:

- You will probably be running a development version of Axe instead of
  the stable release. See `here <https://jenkins.docs.axerunners.com/blue/organizations/jenkins/axerunners-axe-gitian-nightly/activity>`__
  for a list of builds, then choose the latest successful build and
  click **Artifacts** to view a list of binaries.
- When opening the firewall, port 19937 must be opened instead of (or in
  addition to) 9937. Use this command: ``ufw allow 19937/tcp``
- Your desktop wallet must be running in testnet mode. Add the following
  line to *axe.conf*: ``testnet = 1``
- When sending the collateral, you can get the 1000 tAXE for free from
  a faucet (see above)
- You cannot use axeman to install development versions of Axe. See
  the link to downloadable builds above.
- Your masternode configuration file must also specify testnet mode. Add
  the following line when setting up *axe.conf* on the masternode:
  ``testnet = 1``
- As for mainnet masternodes, the RPC username and password must contain
  alphanumeric characters only
- When cloning sentinel, you may need to clone the development branch
  using the ``-b`` option, for example: ``git clone -b core-v0.12.2.x
  https://github.com/axerunners/sentinel.git``
- Once sentinel is installed, modify
  ``~/.axecore/sentinel/sentinel.conf``, comment the mainnet line and
  uncomment: ``network=testnet``
- The wallet holding the masternode collateral will expect to find the
  ``masternode.conf`` file in ``~/.axecore/testnet3/masternode.conf``
  instead of ``~/.axecore/masternode.conf``.

Testnet 0.13.0
==============

In November 2018, the Axe team announced the start of testing of the
upcoming Axe 0.13.0 release. Extensive internal testing has already been
done on the 0.13.0 code, but there are numerous bugs that can only be
revealed with actual use by real people. The Axe team invites anybody
who is interested to download the software and become active on testnet.
This release includes:

- Automatic InstantSend for Simple Transactions
- Deterministic Masternode List
- 3 Masternode Keys: Owner, Operator and Voting
- Special Transactions
- PrivateSend Improvements

Discussion:

- Testnet announcement: https://blog.docs.axerunners.com/product-brief-axe-core-release-v0-13-0-5d7fddffb7ef
- Product brief: https://blog.docs.axerunners.com/product-brief-axe-core-release-v0-13-0-5d7fddffb7ef
- Testnet tools: https://docs.axerunners.com/en/latest/developers/testnet.html
- Issue tracking: https://github.com/axerunners/axe/issues/new

Latest test binaries:

- https://github.com/axerunners/axe/releases/tag/v0.13.0.0-rc11

Testnet 0.12.3
==============

In June 2018, the Axe team announced the start of testing of the
upcoming Axe 0.12.3 release. Extensive internal testing has already been
done on the 0.12.2 code, but there are numerous bugs that can only be
revealed with actual use by real people. The Axe team invites anybody
who is interested to download the software and become active on testnet.
This release includes:

- Named Devnets, to help developers quickly create multiple independent
  devnets
- New format of network message signatures
- Governance system improvements
- PrivateSend improvements
- Additional indexes cover P2PK now
- Support for pruned nodes in Lite Mode
- New Masternode Information Dialog

Discussion:

- https://www.axerunners.com/forum/threads/v12-3-testing.38475
- Testnet tools: https://docs.axerunners.com/en/latest/developers/testnet.html
- Issue tracking: https://github.com/axerunners/axe/issues/new

Latest test binaries:

- https://github.com/axerunners/axe/releases/tag/v0.12.3.0-rc3


Testnet 0.12.2
==============

In October 2017, the Axe team announced the launch of a testnet for
public testing of the upcoming 0.12.2 release of the Axe software.
Extensive internal testing has already been done on the 0.12.2 code, but
there are numerous bugs that can only be revealed with actual use by
real people. The Axe team invites anybody who is interested to download
the software and become active on testnet. This release includes:

- DIP0001 implementation https://github.com/axerunners/dips/blob/master/dip-0001.md
- 10x transaction fee reduction (including InstantSend fee)
- InstantSend vulnerability fix
- Lots of other bug fixes and performance improvements
- Experimental BIP39/BIP44 complaint HD wallet (disabled by default, should be fully functional but there is no GUI yet)

Discussion:

- Testnet 12.2 discussion: https://www.axerunners.com/forum/threads/v12-2-testing.17412/
- Testnet tools: https://www.axerunners.com/forum/threads/testnet-tools-resources.1768/
- Issue tracking: https://github.com/axerunners/axe/issues/new

Latest successfully built develop branch binaries:

- Axe Core: https://jenkins.docs.axerunners.com/blue/organizations/jenkins/axerunners-axe-gitian-nightly
- Sentinel: https://github.com/axerunners/sentinel/tree/develop

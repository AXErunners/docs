.. meta::
   :description: Developers guide and information about sporks and Axe version history
   :keywords: axe, developers, sporks, version history

.. _developers:

==========
Developers
==========

Axe Core has published an extensive `Developer Guide 
<https://axerunner.github.io/en/>`_ to help new developers get started
with the Axe code base, and as a reference for experienced developers.
This guide can be leveraged to quickly and efficiently integrate
external applications with the Axe ecosystem. Anyone can contribute to
the guide by submitting an issue or pull request on GitHub. The
documentation is available at: https://axerunner.github.io/en/

The Axe Core Team also maintains the `Axe Roadmap
<https://github.com/axerunners/axe-roadmap>`_, which sets out delivery
milestones for future releases of Axe and includes specific technical
details describing how the development team plans to realise each
challenge. The Axe Roadmap is complemented by the `Axe Improvement
Proposals <https://github.com/axerunners/dips>`_, which contain detailed
technical explanations of proposed changes to the Axe protocol itself.

The remaining sections available below describe practical steps to
carry out common development tasks in Axe.

.. toctree::
   :maxdepth: 1

   dip3-upgrade.rst
   translating.rst
   compiling.rst
   testnet.rst
   insight.rst

.. _understanding-sporks:

Sporks
======

A multi-phased fork, colloquially known as a "spork", is a mechanism
unique to Axe used to safely deploy new features to the network through
network-level variables to avoid the risk of unintended network forking
during upgrades. It can also be used to disable certain features if a
security vulnerability is discovered - see :ref:`here <sporks>` for a
brief introduction to sporks. This documentation describes the meaning
of each spork currently existing on the network, and how to check their
respective statuses.

Spork functions
---------------

Sporks are set using integer values. Many sporks may be set to a
particular epoch datetime (number of seconds that have elapsed since
January 1, 1970) to specify the time at which they will active. Enabled
sporks are set to 0 (seconds until activation). This function is often
used to set a spork enable date so far in the future that it is
effectively disabled until changed. The following sporks currently exist
on the network and serve functions as described below:

SPORK_2_INSTANTSEND_ENABLED
  Governs the ability of Axe clients to use InstandSend functionality.

SPORK_3_INSTANTSEND_BLOCK_FILTERING
  If enabled, masternodes will reject blocks containing transactions in
  conflict with locked but unconfirmed InstandSend transactions.

SPORK_5_INSTANTSEND_MAX_VALUE
  Enforces the maximum value in Axe that can be included in an
  InstantSend transaction.

SPORK_6_NEW_SIGS
  Enables a new signature format for Axe-specific network messages
  introduced in Axe 12.3. For more information, see `here
  <https://github.com/axerunners/axe/pull/1936>`__ and `here
  <https://github.com/axerunners/axe/pull/1937>`__.

SPORK_8_MASTERNODE_PAYMENT_ENFORCEMENT
  If enabled, miners must pay 50% of the block reward to a masternode
  currently pending selection or the block will be considered invalid.

SPORK_9_SUPERBLOCKS_ENABLED
  If enabled, superblocks are verified and issued to pay proposal
  winners.

SPORK_10_MASTERNODE_PAY_UPDATED_NODES
  Controls whether masternodes running an older protocol version are
  considered eligible for payment. This can be used as an incentive to
  encourage masternodes to update.

SPORK_12_RECONSIDER_BLOCKS
  Forces reindex of a specified number of blocks to recover from
  unintentional network forks.

SPORK_13_OLD_SUPERBLOCK_FLAG
  Deprecated. No network function since block 614820.

SPORK_14_REQUIRE_SENTINEL_FLAG
  Toggles whether masternodes with status are eligible for payment if
  status is WATCHDOG_EXPIRED, i.e. Sentinel is not running properly.

SPORK_15_DETERMINISTIC_MNS_ENABLED
  Controls whether `deterministic masternodes
  <https://github.com/axerunners/dips/blob/master/dip-0003.md>`_ are
  required. When activated, the legacy masternode list logic will no
  longer run and non-updated masternodes will not be eligible for
  payment.

SPORK_16_INSTANTSEND_AUTOLOCKS
  Enables automatic transaction locking for transactions with less than
  a specified number of inputs, and removes the legacy InstantSend fee.
  Allows any node to request the transaction lock, not just the sending
  node.

SPORK_17_QUORUM_DKG_ENABLED
  Enables the `DKG process to create LLMQ quorums
  <https://github.com/axerunners/dips/blob/master/dip-0006.md>`_. At the
  moment, this only activates a dummy DKG on testnet, which will later
  be replaced by the real DKG for mainnet and testnet. When enabled, 
  simple PoSe scoring and banning is also active.
  

Viewing spork status
--------------------

The ``spork show`` and ``spork active`` commands issued in the debug
window (or from ``axe-cli`` on a masternode) allow you to interact with
sporks. You can open the debug window by selecting **Tools > Debug
console**.

.. figure:: img/axecore-sporks.png
   :width: 300px

   spork show and spork active output in the Axe Core debug console


Version History
===============

Full release notes and the version history of Axe are available here:

- https://github.com/axerunners/axe/blob/master/doc/release-notes.md

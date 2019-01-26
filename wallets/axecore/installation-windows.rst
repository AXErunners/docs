.. meta::
   :description: How to download, install and encrypt the Axe Core wallet in Windows
   :keywords: axe, core, wallet, windows, installation

.. _axecore-installation-windows:

Windows Installation Guide
==========================

This guide describes how to download, install and encrypt the Axe Core
wallet for Windows. The guide is written for Windows 10, but the steps
should be similar for Windows XP, Vista, 7 and 8.

Downloading the Axe Core wallet
--------------------------------

Visit https://www.axerunners.com/get-axe to download the latest Axe Core
wallet. In most cases, the website will properly detect which version
you need. Click the blue **Axe Core** button to download the installer
directly.

.. figure:: img/windows/106328672.png
   :height: 250px

   The website properly detects the wallet appropriate for your system

If detection does not work, you will need to manually choose your
operating system and whether you need a 32 or 64 bit version. If you are
unsure whether your version of Windows is 32 or 64 bit, you can check in
Windows 10 under **Start > Settings > System > About**. For details on
how to check this in other versions of Windows, see
`here <https://www.lifewire.com/am-i-running-a-32-bit-or-64-bit-version-of-windows-2624475>`__.

.. figure:: img/windows/106328726.png
   :height: 250px

   In Windows Settings, click System

.. figure:: img/windows/106328734.png
   :width: 337px

   Under the System section, click About to view the System type. This is
   a 64 bit system.

Once you know which version you need, download the Axe Core Installer
to your computer from https://www.axerunners.com/wallets

.. figure:: img/windows/106328767.png
   :height: 250px

   Manually selecting and downloading an installer

Save the file you downloaded to your Downloads folder.

Verifying Axe Core
-------------------

This step is optional, but recommended to verify the integrity of the
file you downloaded. This is done by checking its SHA256 hash against
the hash published by the Axe Core development team. To view the
published hash, click the **Hash file** button on the wallet download
page.

.. figure:: img/windows/112789205.png
   :height: 250px

   Downloading the Axe Core hash file

Once both the Axe Core file and the hash file have downloaded, open the
hash file in a text editor or your browser and find the hash value for
the Axe Core file you downloaded.

.. figure:: img/windows/112789262.png
   :height: 250px

   Viewing the Axe Core hash file

This hash value should correspond with the hash value of the file you
have downloaded to ensure it is authentic and was not corrupted during
transit. To do this, open **Command Prompt**, browse to the location 
where you saved the file, and run the following command, replacing the 
version with the specific version of the file you downloaded.

::

    certutil -hashfile <axecore-version-windows>.exe SHA256

.. figure:: img/windows/112789384.png
   :width: 470px

   Generating an SHA256 hash for the downloaded file

If the hashes match, then you have an authentic copy of Axe Core for
Windows.

Running the Axe Core installer
-------------------------------

Double-click the file to start installing Axe Core.

.. figure:: img/windows/106328792.png
   :height: 250px

   The Axe Core installer in the Downloads folder

At this point, you may see a warning from Windows SmartScreen that the
app is unrecognized. You can safely skip past this warning by clicking
**More info**, then **Run anyway**.

.. figure:: img/windows/106328818.png
   :width: 354px

.. figure:: img/windows/106328813.png
   :width: 354px

   Bypassing Windows SmartScreen to run the app. This warning is known 
   as a “false positive”.

The installer will then guide you through the installation process.

.. figure:: img/windows/106328844.png
   :height: 250px

   The Axe Core installer welcome screen

Click through the following screens. All settings can be left at their
default values unless you have a specific reason to change something.

.. figure:: img/windows/106328866.png
   :height: 250px

   Select the installation location

.. figure:: img/windows/106328871.png
   :height: 250px

   Select the Start menu folder

.. figure:: img/windows/106328876.png
   :height: 250px

   Axe Core is being installed

.. figure:: img/windows/106328881.png
   :height: 250px

   Installation is complete

Running Axe Core for the first time
------------------------------------

Once installation is complete, Axe Core will start up immediately. If
it does not, click **Start > Axe Core > Axe Core** to start the
application. The first time the program is launched, you will be offered
a choice of where you want to store your blockchain and wallet data.
Choose a location with enough free space, as the blockchain can reach
10GB+ in size. It is recommended to use the default data folder
if possible.

.. figure:: img/windows/106328945.png
   :height: 250px

   Choosing the Axe Core data folder

Axe Core will then start up. This will take a little longer than usual
the first time you run it, since Axe Core needs to generate
cryptographic data to secure your wallet.

.. figure:: img/windows/106328960.png
   :height: 250px

   Starting Axe Core

Synchronizing Axe Core to the Axe network
-------------------------------------------

Once Axe Core is successfully installed and started, you will see the
wallet overview screen. You will notice that the wallet is “out of
sync”, and the status bar at the bottom of the window will show the
synchronization progress.

.. figure:: img/windows/106328993.png
   :height: 250px

   Axe Core begins synchronizing with the Axe network

During this process, Axe Core will download a full copy of the Axe
blockchain from other nodes to your device. Depending on your internet
connection, this may take a long time. If you see the message “No block
source available”, check your internet connection. When synchronization
is complete, you will see a small blue tick in the lower right
corner.

.. figure:: img/windows/106329009.png
   :height: 250px

   Axe Core synchronization is complete

You can now begin to use your wallet to send and receive funds.

Encrypting your Axe wallet
---------------------------

After your wallet has synchronized with the Axe network, it is strongly
advised to encrypt the wallet with a password or passphrase to prevent
unauthorized access. You should use a strong, new password that you have
never used somewhere else. Take note of your password and store it
somewhere safe or you will be locked out of your wallet and lose access
to your funds.

To encrypt your wallet, click **Settings > Encrypt Wallet**.

.. figure:: img/windows/106329084.png
   :height: 250px

   Encrypting the Axe wallet with a password

You will be asked to enter and verify a password.

.. figure:: img/windows/106329102.png
   :height: 150px

   Enter a password

.. figure:: img/windows/106329143.png
   :width: 354px

   Confirm you want to encrypt your wallet

When the encryption process is complete, you will see a warning that
past backups of your wallet will no longer be usable, and be asked to
shut down Axe Core. When you restart Axe Core, you will see a small
blue lock in the lower right corner.

.. figure:: img/windows/106329165.png
   :height: 250px

   Fully encrypted and synchronized Axe Core wallet

You can now begin to use your wallet to safely send and receive funds.

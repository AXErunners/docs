.. meta::
   :description: How to install the Axe wallet on your iOS device
   :keywords: axe, mobile, wallet, ios, installation, compile

.. _axe-ios-installation:

Installation
============

App Store
---------

The easiest way to install the Axe Wallet for iOS is from the App
Store. While older versions of iOS are supported, you will need to be
using iOS 10.0 or newer to use the latest version.

.. image:: img/app-store.png
    :width: 250 px
    :target: https://itunes.apple.com/app/id1430269763

Compiling from source
---------------------

The source code for the wallet is available `here
<https://github.com/axerunners/axewallet>`_. The following steps
describe how to download and compile the wallet from source.

1. Install `Xcode <https://itunes.apple.com/us/app/xcode/id497799835?mt=12>`_ 
   from the App Store. The download is about 5GB, so this step may take
   some time.

2. Open **Xcode**, agree to the terms and conditions, then close the 
   app.

3. Open the **Terminal** app and enter the following commands::

     cd ~/Documents
     mkdir src
     cd src
     git clone https://github.com/axerunners/axewallet.git

4. Open **Xcode** again and click **File -> Open**

5. Navigate to ``~/Documents/src/axewallet/AxeWallet.xcodeproj`` and
   click **Open**.

6. Click **Product > Run** to build and run the app in **Simulator**.

.. figure:: img/xcode.png
   :width: 500px

   Axe iOS wallet running in Simulator after compiling in Xcode

You can also make modifications to the code and sideload the app onto
your iOS device. For details, see `this post on Reddit
<https://www.reddit.com/r/sideloaded/wiki/how-to-sideload>`_.

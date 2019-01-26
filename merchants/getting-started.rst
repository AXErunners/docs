.. meta::
   :description: Guide for merchants getting started with Axe. Online and offline payment processors
   :keywords: axe, pos, merchants, payment processor, store, wordpress, woocommerce, coinpayments, point of sale

.. _merchants:

.. include:: <isopub.txt>

===============
Getting Started
===============

Axe welcomes new merchants and supports integration through a
standardised onboarding process. It's easy to begin accepting payments
in Axe and enjoy the following benefits:

- Settlement within seconds and clearance within minutes
- Ability to accept payments from any market around the world
- Irreversible transactions to prevent fraud
- Advanced privacy for both customers and merchants
- Lowest fees in the industry

A three-part course on why Axe is a popular choice for payments and how
integration takes place is available in English and Spanish on
`AxeAcademy.com <http://www.axeacademy.com>`_. To get started with an
integration in your sales system, simply select an online or point of
sale payment solution from the lists below. If you are unsure, GoCoin is
a popular choice due its support for :ref:`InstantSend <instantsend>`,
while CoinPayments supports the largest range of online shop software.
Anypay is an incredibly simple solution for retail stores, and also
supports InstantSend. Larger integrations may require some customisation
or cooperation with a specialist payment processor such as `ePaymints
<http://epaymints.com>`__. This documentation also describes the
:ref:`administrative <merchants-administrative>` and  :ref:`technical
<merchants-technical>` steps required to integrate  various Axe
services.

Any Axe received in payment can be automatically converted to the fiat
currency of your choice using services such as `Uphold
<https://uphold.com>`_. Simply select the card for the target currency
and click **Add funds** -> **With cryptocurrency**. Any cryptocurrency
deposited to this address will immediately be converted to the target
fiat currency at the time of deposit.

Many major merchants accept Axe - check out `Bitrefill
<https://www.bitrefill.com>`__ or `CheapAir
<https://www.cheapair.com>`__ for examples of what merchant integration
can look like. Once you are up and running accepting Axe, consider
adding your business to the directory maintained at `Discover Axe
<https://discoveraxe.com>`_ for increased visibility.

Payment Processors
==================

This section lists known payment processors supporting Axe and the
business platforms they support. Please conduct thorough research before
choosing a payment provider to ensure your needs will be met. 

For more advanced payment processing needs, such as for high risk
merchant accounts in industries challenged with high levels of
chargebacks, it is recommended to contact Axe partner `ePaymints
<http://epaymints.com>`__.


Online Stores
-------------

Due to the wide range of platforms for online stores, the following
table is intended to help you select an appropriate payment processor
for your existing store.

+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
|                                                              | `CoinPayments <https://www.coinpayments.net>`_ | `GoCoin <https://gocoin.com>`_ | `PayBear <https://www.paybear.io>`_ | `Coingate <https://coingate.com>`_ | `GoURL <https://gourl.io>`_ |
+==============================================================+================================================+================================+=====================================+====================================+=============================+
| `Blesta <https://www.blesta.com>`_                           | |check|                                        |                                |                                     | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `BoxBilling <http://www.boxbilling.com>`_                    | |check|                                        |                                |                                     |                                    |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Easy Digital Downloads <https://easydigitaldownloads.com>`_ | |check|                                        |                                |                                     |                                    | |check|                     |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Ecwid <https://www.ecwid.com>`_                             | |check|                                        |                                |                                     |                                    |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Jigoshop <https://www.jigoshop.com/>`_                      |                                                |                                |                                     |                                    | |check|                     |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Magento <https://magento.com>`_                             | |check|                                        | |check|                        | |check|                             | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `OpenCart <https://www.opencart.com>`_                       | |check|                                        | |check|                        | |check|                             | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `osCommerce <https://www.oscommerce.com>`_                   | |check|                                        | |check|                        |                                     | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `PrestaShop <https://www.prestashop.com>`_                   | |check|                                        | |check|                        | |check|                             | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Shopify <https://www.shopify.com>`_                         |                                                | |check|                        |                                     |                                    |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Tomato Cart <https://sourceforge.net/projects/tomatocart>`_ | |check|                                        |                                |                                     |                                    |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `Ubercart <https://www.drupal.org/project/ubercart>`_        | |check|                                        | |check|                        |                                     |                                    |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `VirtueMart <http://virtuemart.net>`_                        |                                                | |check|                        |                                     | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `WHMCS <https://www.whmcs.com>`_                             | |check|                                        | |check|                        |                                     | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `WooCommerce <https://woocommerce.com>`_                     | |check|                                        | |check|                        | |check|                             | |check|                            | |check|                     |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `WP eCommerce <https://wpecommerce.org>`_                    | |check|                                        |                                |                                     |                                    | |check|                     |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+
| `ZenCart <https://www.zen-cart.com>`_                        | |check|                                        | |check|                        |                                     | |check|                            |                             |
+--------------------------------------------------------------+------------------------------------------------+--------------------------------+-------------------------------------+------------------------------------+-----------------------------+


Point of Sale
-------------

A range of Point of Sale systems are available. Many function as an app
or simple website serving a checkout interface and QR code generator,
while others support custom features such as NFC or a rewards scheme.
QR.cr, Spark Payments and Anypay are supported by the community and are
particularly widespread.

+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| Name                                                          | App?    | Web?           | Hardware? | NFC?    | Notes                                                                                    |
+===============================================================+=========+================+===========+=========+==========================================================================================+
| `34 Bytes <https://34bytes.com>`_                             |         |                | |check|   |         | Hardware terminal capable of printing receipts.                                          |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `Alt36 <http://www.alt36.com>`_                               |         |                |           |         | Full stack system. Supports integration of suppliers and employees.                      |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `Anypay <http://anypay.global>`_                              | |check| | |check|        |           |         | Popular solution for smartphones with web interface and backend.                         |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `CDPay <https://www.cdpay.eu>`_                               | |check| |                |           |         |                                                                                          |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `CoinPayments <https://www.coinpayments.net>`_                | |check| | |check|        |           |         |                                                                                          |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `CopPay <https://coppay.io>`_                                 |         | |check|        |           |         |                                                                                          |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `EletroPay <https://www.eletropay.com/>`_                     |         |                | |check|   |         | POS device with ePaper display for unique QR codes and built-in receipt printer.         |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `Festy <https://festy.ie>`_                                   |         |                |           | |check| | NFC wristband payments for festivals.                                                    |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `GB CortexPay <https://www.generalbytes.com/pos>`_            |         |                | |check|   |         | Professional hardware terminal with multiple payment options.                            |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `Paytomat <https://paytomat.com>`_                            |         |                |           |         | Token rewards for crypto payments.                                                       |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `QR.cr <https://qr.cr/>`_                                     | |check| | |check|        |           |         | Cheap solution with many features to use a mobile phone as a POS terminal.               |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `QuikWallet <http://quikwallet.com>`_                         | |check| | |check|        |           |         | India only. Also supports SMS payment.                                                   |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `Salamantex <https://www.salamantex.com>`_                    | |check| | |check|        | |check|   |         | Payments by app, web, software extension for existing POS or standalone POS terminal.    |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `SetGetGo <https://setgetgo.com/>`_                           | |check| | |check|        |           |         | Available for Android, web and Android APIs, payment buttons, competitive fees           |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+
| `Spark Payments <https://www.axerunners.com/forum/threads/39665/>`_ | |check| | |check|        |           |         | Available for Android, Windows, macOS, Linux. 94 exchange rates and Uphold.com supported |
+---------------------------------------------------------------+---------+----------------+-----------+---------+------------------------------------------------------------------------------------------+

Installation Examples
=====================

This section contains worked examples of how to install, configure and
process your first payment using the payment processors listed in this
documentation.

WooCommerce and GoCoin
----------------------

If your online store is built on WooCommerce, you can simply install
GoCoin as an additional payment gateway and immediately begin accepting
Axe. This guide assumes you have already `installed Wordpress
<https://codex.wordpress.org/Installing_WordPress>`_, `installed
WooCommerce <https://docs.woocommerce.com/document/installing-
uninstalling-woocommerce/>`_ and `created at least one product
<https://docs.woocommerce.com/document/managing-products>`_ in your
store.

Go to the `gocoin-woocommerce GitHub Releases page
<https://github.com/GoCoin/gocoin-woocommerce/releases>`_ and download a
zip file of the latest version of the plugin, as shown below. In your
WordPress administration backend, select **Plugins -> Add New** and then
click **Upload Plugin**. Click **Choose File** and select the file you
just downloaded, then click **Install Now** and **Activate Plugin**. 

.. image:: img/gocoin-download.png
   :width: 300px
.. image:: img/gocoin-install.png
   :width: 300px

Next, go to the `GoCoin merchant sign up page
<https://gocoin.com/merchant_signup>`_ and create an account. Once you
are logged in, go to **Preferences**, select **Axe** and click **Add
AXE Address** to add a payment withdrawal address. You will receive an
email with a link to confirm the address. Next, go to **Developers** and
copy the **Merchant ID** into a temporary text file. Next, click **Get
Key** to display a valid API key. Copy this key into your temporary text
file as well. Finally, you can optionally add a Axe logo to your
checkout by **Profile** section and clicking **Logo -> Upload**.

.. image:: img/gocoin-address.png
   :width: 300px
.. image:: img/gocoin-apikey.png
   :width: 300px

Back in the WordPress plugins section, click the **Settings** button for
the WooCommerce plugin and navigate to **Checkout -> GoCoin** section.
Ensure the GoCoin plugin is enabled here, then enter the **Merchant ID**
and **API Key** in the appropriate fields as shown below, modifying the
other fields as necessary. Click **Save changes** when you are ready.

.. image:: img/gocoin-settings.png
   :width: 550px

Your customers will now see an option to pay with Axe when completing
the checkout process for an order. The payment will be processed by
GoCoin, and you will receive emails detailing each purchase procedure.
You can choose how often you want to withdraw your payments, to which
Axe address and various other options in the GoCoin administration
section. See the `GoCoin Documentation <https://gocoin.com/docs>`_ for
more information.

.. image:: img/gocoin-order.png
   :width: 150px
.. image:: img/gocoin-invoice.png
   :width: 225px
.. image:: img/gocoin-scan.png
   :width: 225px

.. figure:: img/gocoin-paid.png
   :width: 400px

   Completing payment through the GoCoin payment processor


WooCommerce and CoinPayments.net
--------------------------------

If your online store is built on WooCommerce, you can simply install
CoinPayments as an additional payment gateway and immediately begin
accepting Axe. This guide assumes you have already `installed Wordpress
<https://codex.wordpress.org/Installing_WordPress>`_, `installed
WooCommerce <https://docs.woocommerce.com/document/installing-
uninstalling-woocommerce/>`_ and `created at least one product
<https://docs.woocommerce.com/document/managing-products>`_ in your
store. A `video <https://www.youtube.com/watch?v=Xa2o_8s3RNY>`_ of the
process to install the CoinPayments payment processor is also available.

In your WordPress administration backend, select **Plugins -> Add New**
and type "coinpayments.net" into the search box. A plugin named
**CoinPayments.net Payment Gateway for WooCommerce** should appear.
Click **Install Now** to install the plugin. Alternatively, you can
`download the plugin <https://wordpress.org/plugins/coinpayments-
payment-gateway-for-woocommerce>`_ from the WordPress website as a zip
file and upload it using the **Upload Plugin** button. Once the plugin
is installed, click **Activate** to begin configuration.

.. figure:: img/coinpayments-plugin.png
   :width: 400px

   Installing the CoinPayments.net WooCommerce plugin

Next, go to CoinPayments.net and `sign up
<https://www.coinpayments.net/register>`_ to create an account. Once you
are logged in, go to **Account -> Coin Acceptance Settings** and enable
Axe, as well as optionally entering a withdrawal address. Next, go to
**Account -> Account Settings** and copy **Your Merchant ID** from the
**Basic Settings** area into a text file. Then navigate to the
**Merchant Settings** section and enter a long, random series of
characters for the **IPN Secret**. Copy this code to your temporary file
as well.

Back in the WordPress plugins section, click the **Settings** button for
the WooCommerce plugin and navigate to **Checkout -> CoinPayments.net**
section. Ensure the CoinPayments plugin is enabled here, then enter the
**Merchant ID**, **IPN Secret** and **Description** in the appropriate
fields as shown below. Click **Save Changes** when you are ready.

.. figure:: img/coinpayments-settings.png
   :width: 550px

   Configuring the CoinPayments.net WooCommerce plugin

Your customers will now see an option to pay with Axe when completing
the checkout process for an order. The payment will be processed by
CoinPayments.net, and you will receive emails detailing each purchase
procedure. You can choose how often you want to withdraw your payments,
to which Axe address and various other options in the CoinPayments
administration section. See the `CoinPayments Documentation
<https://www.coinpayments.net/help>`_ or `Merchant Tools
<https://www.coinpayments.net/merchant-tools>`_ for more information.

.. image:: img/coinpayments-order.png
   :width: 150px
.. image:: img/coinpayments-confirm.png
   :width: 400px
.. image:: img/coinpayments-scan.png
   :width: 250px

.. figure:: img/coinpayments-paid.png
   :width: 250px

   Completing payment through the CoinPayments.net payment processor


Point-of-Sale with Anypay
-------------------------

`Anypay.global <http://anypay.global>`_ allows you to quickly start
accepting point-of-sale payments in Axe at a physical store. The
service functions as a simple website that you load on any internet-
connected and touch-enabled device, such as a smartphone or tablet.

Begin by registering an account with Anypay. You will be asked to
specify an email address and password. Once you are signed in, you must
add a Axe payment withdrawal address.

.. image:: img/anypay-register.png
   :width: 200px
.. image:: img/anypay-signup.png
   :width: 200px
.. image:: img/anypay-address.png
   :width: 200px

.. figure:: img/anypay-admin.png
   :width: 400px

   Setting up Anypay

Once this has been set up, you can begin processing payments
immediately. Simply log in to https://pos.anypay.global or tap
**Merchant Point of Sale App** in the admin area using your device. A
keypad will appear. Enter the invoice amount in USD or AXE and press
the **COLLECT** button at the bottom of the screen. The app will
generate a QR code for your customer to scan. Once payment is complete,
you will be able to create a new invoice by tapping **Next Payment**, or
view the status of your invoices by tapping the **menu button** in the
top left corner of the keypad, or checking the **Invoices** section of
the administration backend. Withdrawals are processed to the address you
specified shortly after payment is complete.

.. image:: img/anypay-enter.png
   :width: 200px
.. image:: img/anypay-scan.png
   :width: 200px
.. image:: img/anypay-paid.png
   :width: 200px

Point-of-Sale with Spark
------------------------

`Spark Payments <https://www.axerunners.com/forum/threads/39665/>`_ allows you
to quickly start accepting point-of-sale payments in Axe at a physical
store. The system works as an app, and is available for Android, macOS,
Windows and Linux, with an iOS progressive web app (`PWA
<https://en.wikipedia.org/wiki/Progressive_Web_Apps>`_) in development.

The project is an external terminal application for processing Axe
payments in brick and mortar stores. The merchant types the sale amount
in their local currency (94 currencies supported), the application will
generate a QR code sale for the proper amount of Axe for the customer
to scan. Then the terminal will provide feedback on the status of the
payment (received, timed out, partial, instantsend or regular), and if
set up - fiat conversion through `uphold.com <https://uphold.com>`_. A
guide on how to set up Spark with Uphold to convert payments to fiat
currency is available in 
`English <https://github.com/axerunners/docs/raw/master/merchants/Spark-Payments-Uphold-English.pdf>`__ 
and 
`German <https://github.com/axerunners/docs/raw/master/merchants/Spark-Payments-Uphold-German.pdf>`__.

To use Spark, open the app on your device. If this is the first time you
are using the app, you will need to specify a Axe address to receive
payments from the system, as well as your chosen fiat currency. You can
change this information at any time from the menu. To generate a payment
invoice, enter the amount in fiat currency. Spark will generate a QR
code containing your specified address and the requested amount,
denominated in Axe. The customer scans the QR code, and the app will
display a visual indication when payment is complete.

.. figure:: img/spark.png
   :width: 600px

   Configuring and receiving payment using Spark Payments

Payment systems like Anypay and Spark can be integrated with your
existing terminal and/or accounting software (such as Square Register,
by recording sales invoiced in Axe as an **Other Payment Type** in the
system. This allows you to keep track of your Axe income as easily as
if you were accepting cash.

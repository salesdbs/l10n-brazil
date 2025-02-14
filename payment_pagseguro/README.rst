=================
Payment PagSeguro
=================

.. !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Beta-yellow.png
    :target: https://odoo-community.org/page/development-status
    :alt: Beta
.. |badge2| image:: https://img.shields.io/badge/licence-AGPL--3-blue.png
    :target: http://www.gnu.org/licenses/agpl-3.0-standalone.html
    :alt: License: AGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fl10n--brazil-lightgray.png?logo=github
    :target: https://github.com/OCA/l10n-brazil/tree/12.0/payment_pagseguro
    :alt: OCA/l10n-brazil
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/l10n-brazil-12-0/l10n-brazil-12-0-payment_pagseguro
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runbot-Try%20me-875A7B.png
    :target: https://runbot.odoo-community.org/runbot/124/12.0
    :alt: Try me on Runbot

|badge1| |badge2| |badge3| |badge4| |badge5| 

Payment Acquirer: PagSeguro Implementation

This module extends the payment module to add a new payment method: Pagseguro.

There are three ways to integrate the Pagseguro API, in this module we use the
checkout transparent approach.

You can learn more about that on this `youtube video <https://www.youtube.com/watch?v=3DxKEKoSPkA>`_.

If you wish to use Pagseguro on production environment you need to get an approval
from pagseguro, more on that `here <https://dev.pagseguro.uol.com.br/docs/comecando-processo-de-integracao>`_.

**Table of contents**

.. contents::
   :local:

Installation
============

This module depends on:

* payment
* web_tour

Configuration
=============

This module will require registering in eCommerce PagSeguro https://acesso.pagseguro.uol.com.br/

To configure your API keys go to Invoicing -> Configuration -> Payment Acquirers -> PagSeguro.
Then insert your token on the credentials page, as shown below:

.. figure:: https://raw.githubusercontent.com/OCA/l10n-brazil/12.0/payment_pagseguro/static/description/payment_acquirer_01.png
    :alt: Payment acquirer pagseguro
    :width: 600 px

Under the configuration page, select your payment journal.
On the upper right corner buttons you can publish on your website and change the environment.

.. figure:: https://raw.githubusercontent.com/OCA/l10n-brazil/12.0/payment_pagseguro/static/description/payment_acquirer_02.png
    :alt: Payment acquirer pagseguro
    :width: 600 px

The credential Token and can only be acquired via the PagSeguro user account.
On your account, go to "Venda Online" > "Integrações". Then, click on "Gerar Token".

.. figure:: https://raw.githubusercontent.com/OCA/l10n-brazil/12.0/payment_pagseguro/static/description/pagseguro_website.png
    :alt: Payment acquirer pagseguro
    :width: 600 px

Still on the configuration tab, you can configure the maximum amount
of installments available for your clients to select at the
payment.

So far, we only support up to 12 installments, setting a value higher than
that will lead to possible errors on payment.

.. figure:: https://raw.githubusercontent.com/OCA/l10n-brazil/12.0/payment_pagseguro/static/description/payment_acquirer_03.png
    :alt: Pagseguro max installments configuration
    :width: 600 px


* full manual for API:

https://dev.pagseguro.uol.com.br/reference/pagseguro-reference-intro

Usage
=====

After the configuration, you can go to the website module, and buy a product
in your website shop by selecting the Pagseguro payment method.

Here you can select:
  - Payment form (there is only credit card so far).
  - Amount of installments you want to pay (notice than the maximum value you can select is based on your acquirer configuration).

When selecting the installments you can see the value of each installment on
the input field on the right.

After that, insert you Card number, name, expiration date and security code.
Then, click on the pay now button.

So far, we support only VISA, MasterCard, American Express and Diners brands.

.. figure:: https://raw.githubusercontent.com/OCA/l10n-brazil/12.0/payment_pagseguro/static/description/pagseguro_payment_form.png
    :alt: Payment form pagseguro
    :width: 600 px

**notice**: The credentials that we use in this image are not from a real card,
instead this is a test card given by the Pagseguro for test purposes.
You can find more tests cards here https://dev.pagseguro.uol.com.br/reference/testing-cards.

Known issues / Roadmap
======================

Issues
  - To support more brands we need to overwrite the focusout event from the card number field
  - Selecting installments should also change the total price

Roadmap
  - Add bill payment form
  - Add debit card payment form
  - Add PIX payment form

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/l10n-brazil/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us smashing it by providing a detailed and welcomed
`feedback <https://github.com/OCA/l10n-brazil/issues/new?body=module:%20payment_pagseguro%0Aversion:%2012.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
~~~~~~~

* KMEE

Contributors
~~~~~~~~~~~~

* Luis Felipe Miléo <mileo@kmee.com.br>
* Cristiano Rodrigues <cristiano.rodrigues@kmee.com.br>
* Kilian Macedo <kilian.macedo@kmee.com.br>

Other credits
~~~~~~~~~~~~~

The development of this module has been supported by:

`KMEE INFORMATICA LTDA <https:/www.kmee.com.br>`__

Maintainers
~~~~~~~~~~~

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

This module is part of the `OCA/l10n-brazil <https://github.com/OCA/l10n-brazil/tree/12.0/payment_pagseguro>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.

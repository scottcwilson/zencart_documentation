---
title: Manual Credit Card Collection
description: Why you shouldn't use manual credit card processing with online stores
category: payment
weight: 10
---

Older payment modules like "credit card" (`cc.php`) and "CEON Manual Card" (`ceon_manual_card.php`) are not recommended for the following reasons: 

- They are not PCI Compliant.
- Storing credit card details in your database puts the store owner at great financial risk in the event of a data breach.  [Fines can range from $5000 to $500,000 for said breach.](https://ebizcharge.com/blog/storing-credit-card-information-safely-in-2022-the-dos-and-donts/#:~:text=In%20addition%2C%20if%20a%20merchant,far%20outweighs%20any%20security%20solution.)
- It may not be legal to do this (depending on your jurisdiction).
- It may be a violation of your merchant agreement (depending on the terms you agreed to).
- If a data breach occurs then the various 3rd party providers whom you rely upon may have to respond, and thus some of those parties (such as hosting providers) may not let you put them at such risk because it would be a violation of their terms of service with you. You could be in breach of contract with them which might result in account suspension.

So what should you do? 

- Switch to one of the built-in payment gateways.  There are many [payment processors Zen Cart supports](https://www.zen-cart.com/content.php?14-Payment-Processing). 

- Switch to one of the [payment gateways from the Plugins Library](https://www.zen-cart.com/downloads.php?do=cat&id=8).

The former will be better supported of course, but it's your choice.

Please see [getting off manual card collection](/user/payment/getting_off_manual/) for ideas on replacements for manual card collection. 

Notes: 

- Many gateways can be configured to [Auth Only instead of Auth and Capture](/user/payment/auth_only/) if your concern is that the final order total might change.

- The plugin [Authorize.net CIM Card on file](https://www.zen-cart.com/downloads.php?do=file&id=2272) allows you to securely store credit card information at the payment gateway.  The Zen Cart database stores only a token for use in future charges.  This method of tokenizing credit card data is the accepted best practice for enacting card on file transactions.

All these options give you a credit card entry form on your checkout payment page, which is what most customers will expect.  (Naturally they all require an [SSL certificate](/user/security/ssl_cert/), but hopefully you already have one; if not, [install SSL](/user/installing/enable_ssl/) first.)


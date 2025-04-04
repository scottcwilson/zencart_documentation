---
title: Variant Stock 
description: Using POSM and tracking quantities of products with variants 
category: Running
weight: 10
---

Older releases of Zen Cart do not track the stock of individual product variants (a t-shirt's stock of large versus medium, for example).  There are commercial modifications that address this requirement however, such as 
the [Products' Options' Stock Manager](https://vinosdefrutastropicales.com/product_extra_files/options_stock/readme.html).
Note that this plugin is sometimes called "Products Options Stock Manager" (without the apostrophes) or just "POSM."

There are also open source plugins which provide this capability; search for "Stock by Attributes."

In version 2.1.0 of Zen Cart, POSM has been added as a core feature.
See [the POSM wiki](https://github.com/lat9/options_stock_support/wiki) for detailed information. 

To track variant stock in Zen Cart 2.1.0 and higher using POSM: 
- go to Admin > Modules > Plugin Manager 
- install Products' Options' Stock Manager
- Users of the Responsive Classic template will need to change the configuration value [Dependent Attributes: Outer Selector](/user/admin_pages/configuration/configuration_optionsstockmanager/#dependent_attributes_outer_selector).

Users of Zen Cart 1.5.8a, 2.0.0 and 2.0.1 may use the encapsulated version of POSM provided in v2.1.0, but must follow [these instructions on Upgrading POSM](https://github.com/lat9/options_stock_support/wiki/Release%E2%80%90Specific-Upgrade-Notes#upgrading-posm-to-v500-and-later).

Once POSM is installed, on Admin > Catalog > Categories/Products, drill down to a product with attributes.  You'll be able to spot products with attributes because the "A" icon on the right will be blue rather than black. 

<img src="/images/products_icons_attrs.png" alt="Admin Product Listing Icons showing Attributes" style="float: right" />
<br clear="all" />
<br>

If the "A" is still black and you need a refresher on adding attributes, please see [Attributes - adding to products](/user/products/attributes/) and [Attributes Controller](/user/admin_pages/catalog/attributes_controller/).

## Configuring Variant Stock Levels 

Once you have a product with a blue "A", and you want to track stock on each variant, you have to configure the product to  be POSM managed. 

- Go to Admin > Catalog > Manage Options' Stock.  Using the "Display products from category" dropdown, select the category of the product you wish to manage.  Click the "Go" button on the right. 

- Use the "Choose the product to manage" dropdown, and select the desired product.  Click the "Go" button on the right.

- Under the label "Version" on the green bar at the bottom, you'll see a dropdown with "* (All)" selected.  

![Adding POSM management the first time](/images/posm_new_1.png)

- Click the "Insert" button to the right. Now you will see a row for each product/attribute combination. 

![Adding POSM management the first time](/images/posm_new_2.png)

Set the quantities of each variant under the Qty label and press update.
Note that you may also provide specific SKUs for each variant using the Option Model/SKU.

For more details on this screen, see the 
[admin help page for Manage Options' Stock](/user/admin_pages/catalog/options_stock_manager/) and the 
[Manage Options' Stock](https://github.com/lat9/options_stock_support/wiki/Admin-User-Interface-Changes#catalog--manage-options-stock) in the POSM help. 

## Managing Variant Stock Levels 

- Go to Admin > Catalog > Options' Stock -- View All.  

- By default, this screen only lists variants with low stock.  You may view all your variant products by clicking the "View *all* managed variants" checkbox and clicking the "Go" button. 

![POSM View All screen](/images/posm_view_all.png)

For more details on this screen, see the 
[admin help page for Options Stock - View All](/user/admin_pages/catalog/options_stock_view_all/) and the 
[Options' Stock View All](https://github.com/lat9/options_stock_support/wiki/Admin-User-Interface-Changes#catalog--options-stock-view-all) in the POSM help. 

## Displaying Stock Statuses 

When POSM is enabled, indicators like "In Stock" or "Back Ordered" are shown in various places, such as on the shopping cart page.

![POSM Stock Statuses](/images/posm_stock_status.jpg) 

These may be disabled using Admin > Configuration > Options Stock Manager > Stock Status Display: Show Messages?

## Dependent Attributes

Attributes in POSM-controlled products are dependent by default.  You must choose attributes in the order in which they are presented (which is by the sort order set when creating the Product Options). 

![POSM Dependent attributes](/images/dependent_attributes.png)

In the example shown above, you must choose Size before you can choose Media Type.

If the product were not POSM-controlled, all attribute settings would be available at the same time.

![Regular attributes](/images/regular_attributes.png)

The dependent attribute feature is highly configurable; see [Configuration Settings for Options' Stock Manager](/user/admin_pages/configuration/configuration_optionsstockmanager/). 

## My Variants have different prices and weights!

There are two ways to handle this situation: 

#### a) No Plugins 

The built-in solution to this problem uses attribute prices and weights.

The [Attributes Controller](/user/admin_pages/catalog/attributes_controller/) allows you to set prices and weights for attribute values.  In this example from the demo data, the Premium model is $100 more, the 8mb memory is $50 more, and the 16mb memory is $75 more. 

See [Attribute Pricing](/user/products/attribute_pricing/) for more information about doing this.

![Attribute Prices](/images/attribute_prices.jpg)

These values are displayed on the storefront as offsets from the base price. 

![Attributes Prices Storefront](/images/attribute_prices_storefront.jpg)

#### b) Using the POSM-PW plugin 

The commercial plugin [POSM Price/Weight](https://vinosdefrutastropicales.com/index.php?main_page=product_info&cPath=2_7&products_id=60) allows you to set the weights and prices of variant products on a variant-by-variant basis, rather than attribute-by-attribute. 


![POSM Product Prices](/images/posmpw_prices.jpg)

These values are displayed on the storefront as final prices once all attributes are selected. 

![Attributes Prices Storefront](/images/posmpw_prices_storefront.jpg)


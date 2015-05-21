[![Build Status](https://travis-ci.org/OCA/connector-magento.svg?branch=8.0)](https://travis-ci.org/OCA/connector-magento)
[![Coverage Status](https://coveralls.io/repos/OCA/connector-magento/badge.png?branch=8.0)](https://coveralls.io/r/OCA/connector-magento?branch=8.0)

Odoo Connector Magento Modules
==============================

*OpenERP Magento Connector (also known as MagentoERPconnect) is a bi-directional connector, 100% compatible with the last OpenERP 7.0 and latest Magento versions.*

This new release of MagentoERPconnect is based on the [OpenERP Connector framework](https://github.com/OCA/connector).

The mailing list for this project is on https://launchpad.net/~openerp-connector-community

Documentation:
http://www.odoo-magento-connector.com
http://www.odoo-connector.com

================================



Odoo
Clone the repositories below in the path where you chosed to store the addons:

$ git clone git@github.com:OCA/connector.git -b 8.0
$ git clone git@github.com:OCA/connector-ecommerce.git -b 8.0
$ git clone git@github.com:OCA/connector-magento.git -b 8.0
$ git clone git@github.com:OCA/e-commerce.git -b 8.0
$ git clone git@github.com:OCA/product-attribute.git -b 8.0
$ git clone git@github.com:OCA/sale-workflow.git -b 8.0
Important
Keep the git branches entire. Do not copy-paste the modules in another directory.
Add the branches in the addons path, either using the server command line or adding them in the Odoo server configuration file.

Example using the command line argument:

$ /path/to/openerp-server --addons-path /path/to/connector,/path/to/connector-ecommerce,/path/to/connector-magento,/path/to/e-commerce,/path/to/product-attribute,/path/to/sale-workflow
You also need to install the magento Python package. So install it with either pip or either easy_install:

$ pip install magento

$ easy_install magento
Note that you may need to use the root rights on your system.

In Odoo, update the modules list using Settings > Modules > Update Modules List.

Go to the menu Settings > Modules > Installed Modules, remove the Installed filter and search for Magento Connector, then click on Install.

Magento
For the time being, the Magento extension originally built by OpenLabs is still used by the connector. But the version published on Magento Connect is outdated.

Download the following Bazaar branch and install it in Magento:

$ bzr branch lp:magentoerpconnect/magento-module-oerp6.x-stable magento-module
In order to install it:

Move the Openlabs folder in the magento_root/app/code/community.
Move the file app/etc/modules/Openlabs_OpenERPConnector.xml in magento_root/app/etc/modules.
Flush the Magento cache from the admin panel or by removing everything in magento_root/var/cache
Important
Please check if you have installed Magento on PHP with a 5.4.x* version. Magento is not compatible with this version and would prevent the API to behave normally. In that case, you must retrograde to PHP 5.3.x or apply the patch provided by Magento (see http://magento.com/resources/system-requirements)
Configuring the Magento web-services
In the Magento admin panel, go to System > Web-Services > SOAP/XML-RPC - Roles.
Create a new role named openerp with access to All resources.
In System > Web-Services > SOAP/XML-RPC - Users, create a new user named as you want, for instance openerp_connect, and an API key. In User Role, choose the openerp role.
After the installation
Once the addon is installed, you may want to:

Read or read again Key questions when connecting Odoo with Magento
Assign the Connector Manager group on your user.
Create the Backend in Connectors > Magento > Backend, use the role created in Configuring the Magento web-services.
Synchronize the initial metadata using the button Synchronize Metadata on the backend.
Configure the translations if you use them: How to configure translations
Configure: How to configure emails
Configure: Howto: configure payment methods
Configure: Howto: configure automatic workflows
Configure: How to configure shipping methods
Configure: How to configure warehouses
Configure: How to configure pricing
On the backend,

Import the customer groups
Optionally, import the partners, otherwise they will be imported on the fly with the sales orders
Import the product categories
Configure the default values (accounting, ...) of the new categories, using the Check the connector checkpoint
Import the products
Configure the new products (accounting, suppliers, stock rules, ...) of the new products, using the Check the connector checkpoint
Create an inventory for your products
Update the stock quantities on Magento
Import the sales orders
Once you are all done and happy, configure the schedulers: How to configure schedulers
On a daily basis
Check the connector checkpoint
Monitor and resolve jobs
Odoo
Clone the repositories below in the path where you chosed to store the addons:

$ git clone git@github.com:OCA/connector.git -b 8.0
$ git clone git@github.com:OCA/connector-ecommerce.git -b 8.0
$ git clone git@github.com:OCA/connector-magento.git -b 8.0
$ git clone git@github.com:OCA/e-commerce.git -b 8.0
$ git clone git@github.com:OCA/product-attribute.git -b 8.0
$ git clone git@github.com:OCA/sale-workflow.git -b 8.0
Important
Keep the git branches entire. Do not copy-paste the modules in another directory.
Add the branches in the addons path, either using the server command line or adding them in the Odoo server configuration file.

Example using the command line argument:

$ /path/to/openerp-server --addons-path /path/to/connector,/path/to/connector-ecommerce,/path/to/connector-magento,/path/to/e-commerce,/path/to/product-attribute,/path/to/sale-workflow
You also need to install the magento Python package. So install it with either pip or either easy_install:

$ pip install magento

$ easy_install magento
Note that you may need to use the root rights on your system.

In Odoo, update the modules list using Settings > Modules > Update Modules List.

Go to the menu Settings > Modules > Installed Modules, remove the Installed filter and search for Magento Connector, then click on Install.

Magento
For the time being, the Magento extension originally built by OpenLabs is still used by the connector. But the version published on Magento Connect is outdated.

Download the following Bazaar branch and install it in Magento:

$ bzr branch lp:magentoerpconnect/magento-module-oerp6.x-stable magento-module
In order to install it:

Move the Openlabs folder in the magento_root/app/code/community.
Move the file app/etc/modules/Openlabs_OpenERPConnector.xml in magento_root/app/etc/modules.
Flush the Magento cache from the admin panel or by removing everything in magento_root/var/cache
Important
Please check if you have installed Magento on PHP with a 5.4.x* version. Magento is not compatible with this version and would prevent the API to behave normally. In that case, you must retrograde to PHP 5.3.x or apply the patch provided by Magento (see http://magento.com/resources/system-requirements)
Configuring the Magento web-services
In the Magento admin panel, go to System > Web-Services > SOAP/XML-RPC - Roles.
Create a new role named openerp with access to All resources.
In System > Web-Services > SOAP/XML-RPC - Users, create a new user named as you want, for instance openerp_connect, and an API key. In User Role, choose the openerp role.
After the installation
Once the addon is installed, you may want to:

Read or read again Key questions when connecting Odoo with Magento
Assign the Connector Manager group on your user.
Create the Backend in Connectors > Magento > Backend, use the role created in Configuring the Magento web-services.
Synchronize the initial metadata using the button Synchronize Metadata on the backend.
Configure the translations if you use them: How to configure translations
Configure: How to configure emails
Configure: Howto: configure payment methods
Configure: Howto: configure automatic workflows
Configure: How to configure shipping methods
Configure: How to configure warehouses
Configure: How to configure pricing
On the backend,

Import the customer groups
Optionally, import the partners, otherwise they will be imported on the fly with the sales orders
Import the product categories
Configure the default values (accounting, ...) of the new categories, using the Check the connector checkpoint
Import the products
Configure the new products (accounting, suppliers, stock rules, ...) of the new products, using the Check the connector checkpoint
Create an inventory for your products
Update the stock quantities on Magento
Import the sales orders
Once you are all done and happy, configure the schedulers: How to configure schedulers
On a daily basis
Check the connector checkpoint
Monitor and resolve jobs

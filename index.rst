Rangespan Retailer Integration Docs
***********************************

These articles will guide you through your interactions with the Rangespan system. If you have any questions, you can contact your account manager or retailers@rangespan.com. 

See below a short introduction to the Rangespan system:

.. youtube:: http://www.youtube.com/watch?v=sMYVMgkcl_g



Features
========

`Rangespan Product Search <1%20-%20Rangespan%20Product%20Search.html>`_ 
------------------------------------------------------------------------
    
The rangespan.com/range page allows you to:
    - `Research Products within the larger online market <1%20-%20Rangespan%20Product%20Search.html#research-products>`_
    - `Find Relevant Products sourced by Rangespan <1%20-%20Rangespan%20Product%20Search.html#find-selection>`_

You can also directly launch new products:
    - `Build and Share Shortlists of appealing products <2%20-%20Launching%20Products.html#building-shortlists>`_
    - `Use the raw data for extra analysis or to share more widely <2%20-%20Launching%20Products.html#download-product-data>`_
    - `Click and 'launch' new products on your site <2%20-%20Launching%20Products.html#launch-product-selections>`_


`Rangespan Product Data <http://rangespan-retailer-integration.readthedocs.org/en/latest/Product%20Data.html>`_
---------------------------------------------------------------------------------------------------------------

`Click through to full article <http://rangespan-retailer-integration.readthedocs.org/en/latest/Product%20Data.html>`_


Rangespan aggregates, transforms and performs Quality Control on item data from suppliers and manufacturers. This is stored as `Basic <http://rangespan-retailer-integration.readthedocs.org/en/latest/Product%20Data.html#basic-attributes>`_ and `Extended Attributes <http://rangespan-retailer-integration.readthedocs.org/en/latest/Product%20Data.html#extended-attributes>`_. Enterprise Retailers can provide `Custom Template Guidelines <http://rangespan-retailer-integration.readthedocs.org/en/latest/Product%20Data.html#custom-templates>`_.


`Rangespan Consolidated Offers <http://rangespan-retailer-integration.readthedocs.org/en/latest/Consolidated%20Offers.html>`_
-----------------------------------------------------------------------------------------------------------------------------

`Click through to full article <http://rangespan-retailer-integration.readthedocs.org/en/latest/Consolidated%20Offers.html>`_


Retailers access the best prices from our suppliers daily. API-integrated retailers have access to live inventory; we update SFTP-integrated retailers 4 times a day with the latest availability. 


`Rangespan Order Management <http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html>`_
-----------------------------------------------------------------------------------------------------------------------

`Click through to full article <http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html>`_


This page details the process behind:

- `Placing an order <http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html#placing-an-order>`_
- `Tracking an order <http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html#order-status>`_
- `Cancelling an order <http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html#cancelling-an-order>`_
- `Order Delivery
<http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html#delivery-process>`_
- `Customer Enquiries <http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html#customer-enquiries>`_
- `Returns
<http://rangespan-retailer-integration.readthedocs.org/en/latest/Order%20Management.html#order-returns>`_

Technical Details
=================
Documentation links
-------------------
Retailers can automate interactions with Rangespan using exchanges over Ssh File Transfer Protocol (SFTP) or by calling our software Application Programming Interface (API). 
 - `API documentation <https://www.rangespan.com/docs/api/v2/index.html>`_
 - `SFTP documentation <_SFTP.html>`_

Rangespan provides a framework to test the integration `here. <hhtps://www.rangespan.com>`_

API or SFTP?
------------
Many retailers find feeds easier to prepare integration for, while using the API requires some upfront development.  The key differences are:
 * **Speed**: An API call is processed immediately, while SFTP exchanges are processed less frequently. An SFTP-integrated retailer might see a lag of up to 15 minutes, between an order file transferring to Rangespan's SFTP and Rangespan's systems assigning those orders to the best supplier.
 * **Accessibility**: APIs are accessed programmatically by software, which can make it harder for the retailer's non-technical staff to access or modify some information on an ad-hoc basis.  Non-technical staff can usually interact with feeds manually easily if needed.
 * **Format**: The information exchanged through the API is JSON formatted, while SFTP uploads are CSV (comma separated values).  It is usually much easier to make manual corrections to a CSV file (in Excel) than directly in JSON.
 * **Security** Both API and SFTP are encrypted, ensuring sensitive data is transferred in a secure manner.

A mixed approach of feeds and API is possible.  A retailer might, for example, use CSV feeds for product attribute information but communicate about orders through the API.


Glossary
========

Concepts and key words (like RIN or Retailer Listing State) can be found in the `Glossary <00%20-%20Glossary.html>`_.

Rangespan Order Management
==========================

For technical details, see the relevant sections for `API Integration <https://www.rangespan.com/docs/api/v2/index.html#orders>`_ or `SFTP Integration <http://rangespan-retailer-integration.readthedocs.org/en/latest/_SFTP.html#orders>`_. This article describes how retailers can use the website to track and manage orders, and what happens in practise.

Placing an order
----------------

Once an order is placed, Rangespan's system assigns it to the best available supplier, typically within 5 minutes of the order being placed by the retailer. 

.. sidebar:: Supplier Performance

    Rangespan monitors agrregate fulfilment rates and processing times: this influence whether they get an order or not. We require that suppliers ship the item within 2 business days for standard delivery methods and within 1 day for expedited methods.

The shipping method for the order is set based on the cost price of the item. An item worth less than 40 GBP can be shipped un-tracked, unsigned. Items with a cost price between 40 GBP and 100 GBP need to be tracked, and any order worth above 100 GBP needs to be tracked and signed for. Suppliers are responsible for getting the item to the end customer, and may upgrade the shipping method in some cases.

The 'placed date' submitted by the retailer will be used to look up the cost price. This feature exists only to allow retailers to keep up-to-date pricing and availability for week-end orders even if the orders themselves are submitted a day or two later.


Order Status
------------

You can access a list of in-progress orders by making an `API call <https://www.rangespan.com/docs/api/v2/#get-details-for-an-order>`_, or on `Rangespan's website <https://www.rangespan.com/orders/retailer>`_. Retailers are notified of any updates on their orders on a daily schedule via `SFTP order notifications <http://rangespan-retailer-integration.readthedocs.org/en/latest/_SFTP.html#order-notifications-overview>`_. 

Rangespan breaks a retailer order into single rangespan orders with one unit of one sku. These are grouped back in any API responses, but the individual components are what we will most often refer to as 'orders'.

Orders will be in one of the following states:

.. csv-table::  
   :header: Order State, Description
   :widths: 20,80   
   
    "Pending", "Rangespan's system is processing these orders
    These have not yet been assigned to a supplier for shipment."
    "Processing", "Orders have been assigned to a supplier for shipment.
  
    Before returning a product, some suppliers might prefer a replacement to a refund.
    In these cases the order is placed into 'Processing' again."
    "At Risk", "Rangespan escalates any issues with 'At Risk' orders
    Usually, this involves following up with our vendors."
    "Shipped", "Order has been shipped.
  
    Depending on the shipping method, it can be 1-3 days before the customer receives the item.
    If the supplier uses a tracked delivery method (higher value orders) 
    tracking details are made available from the time an order enters this state."
    "Cancelled", "A cancelled order has not yet been shipped.
    Credit will be provided for any orders that have already been invoiced."
    "Refunded", "A customer returns the goods within the agreed terms.
    An order that is refunded will show up as 2 lines in the invoice: once on the sale, and once for the refund deduction."
    
Orders move between states as seen in this figure:

.. image:: images/order_states.png


Cancelling an order
-------------------

Orders can be cancelled via our `API <https://www.rangespan.com/docs/api/v2/#cancel-an-order>`_, or via the Rangespan website (see chases). It is not currently possible to cancel orders via SFTP.

In most cases, cancellations can be applied immediately. If a cancelation is sent *after* the supplier has dispatched the item, Rangespan's operations team will notify the retailer to request that the customer return the product, instead.


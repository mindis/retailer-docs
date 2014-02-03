Rangespan Retailer FTP Integration
**********************************

Versioning
==========
Last updated: 2014-02-02

Connection Details
==================
sftp.rangespan.com

Use your rangespan account name as the username. Password communicated seperately by your Rangespan account manager. 

Home Directory:
sftp.rangespan.com/data/rangespan/retailers/[username]

Data Formats
============

Dates and times
---------------

Date and time related fields should be UTC and formatted as per `ISO-8601 <http://en.wikipedia.org/wiki/ISO_8601>`_, some common examples are shown below.


.. csv-table:: 
    :header: Representation,Format,Example
    
    "Date", "YYYY-MM-DD", "2013-02-28"
    "Date and time", "YYYY-MM-DDTHH:MM:SS", "2013-02-28T23:59:59"


Pricing
-------

Throughout, prices are described as a number with 2 decimal places. Do NOT include '£' or 'GBP' in any of the price fields. Prices are in GBP.



Catalog
=======

- sftp.rangespan.com/data/rangespan/retailers/[retailer]/catalog

Rangespan generates 2 files daily, with the latest information



Catalog Basic - Overview
------------------------
.. csv-table::  
   :stub-columns: 1
   :widths: 20, 80

   "Type", "Rangespan Generated"
   "Description", "Basic product information excluding price. Affects all products from the retailer's selection."
   "Filename", "catalog_basic_[YYYYMMDD].csv"

 
Catalog Basic - Example
-----------------------
.. csv-table:: 
    :header: rin, state,category,item_name,gtin,manufacturer,manufacturer_part_number,description,asin,image_url,image_date

    "R0000EW5RX","live","tablet-cases","Amazon Kindle Flip-Arm LED Light, Black","05052801822010","Opus","OP10002","Super LED light is as bright as six regular LEDs [..]","","http://media.rangespan.com/image/R0000EW5RX","15/07/2012 19:40"
    "R0000EVZVF","live","activity-toys","Tomy 71515 Be Baby - Aqua Splash and Print","05011666715158","Tomy","71515","No mess fun for parent and baby[...]","","http://media.rangespan.com/image/R0000EVZVF","12/11/2013 19:10"
 
*Note: the descriptions were shortened for readability here.*
 
Extended Catalog - Overview
----------------------------
.. csv-table::  
   :stub-columns: 1
   :widths: 20, 120

   "Type", "Rangespan Generated"
   "Description", "Full product information excluding price. Affects all products from the retailer's selection. Raw Key-value pairs with most basic descriptions of a product."
   "Filename", "catalog_extended_[YYYYMMDD].csv"

Extended Catalog - Example
--------------------------
.. csv-table::  
   :header: rin, key, value
   :widths: 20, 40, 100
   
    "rin","attribute","value"
    "R0000EW5RX","vat_code_uk","standard_rate"
    "R0000EW5RX","manufacturer_part_number","OP10002"
    "R0000EW5RX","manufacturer","Opus"
    "R0000EW5RX","item_name","Amazon Kindle Flip-Arm LED Light, Black"
    "R0000EW5RX","category","tablet-cases"
    "R0000EW5RX","description","Super LED light is as bright as six regular LEDs and never need replacing. Strong wide mouth clip grips almost anything, or use free standing as a task light. Cool to the touch, never gets hot."
    "R0000EW5RX","gtin","05052801822010"
    "R0000EVZVF","gender","U"
    "R0000EVZVF","supports_powering_by_solar","FALSE"
    "R0000EVZVF","manufacturer","Tomy"
    "R0000EVZVF","product_weight","0.26"
    "R0000EVZVF","description","No mess fun for parent and baby that can be played with again and again. Fill the fun lilly pad with water and place little hands or feet on top to make fun hand and foot prints everywhere using only water! Have fun with your little one using just water then watch your prints magically fade away ready to enjoy again and again. Make fun prints and use the 2 stampers for even more fun! The magic mat then dries like new."
    "R0000EVZVF","supports_powering_by_mains","FALSE"
    "R0000EVZVF","manufacturer_part_number","71515"
    "R0000EVZVF","supports_powering_by_petrol","FALSE"
    "R0000EVZVF","supports_powering_by_computer","FALSE"
    "R0000EVZVF","contains_mains_adapter","FALSE"
    "R0000EVZVF","item_name","Tomy 71515 Be Baby - Aqua Splash and Print"
    "R0000EVZVF","number_of_batteries","0"
    "R0000EVZVF","category","activity-toys"
    "R0000EVZVF","vat_code_uk","standard_rate"
    "R0000EVZVF","gtin","505011666715158"
    "R0000EVZVF","supports_powering_by_lighter","FALSE"
    "R0000EVZVF","min_suggested_age","6"
    "R0000EVZVF","supports_powering_by_phantom_power","FALSE"
    "R0000EVZVF","supports_powering_by_phone","FALSE"
    "R0000EVZVF","supports_powering_by_battery","FALSE"

Offers
======

 - sftp.rangespan.com/data/rangespan/retailers/[retailer]/offers

Rangespan generates 4 files daily, with the latest pricing and inventory information.

Offers All - Overview
---------------------

.. csv-table::  
   :stub-columns: 1
   :widths: 20, 80

   "Type", "Rangespan Generated"
   "Description", "Pricing and inventory information. Updated 4 times a day (00h, 06h, 12h, 18h)."
   "Filename", "offers_all_[YYYYMMDD].csv"


Offers All - Example
--------------------
.. csv-table::
   :header: "rin","state","inventory","cost_ex_vat","cost_inc_vat","vat_amount","vat_rate","valid_from","valid_to","amazon_price"

   "R0000EW5RX","live","125","4.73","5.68","0.95","0.2","2013-12-17T00:00:00","2013-12-17T23:59:59",""
   "R0000EVZVF","live","78","9.5","11.4","1.9","0.2","2013-12-17T00:00:00","2013-12-17T23:59:59","13"

Orders
======

Retailers can place orders by dropping a properly formatted file into the relevant SFTP directory. Note that it is up to the retailer to get a succesful response from Rangespan: if there are errors in the file you drop, the associated orders will not be processed. You can see all ingested orders on our webiste:
https://www.rangespan.com/orders/retailer/


Place a new order - Overview
----------------------------

.. csv-table::  
   :stub-columns: 1
   :widths: 20, 80

   "Type", "Retailer Generated"
   "Description", "New orders, uploaded by Retailer"
   "Filename", "place_orders_[YYYYMMDD]_[HHMMSS].csv"


Place a new order - Example
---------------------------
.. csv-table::
   :header: "retailer_reference","rin","unit_cost_ex_vat","placed_date","quantity","customer_address_line_1","customer_address_line_2"

    "100019355","R0000XCA7J","","2014-02-07 00:00:00","1","B131, Macmillan house","Paddington Station"
    
(continued)

.. csv-table::
    :header: "customer_town","customer_county","customer_postcode","customer_country","customer_phone","customer_name","customer_email"

    "London","","W2 1FT","UK","02074022331 ","Mr T. Order","info@rangespan.com"

Place a new order - Responses
-----------------------------

The rangespan system check each FTP folder for an update every 10 minutes. The files are processed within a couple of minutes, and a response file is generated once that is complete. If there were **any** errors, the entire file will be rejected.

We have explicit error handling for the following:

- "Missing mandatory customer data" - The following customer data fields are mandatory ('name', 'address_line_1', 'town', 'country', 'postcode', 'email')
- "Missing retailer reference"
- "Placed date is too old" - Placed date must be within 7 days of ingestion date
- "Quantity must be greater than zero"  
- "Invalid RIN" - Retailer has not selected the given RIN
- "Unable to parse (placed_date|unit_cost_ex_vat)" - Input data is not formatted correctly
- "Offer unavailable" - not price exists for RIN / placed date
- "Retailer reference already exists" - an order with this reference was already submitted.


Order Notifications - Overview
------------------------------

.. csv-table::  
   :stub-columns: 1
   :widths: 20, 80

   "Type", "Rangespan Generated"
   "Description", "Order status for any orders that have changed in the last 24 hours, published by Rangespan daily"
   "Filename", "orders_all_[YYYYMMDD].csv"


Order Notfications - Example
----------------------------

.. csv-table::
   :header: "rangespan_reference", "retailer_reference","rin","state","quantity","unit_cost_ex_vat","vat_rate","customer_title","customer_address_line_1","customer_address_line_2", "customer_address_line_3"

    "12345","100019355","R0000XCA7J","processing","1","15.48","0.2","","B131, Macmillan house","Paddington Station",""

(continued)

.. csv-table::
    :header: "customer_town","customer_county",	"customer_country", "customer_postcode","customer_phone","customer_alternate_phone","customer_email"
    
    "London", "", "UK", "W2 1FT", "02074022331", "", "info@rangespan.com"

(continued)

.. csv-table::
    :header: "shipping_method",	"shipping_provider","shipping_reference","placed_date","created_date","shipping_date","promise_date","last_modified_date"
    
    "0", "Royal Mail", "RM12345", "2014-02-07 00:00:00", "2014-02-07 00:00:00", "", "2014-02-12 00:00:00", "2014-02-07 00:00:00"


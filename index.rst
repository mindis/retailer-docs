***********************************
Rangespan Retailer Integration Docs
***********************************

These articles will guide you through your interactions with the Rangespan system. If you have any questions, you can contact your account manager or retailers@rangespan.com. 

Features
========
See below details on how to:
 - Use Rangespan Search for market research
 - Launch new products
 - Update your product prices and availability
 - Place orders
 - Manage orders
 - Customer Service tools
 - Process Rangespan invoices

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


---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Context Sensitive Help
description: Welcome brave explorer to the Street As context sensitive help page. You most likely navigated to this page by clicking the help icon in Business Central (the one that looks like a question mark) and then clicking a link under the About apps on this page section. If the page you were looking at has a special topic dedicated to that page, you will have been taken straight to that topic heading when you clicked the link. If there is no dedicated help topic for the page you were on, you will have been shown the top of this page and will be reading this text, probably wondering why you are here, and what it was you were trying to do before you arrived.

# Author box
author:
    title:
    title_url: 
    external_url: 
    description: 

# Micro navigation
micro_nav: true

# Page navigation
page_nav:
    prev:
        content: New Zealand Postal Addresses
        url: /new-zealand-postal-addresses
    next:
        content: EULA
        url: /eula
---

# Address Format Callers

Every time an address is formatted for printing, the object and routine that called that address formatting code will get logged in this page. This means if you haven't run any of the reports that format addresses as part of their output after installing the Street As app, this list will be blank. The list will build up over time as each of the various reports get used.

Some of the reports have multiple formatted addresses on the single report and, in order to make this configuration work for any caller (of which there are many), I needed to make it refer to technical things like Object Type and Object Id. I also included the Procedure Name and Formatting For to allow different settings to be configured for each individual address that may appear on the report. It's unfortunate that this has to appear so complicated but, it can be extremely useful if you want to have slightly different layouts on some specific reports.

To illustrate how the set up is used, here's an example of some values and how they relate to out-of-the-box report layouts.

| Object Type | Object Id | Object Name | Procedure Name | Formatting For | Notes |
|-|-|-|-|-|-|
| Report | 1304 | "Standard Sales - Quote" | "Header - OnAfterGetRecord"(Trigger) | GetCompanyAddr | Your company's address in Company Information |
| Report | 1304 | "Standard Sales - Quote" | "Header - OnAfterGetRecord"(Trigger) | SalesHeaderBillTo | The bill-to address from the Sales Quote |
| Report | 1304 | "Standard Sales - Quote" | "Header - OnAfterGetRecord"(Trigger) | SalesHeaderShipTo | The ship-to address from the Sales Quote |

For each of the options in the list you can specify settings that will override the default behaviour specified on the Street As Setup page.

# Bank Account Card

# Blanket Sales Order

# Company Information

The company address and ship-to address have changed to allow New Zealand address formats to be entered. See [New Zealand Address Format](/new-zealand-postal-addresses) for more details.

| Some Table Column | Second Column | Third Column |
|-|-|
| This is a whole load of text that is meant to fit in one column. | Column two text. Not nearly so big. | 3 |
| 2 | Column two text. Not nearly so big. | This is a whole load of text that is meant to fit in one column. |
| This is a whole load of text that is meant to fit in one column. | Column two text. Not nearly so big. | 3 |

## General

The `Country/Region Code` field has moved to appear before the first of the address fields in the General tab and all of the address fields have moved to be within a group that will either display **New Zealand Address** if the Country/Region Code matches a country that has a Country Address Format of *New Zealand*, or will display **Address** if the Country Address Format is set to *Other*. 

The [Country/Region Code](## "Specifies the country or region of the address. Set this value first to ensure other postal address fields are displayed correctly for the country selected.") field has moved to appear before the first of the address fields in the General tab and all of the address fields have moved to be within a group that will either display **New Zealand Address** if the Country/Region Code matches a country that has a Country Address Format of *New Zealand*, or will display **Address** if the Country Address Format is set to *Other*. 

## Shipping

The **Ship-to Country/Region Code** field has moved to appear before the first of the ship-to address fields in the Shipping tab and all of the ship-to address fields have moved to be within a group that will either display **New Zealand Address** if the Ship-to Country/Region Code matches a country that has a Country Address Format of *New Zealand*, or will display **Address** if the Country Address Format is set to *Other*.

# Countries/Regions

The Countries/Regions page has a new **Country Address Format** field that will control how addresses will be displayed on pages that show an address and how the addresses will be formatted on printed reports. Currently only two options are available:

- Other
- New Zealand

With the option set to *Other* the system will behave as it did before Street As was installed. All address-formatting options will be in affect. When the option is set to *New Zealand* the standard address formatting fields such as **Address Format** and **Contact Address Format** will be ignored and the New Zealand address formatting will be used. See *New Zealand Address Format* for more details.

# Customer Card

There are some extra fields on the customer card. Deal with it

# Sales Credit Memo

# Sales Invoice

# Sales Order

# Sales Quote

# Sales Return Order

# Street As Setup

## New Zealand Country Code

Specifies the Country/Region Code that is used to identify whether the New Zealand address format should be used. A New Zealand address format includes the ability to lookup a suburb code as well as removing the standard post code/city validation. To allow blank country codes to use the New Zealand address format, set the Default Country Address Format to New Zealand too.

## Include Contact

Specifies whether the contact should be included as the recipient in the formatted address. The options are applied to all printed address, although this setting can be overridden on individual reports using the [Address Format Callers](#address-format-callers) list page.

## Default Country Address Format

Specifies the country address format that will be used when the country/region code is left blank. This should be set to match the country in which your company is located.

# New Zealand Address

It's a nice page isn't it. :-)

# Vendor Card

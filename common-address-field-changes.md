---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Common Address Field Changes
description: This section describes the changes to page layouts that have been made to accommodate a New Zealand address. To make integration with other systems continue to work we have used the same fields as the standard addresses but have changed the caption of the fields to reflect the new usage.

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
        content: Context Sensitive Help
        url: /context-sensitive-help
    next:
        content: EULA
        url: /eula
---

# Introduction

There are over sixty pages in Business Central that display an address and, with a few exceptions, they follow a standard pattern. Some pages include multiple addresses (such as orders with a Sell-to, Bill-to, and Ship-to Address). Street As includes changes to every page that shows an address and tries to keep the changes to a minimum. Most pages follow the common changes described below.

# Common Address Changes

Wherever an address is displayed on a page, the **Country/Region Code** field has moved to the start of the address. This is necessary because it is the country field that controls which other fields should be displayed. The following table shows the field captions for countries other than New Zealand (called _Other Country Field Name_) in comparison to how the same field is re-captioned (shown as _New Zealand Field Name_). New Zealand addresses have additional behaviour on the address fields which is described in the _New Zealand Behaviour_ column.

| Other Country Field Name | New Zealand Field Name | New Zealand Behaviour |
|-|-|-|
| Address   | Address      | Use assist edit button to set Unit Line, Building, and Delivery. |
| Address 2 | Suburb       | Use the lookup button to select from available suburbs. |
| City      | Town or City |  |
| County    |  | This field is not shown for a New Zealand address. |
| Post Code | Postcode |  |

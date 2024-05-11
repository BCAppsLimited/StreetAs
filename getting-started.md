---
# Page settings
layout: default
keywords:
comments: true

# Hero section
title: Getting Started
description:  In this section you'll find basic information about Street As and how to install it and use it properly. If you're a first time user, you should read this Getting Started section first.

# Author box
author:
    title: 
    title_url: 
    external_url: false
    description: 

# Micro navigation
micro_nav: true

# Page navigation
page_nav:
    prev:
        content: Home
        url: /
    next:
        content: Clever Stuff
        url: /advanced-configuration-options
---

# What is Street As?

Street As changes the layout of all[^1] pages that include address fields so they are better suited for New Zealand Addresses. Once activated, all address pages will show:

- **Address**
- **Suburb**
- **Town or City**
- **Postcode**

The **Country/Region** code that controls how an address is displayed has also moved so that it appears before the first address field. You can configure the system so that leaving the **Country/Region** field empty will treat the address like it's a New Zealand address.

There are some more advanced features that are covered in the [Clever Stuff](/StreetAs/advanced-configuration-options) section, but for now, let's get you going with the basic setup.

# Installation and Configuration

Street As is available with a free trial through [Microsoft's AppSource](https://appsource.microsoft.com/en-US/marketplace/apps?product=dynamics-365-business-central). 

After the app is installed, search for Street As Setup[^2] and launch the setup page. There's not a lot to enter here, in fact you can get up and running by setting only two fields.

## Street As Setup

### Step 1. Set the New Zealand Country Code

That's right, your first task is to see if you can correctly identify the country code that is used to represent New Zealand. If your system has been configured well it will most likely use the ISO 2- or 3-character codes of NZ or NZL. Use the lookup to select the correct value if you're unsure. Once the **New Zealand Country Code** field contains a value, you can continue to step 2.

### Step 2. Activate the app

Click on the **Active** toggle button so activate the app. Once the app is active, the layout of pages will change for any address that has the country/region code set to the value you selected in the **New Zealand Country Code** field.

### Step 3. Set the Default Country Address Format

This step is optional but extremely useful. If you want an address that does not have a **Country/Region** code specified (for example when creating a new customer), you can use this field to tell the system to treat addresses with no country specified as New Zealand addresses. There are only two options for this setting: _Other_, and _New Zealand_. I recommend you set this field to _New Zealand_.

### Advanced options

There are more fields to configure on the **Recipient** tab but these are optional and might take a little more consideration to use them properly. Essentially the settings here will allow you to determine how a contact name should be included in the printed address when documents are generated. We'll cover this in detail in the [Clever Stuff](/StreetAs/advanced-configuration-options) section and you can also find out about all of the fields and actions on this page in the [Street As Setup Page Help](/StreetAs/context-sensitive-help/#street-as-setup).

# Licensing

In order to use the Street As app, users must have a license assigned to their user account. If a user does not have a license assigned, the behaviour of the system will be the same as if the app was not active. This means the user will see the standard address fields on pages that contain addresses and documents that use addresses will be formatted according to the standard configuration options.

---

[^1]: There are currently 66 pages with updated address fields. If you find a page that you would like to be included, please log an issue by clicking the LOG ISSUE link at the top right of this page (a github user account is required to log an issue).
[^2]: Use the Alt+Q key combination or click on the magnifying glass icon in the top bar to launch the "Tell me what you want to do" search box. The search feature is a little bit smart and you can usually get away with just typing the start of the words you are looking for. I usually just type "Street Setup" to quickly get to the setup screen.
[^3]: That's right, your first configuration task is going to see if you can correctly identify New Zealand in a list of countries.
[^4]: Use the Alt+Q key combination or click on the magnifying glass icon in the top bar to launch the "Tell me what you want to do" search box. The search feature is a little bit smart and you can usually get away with just typing the start of the words you are looking for.
[^5]: The biggest cost is the code-signing certificate. Then there's the domain name, the Microsoft 365 subscription, the template used to make the online help. Not to mention the time invested in building the app and keeping it up to date with the latest versions of Business Central. I feel a sales pitch coming on...  
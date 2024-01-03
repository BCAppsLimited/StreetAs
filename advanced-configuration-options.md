---
# Page settings
layout: default
keywords:
comments: true

# Hero section
title: Clever Stuff
description: Read this section for more advanced setup options like controlling whether a recipient should appear, or how to override default settings for specific reports.

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
        content: Getting Started
        url: /getting-started
    next:
        content: New Zealand Postal Addresses
        url: /new-zealand-postal-addresses
---

# What is Street As?

It's easiest to describe Street As in terms of what it does. Here's a list of features.

- Allow a country (in Countries/Regions[^1] list) to be configured as having a _Country Address Format_ of "New Zealand".
- Change the various screens that allow addresses to be entered to show the fields needed for a New Zealand postal address.
- Add a lookup to a list of Suburbs to the Suburb field (aka _Address 2_).
- Validate a partial Suburb match and fill in the Town or City and Postcode fields.
- Allow the delivery line of an address (aka _Address_) to be split into three lines for Unit Line, Building, and Delivery when printed.
- Modify all reports that use the standard address formatting routines to format New Zealand addresses correctly.
- Allow contacts to be included in a line at the top of the address based on a starting text of Attn., C/O, C/-, or any other secret incantation you care to invoke.
- Allow inclusion of contacts in a printed address to be overridden on a report-by-report basis.
- Allow the _Default Country Address Format_ to be specified for your company so the system will treat a blank country code as being in this format.

# Why is it free?

After typing that list of features I'm beginning to wonder that myself. It seems like Street As is a pretty neat app and should be worth a few bucks, right? There are costs associated with publishing an app and keeping it updated in AppSource[^3]. But what if no-one uses this app because they don't think it's worth spending money on? I hate the idea of putting so much effort into building an app and no-one using it simply because it costs a few dollars. Getting businesses to part with their money is sometimes hard. Street As is intended to make using Business Central a little bit less annoying and doesn't promise great gains in productivity or a huge return on investment. So it's free (as in beer). Enjoy!

I've made Street As include a screen showing all of the apps available from BC Apps and some of those apps will not be free. Search for "BC Apps Management" (after you've installed the app of course) and take a look. Maybe you'll find something that you would find useful (and would like to spend money on). I'll also send you a notification if a new app gets added (or there's an update to an app that might interest you). Finally, if you do use Street As and you like it, leave a review on AppSource.

# Installation

Street As is available for free through [Microsoft's AppSource](https://appsource.microsoft.com/en-US/marketplace/apps?product=dynamics-365-business-central). If you've already installed the app, jump ahead to the [Configuring](#configuring) section. You can [install the app from AppSource](##appsource) or from within [Business Central](##business-central).

## AppSource

Open the [Street As](#) product page on AppSource and click on the *Get it now* button. You will be redirected to your Business Central instance where you will

## Business Central

Sign in to Business Central and search[^2] for "extension marketplace".  

# Configuring

Todo: Some configuration instructions

---

[^1]: You may wonder why we did it this way. After all, there is only one _New Zealand_ so why make you pick which one it is? If we add another country format to Street As (no promises), this approach makes it easier.
[^2]: Use the Alt+Q key combination or click on the magnifying glass icon in the top bar to launch the "Tell me what you want to do" search box. The search feature is a little bit smart and you can usually get away with just typing the start of the words you are looking for.
[^3]: The biggest cost is the code-signing certificate. Then there's the domain name, the Microsoft 365 subscription, the template used to make the online help. Not to mention the time invested in building the app and keeping it up to date with the latest versions of Business Central. I feel a sales pitch coming on...  
---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: New Zealand Postal Addresses
description: Learn about rural delivery routes, postal services, and why suburbs must be specified unless they're not needed.

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
        content: Clever Stuff
        url: /advanced-configuration-options
    next:
        content: Context Sensitive Help
        url: /context-sensitive-help
---

# Address Types

New Zealand postal addresses come in three flavours: urban, rural, and delivery service. You don’t really need to know this, but it helps to make the structure of address lines easier to explain if they’re handled in these three categories. For the most part, when dealing with businesses and their addresses, you’ll be dealing with urban addresses or delivery services. Depending on your business (if you have a lot of regular households as customers for instance) you may use rural addresses a fair bit. 

One easy way to differentiate between the three types of address is: 

- An **urban address** will often have a **suburb** before the town or city and postcode. 
- A **delivery service** will have **PO Box** number (there are also options of Private Bag, Response Bag, CMB, Counter Delivery, and Poste Restante, although we had to look that last one up it’s so rarely used). 
- A **rural address** will have an **RD** number. 

The following lines are used to create a New Zealand postal address: 

- Reference
- Recipient 
- Unit 
- Building Name 
- Delivery 
- Suburb 
- Town or City and Postcode 
- Country 

That’s an awful lot of lines. Let’s take a look at how addresses are made up in Business Central. We have up to eight lines of an address and this can be made up from the following fields: 

- Name 
- Name 2 
- Contact 
- Address 
- Address 2 
- City 
- Post Code 
- County 
- Country Code 

There are some configuration options and settings within standard Business Central that you can use to configure which fields will be used and how they will be structured in printed addresses, but the options don’t really suit the NZ address format. For example, we never use the County field, so that’s right out. And, according to NZ Post, the Country should only be shown if it’s not a New Zealand address. The Name and Contact could be used to fill in our Reference (from the Contact) and Recipient (from the Name field). The following table illustrates the way the New Zealand address lines are mapped to Business Central fields in **Street As**: 


| NZ Address Line |  BC Field Name | Example | 
|-----------------|----------------|---------|
| Reference       | **Contact**    | Attn Mr. Dent | 
| Recipient | **Name** | Dent & Prefect Limited | 
| Unit | Part 1 of **Address** | Level 2 | 
| Building Name | Part 2 of **Address** | Trillian Astra House |
| Delivery | Part 3 of **Address** | 42 Meaningful Street |
| Suburb | **Address 2** | Bryndwr | 
| Town or City and Postcode | **City** and **Post Code** | Christchurch 8053 |
| Country | **Country/Region Code** | | 

That’s a reasonable mapping but we have quite a lot of weight being carried by the **Address** field as it’s being used for Unit, Building Name, and Delivery. NZ Post say that punctuation must not be used in the address lines, but I’ve studied enough real-world examples of addresses in New Zealand to know that when it comes to postal addresses, rules are there to be broken. Street As will split the Address line into three separate lines if you separate Unit, Building Name, and Delivery with commas. 

To make it easier to enter this complex address line, we’ve added an assist edit page that will put the commas in for you. 

![Image showing an address field and how the three parts split into three lines.](/screenshots/StreetAsAddressSplit.png)

There are options in the advanced configuration section that allow you to decide whether the Address line should be split into separate lines when a document is printed either as a default setting for the entire company (managed on the Street As Setup page) or for individual addresses in specific reports (managed on the Address Format Callers page). 

When it comes to the standard behaviour of Business Central and addresses, the relationship between Post Code, City, County, and Country/Region doesn’t work that well for New Zealand postal addresses. By default, you can set up your Post Codes with a link to a City and County. If you enter a Post Code that cannot be found in the setup, the system will throw an error and demand that you create the Post Code before you can continue. In some ways this error is a protection against entering invalid data, but at the same time it’s forcing the user to enter the same data more than once. Also, we don’t use the County field in New Zealand addresses but there’s no support for Suburb so we’re not validating that I’m entering the correct post code for the suburb. This also means if we use the lookup to select a Post Code, we might get thirteen different post codes all for Christchurch. Which one should we use?  

What if we used the County field as the suburb? Genius! This way we’ll be able to see what the different post codes mean. We can even change the caption of the County field in the standard setup so it is called Suburb instead of County and this setting is country specific. That seems close to what we need, but there’s a problem with this approach. 

The primary key (the combination of fields that differentiates one record from another) for the Post Code table is the Code and the City. That means you can’t have these records stored in the database because they violate the primary key: 

| County (suburb really) | City | Postcode | 
|-|-|-|
| Bottle Lake        | Christchurch | 8083 | 
| Brooklands         | Christchurch | 8083 | 
| Burwood            | Christchurch | 8083 | 
| Kainga             | Christchurch | 8083 | 
| Marshland          | Christchurch | 8083 | 
| New Brighton       | Christchurch | 8083 | 
| North New Brighton | Christchurch | 8083 | 
| Ouruhia            | Christchurch | 8083 | 
| Parklands          | Christchurch | 8083 | 
| Shirley            | Christchurch | 8083 | 
| Spencerville       | Christchurch | 8083 |
| Styx               | Christchurch | 8083 |
| Waimairi Beach     | Christchurch | 8083 | 

But those are real suburb, city, and postcode combinations. “Aha!” we hear you cry, what if we were to enter the suburb into the City field and the City into the County field and we change the Caption of the County field to be Suburb? Well that would mean that on your pages that store addresses you now have two fields called City and one of them is really the County. It’s a bit of mess. This is why we created Street As. 

Finally, in order to make life easier still, we’ve made a lookup feature for the Address 2 field (which we’ve re-captioned as “Suburb”) so that you can select the correct suburb from the list and the Town or City and Postcode will be automatically populated. If you type the start of the suburb and activate the lookup (we use Alt+Down Arrow) the list will show you the first entry that matches what you typed. For example, typing “bry” and pressing Alt+Down Arrow will show the following. 

![Image showing the New Zealand Suburbs page filtered for a match on "bry".](/screenshots/StreetAsBryLookup.png)

We’ve prepared a starter data file with the list of suburbs which you can download from our website, eventually this will be imported automatically when you install the app. To learn how to set up your suburbs, see [Setup Suburbs Data](/StreetAs/advanced-configuration-options/#setup-suburbs-data) in the Clever Stuff section.

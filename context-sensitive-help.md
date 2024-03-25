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
        content: Common Address Field Changes
        url: /common-address-field-changes
---

# Address Format Callers

Every time an address is formatted for printing, the object and routine that called that address formatting code will get logged in this page. This means if you haven't run any of the reports that format addresses as part of their output after installing the Street As app, this list will be blank. The list will build up over time as each of the various reports get used.

Some of the reports have multiple formatted addresses on the single report and, in order to make this configuration work for any caller (of which there are many), I needed to make it refer to technical things like Object Type and Object Id. I also included the Procedure Name and Formatting For to allow different settings to be configured for each individual address that may appear on the report. It's unfortunate that this has to appear so complicated but, it can be extremely useful if you want to have slightly different layouts on some specific reports.

To illustrate how the set up is used, here's an example of some values and how they relate to out-of-the-box report layouts. Note that each of the rows shown here have:

- Object Type = Report
- Object Id = 1304
- Object Name = "Standard Sales - Quote"
- Procedure Name = "Header - OnAfterGetRecord"(Trigger) 

I have removed those columns from the sample to conserve space.

| Formatting For | Notes |
|-|-|
| GetCompanyAddr | Your company's address in *Company Information*. |
| SalesHeaderBillTo | The bill-to address from the Sales Quote. |
| SalesHeaderShipTo | The ship-to address from the Sales Quote. |

<div class="callout callout--info">
    <p><strong>Top Tip</strong> If you're not 100% sure which of the addresses on the printed report corresponds to which of the <em>Formatting For</em> values, you can use the settings of the contact to identify which address is which. For example:</p>

<table>
  <thead>
    <tr>
      <th>Formatting For</th>
      <th>Include Contact as Recipient</th>
      <th>Recipient</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>GetCompanyAddr</td>
      <td>Use Specified</td>
        <td>COMPANY ADDRESS</td>
    </tr>
    <tr>
      <td>SalesHeaderBillTo</td>
      <td>Use Specified</td>
        <td>BILL TO</td>
    </tr>
    <tr>
      <td>SalesHeaderShipTo</td>
      <td>Use Specified</td>
        <td>SHIP TO</td>
    </tr>
  </tbody>
</table>
</div>

For each of the options in the list you can specify settings that will override the default behaviour specified on the [Street As Setup](#street-as-setup) page. The option for *Include Contact as Recipient* has the following possible values and meanings:

| Value | Meaning |
| - | - |
| Default Setup | Use whatever settings existing on the Street As Setup to control how the recipient line is displayed. |
| Never | The recipient line for this address will never be included. |
| Always | The recipient line for this address will always be included. |
| Only When Matches RegEx | The recipient line for this address will only be included when it matches the regular expression that is defined on the Street As Setup page. |
| Use Specified | The recipient line always be included for this address and will always show the value specified in the *Use Specified* field. |

# Alternative Address Card

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Bank Account Card

The address fields on the **Communication** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).


# Blanket Purchase Order

The blanket purchase order page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses have been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

There is a perculiar side-effect related to the pay-to address fields. If you use the lookup against the **Name** field within the **Pay-to** group on the **Shipping and Payment** tab and select a different pay-to vendor that has an address that is for a different country format (i.e. you went from a NZ address to a non-NZ address or vice-versa) then the address fields for the **Pay-to** to group will not update to reflect the change. You can get the correct fields to display by simply pressing the F5[^1] key to refresh the page in your browser. If however, you typed the name of the vendor rather than using the lookup, the refresh will work correctly. There are technical reasons[^2] for this limitation in the current version of BC and rather than try to find a programming work-around, I decided[^3] to leave this behaviour as it was.

# Blanket Purchase Order Archive

The blanket purchase order archive page has addresses for buy-from (**General** tab), ship-to (**Shipping** tab), and pay-to (**Invoicing** tab)[^4]. Each of the three sets of addresses have been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). Unlike the blanket purchase order page, the blanket purchase order archive does not require the **Show more** to show the full address, however, for some bizarre reason the county fields are not shown in the address.[^5]  

# Blanket Sales Order

The blanket sales order page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses have been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

There is a perculiar side-effect related to the bill-to address fields. If you use the lookup against the **Name** field within the bill-to group on the **Shipping and Billing** tab and select a different bill-to customer that has an address that is for a different country format (i.e. you went from a NZ address to a non-NZ address or vice-versa) then the address fields for the bill-to to group will not update to reflect the change. You can get the correct fields to display by simply pressing the F5 key to refresh the page in your browser. If however, you typed the name of the customer rather than using the lookup, the refresh will work correctly. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

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

# Customer Card

There are some extra fields on the customer card. Deal with it

# Sales Credit Memo

# Sales Invoice

# Sales Order

# Sales Quote

# Sales Return Order

# Street As Setup

## New Zealand Country Code

Specifies the Country/Region Code that is used to identify whether the New Zealand address format should be used. A New Zealand address format includes the ability to lookup a suburb code as well as removing the standard post code/city validation. To allow blank country codes to use the New Zealand address format, set the *Default Country Address Format* to New Zealand.

## Include Contact as Recipient

Specifies whether the contact should be included as the recipient in the formatted address. The options are applied to all printed address, although this setting can be overridden on individual reports using the [Address Format Callers](#address-format-callers) list page. The option for *Include Contact* has the following possible values and meanings:

| Value | Meaning |
| - | - |
| Never | The recipient line for New Zealand addresses will never be included. |
| Always | The recipient line for New Zealand addresses will always be included. |
| Only When Matches Regular Expression | The recipient line for New Zealand addresses will only be included when it matches the regular expression that is defined in the *Recipient Regular Expression* field. |

## Default Country Address Format

Specifies the country address format that will be used when the country/region code is left blank. This should be set to match the country in which your company is located.

## Recipient Regular Expression

This field value is used in conjunction with the *Only When Matches Regular Expression* setting on the *Include Contact as Recipient* field. Regular expressions are an incredibly powerful way to specify a formula for matching to some text. The default setting for this field is `^Attn |^C\/- |^C\/O` and you can restore this default value by using the action on this page and selecting *Actions > Set Default Recipient Regular Expression*. For more information on using regular expressions and some examples of how this default regular expression works, take a look at this [Regular Expressions 101 Saved Example](https://regex101.com/r/VkBQx8/1).

<div class="callout callout--info">
    <p><strong>Regular Expressions</strong>The previous link will take you to the regex101.com site with a saved example that shows how the default regular expression will match against the following list of candidates.</p>

<ul>
<li>Bond, James Bond</li>
<li><mark>Attn </mark>Miss Moneypenny</li>
<li><mark>C/- </mark>Mr Bill Tanner</li>
<li><mark>C/O </mark>Ms Mary Goodnight</li>
</ul>
</div>

# Location Card

When the Country/Region Code relates to New Zealand the Address group caption changes to New Zealand Address and the Address, Suburb, Town or City, Postcode fields are shown in place of the regular address fields.

# New Zealand Address

It's a nice country. Changed content.

# Vendor Card


[^1]: Or Cmd+R if you're using a Mac.

[^2]: The lookup trigger is on the table field and not the page field. There is currently no way for a page extension to detect that a record has changed as a result of a lookup trigger that executes on the table field.

[^3]: I could create a new field to replace the Name field and then call the same lookup code that exists on the table field and use this to refresh the page once the lookup has completed. I decided against this approach (even though it worked OK) because it added a change that might cause complications if changes are made to the standard application in this area. Considering the obscure scenario that will trigger this odd behaviour and the fact there is a simple standard work-around (just refresh the browser) helped me to decide to minimise the changes and live with this odd glitch.

[^4]: I know right! The archive has different fields and layout compared to the unarchived document. Weird.

[^5]: I've made a note to log this with Microsoft. Who know's by the time you're reading this, it may have been fixed already and you're wondering what on earth I'm talking about.
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

The blanket purchase order page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

There is a perculiar side-effect related to the pay-to address fields. If you use the lookup against the **Name** field within the **Pay-to** group on the **Shipping and Payment** tab and select a different pay-to vendor that has an address that is for a different country format (i.e. you went from a NZ address to a non-NZ address or vice-versa) then the address fields for the **Pay-to** to group will not update to reflect the change. You can get the correct fields to display by simply pressing the F5[^1] key to refresh the page in your browser. If however, you typed the name of the vendor rather than using the lookup, the refresh will work correctly. There are technical reasons[^2] for this limitation in the current version of BC and rather than try to find a programming work-around, I decided[^3] to leave this behaviour as it was.

# Blanket Purchase Order Archive

The blanket purchase order archive page has addresses for buy-from (**General** tab), ship-to (**Shipping** tab), and pay-to (**Invoicing** tab)[^4]. Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). Unlike the blanket purchase order page, the blanket purchase order archive does not require the **Show more** to show the full address, however, for some bizarre reason the county fields are not shown in the address.[^5]  

# Blanket Sales Order

The blanket sales order page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

There is a perculiar side-effect related to the bill-to address fields. If you use the lookup against the **Name** field within the bill-to group on the **Shipping and Billing** tab and select a different bill-to customer that has an address that is for a different country format (i.e. you went from a NZ address to a non-NZ address or vice-versa) then the address fields for the bill-to to group will not update to reflect the change. You can get the correct fields to display by simply pressing the F5 key to refresh the page in your browser. If however, you typed the name of the customer rather than using the lookup, the refresh will work correctly. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Blanket Sales Order Archive

The blanket sales order archive page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). Unlike the blanket sales order page, the blanket sales order archive does not require the **Show more** to show the full address, however, once again the county fields are not shown in the address for non-New Zealand addresses.  

# Company Information

The company information page has addresses for the company (**General** tab) and ship-to address (**Shipping** tab). Each of the addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). There is a bug on the standard version of this page (that may be fixed by the time I release this app) that causes the Ship-to County to show/hide incorrectly (currently this value toggles depending on the setting of the Country/Region Code and not the Ship-to Country/Region Code). You'd only find this bug if your company existed in one country and had a ship-to address in another country and those two countries had different rules about whether the county field should be shown.

# Contact Alt. Address Card

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Contact Card

The address fields on the **Communication** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Customer Bank Account Card

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Customer Card

The address fields on the **Address & Contact** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Customer Templ. Card

The address fields on the **Address & Contact** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Employee Card

The address fields on the **Address & Contact** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Filed Service Contract

The filed service contract page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).  

# Finance Charge Memo

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Issued Finance Charge Memo

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Issued Reminder

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Job Card

The job card page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Invoice and Shipping** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

The job card supports *Default (Customer)*, *Custom Address*, and *Another Customer* as options for the **Bill-to** address and the address fields will only be shown when the option is *Custom Address* or *Another Customer*. In addition, the **Ship-to** address supports *Default (Sell-to Address)*, *Custom Address*, and *Alternate Shipping Address*. The address fields are only shown for *Custom Address* and *Alternate Shipping Address*. There is a perculiar side-effect related to the bill-to address fields. If you use the lookup against the **Name** field within the bill-to group on the **Invoice and Shipping** tab and select a different bill-to customer that has an address that is for a different country format (i.e. you went from a NZ address to a non-NZ address or vice-versa) then the address fields for the bill-to to group will not update to reflect the change. You can get the correct fields to display by simply pressing the F5 key to refresh the page in your browser. If however, you typed the name of the customer rather than using the lookup, the refresh will work correctly. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Location Card

The address fields on the **Address & Contact** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Order Address

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Posted Direct Transfer

The posted direct transfer page has addresses for transfer-from (**Transfer-from** tab) and transfer-to (**Transfer-to** tab). Both of the addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Posted Purchase Credit Memo

The posted purchase credit memo page has addresses for buy-from (**General** tab), ship-to, and pay-to (**Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Purchase Invoice

The posted purchase invoice page has addresses for buy-from (**General** tab), ship-to, and pay-to (**Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Purchase Receipt

The posted purchase receipt page has addresses for buy-from (**General** tab), ship-to (**Shipping** tab), and pay-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Return Receipt

The posted return receipt page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Return Shipment

The posted return shipment page has addresses for buy-from (**General** tab), ship-to (**Shipping** tab), and pay-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Sales Credit Memo

The posted sales credit memo page has addresses for sell-to (**General** tab), ship-to, and bill-to (**Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Sales Invoice

The posted sales invoice page has addresses for sell-to (**General** tab), ship-to, and bill-to (**Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Sales Shipment

The posted sales shipment page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Service Credit Memo

The posted service credit memo page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Posted Service Invoice

The posted service invoice page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).[^6] 

# Posted Service Shipment

The posted service shipment page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Posted Transfer Receipt

The posted transfer receipt page has addresses for transfer-from (**Transfer-from** tab) and transfer-to (**Transfer-to** tab). Each of the two sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Posted Transfer Shipment

Welcome to the wild world of transfer shipment pages, where the **Transfer-from** tab and the **Transfer-to** tab are not just tabs – they're destinations on a thrilling journey of address discovery! Imagine, if you will, a place where addresses morph and twist with the excitement of a spy changing disguises. That's right, each set of addresses has undergone a magical transformation to showcase the most [common address changes](/StreetAs/common-address-field-changes#common-address-changes), making them the chameleons of the shipping world. So, buckle up and enjoy the ride as you navigate through the ever-shifting landscape of our transfer shipment page – it's like a party where the addresses are the guests of honor, and you're the host with the most![^7]

# Purchase Credit Memo

The purchase credit memo page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

There is a perculiar side-effect related to the pay-to address fields. If you use the lookup against the **Name** field within the **Pay-to** group on the **Shipping and Payment** tab and select a different pay-to vendor that has an address that is for a different country format (i.e. you went from a NZ address to a non-NZ address or vice-versa) then the address fields for the **Pay-to** to group will not update to reflect the change. You can get the correct fields to display by simply refreshing the page in your browser. If however, you typed the name of the vendor rather than using the lookup, the refresh will work correctly. This behaviour is similar to that described for the blanket purchase order page.

# Purchase Invoice

The purchase invoice page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

Due to the way pay-to addresses are handled, if the correct address fields don't show after you have changed the address country, refresh your browser. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Purchase Order

Welcome to the whimsical world of purchase orders, where addresses hop around like a game of musical chairs! On the **General** tab, you'll find the buy-from address, probably sipping tea and minding its own business. Then there's the ship-to and pay-to addresses, lounging on the **Shipping and Payment** tab like they own the place. They've all had a makeover to show off their [common address changes](/StreetAs/common-address-field-changes#common-address-changes), but they're shy, so they'll only reveal a few details unless you coax them with the **Show more** button.

Now, here's the kicker: the pay-to address fields have a quirky little quirk. If you play detective and use the lookup to find a new pay-to vendor, and they happen to live in a different country format (like swapping a kiwi address for a non-kiwi one), the pay-to fields throw a tantrum and refuse to update. It's like they're stuck in an address identity crisis! But fear not, a simple page refresh is like a magic wand that sets everything right. Unless, of course, you went old-school and typed the vendor's name manually—then the refresh works as smoothly as a penguin on ice. This odd behavior is like the distant cousin of what happens on the [Blanket Purchase Order](#blanket-purchase-order) page, equally peculiar but part of the family. So next time you're navigating the thrilling saga of purchase orders, remember: a little refresh goes a long way, and always keep an eye on those sneaky address fields!

# Purchase Order Archive

The purchase order archive page has addresses for buy-from (**General** tab), ship-to (**Shipping** tab), and pay-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Purchase Quote

The purchase quote page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

Due to the way pay-to addresses are handled, if the correct address fields don't show after you have changed the address country, refresh your browser. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Purchase Quote Archive

In the shadowy corners of the purchase quote archive page, a mystery most peculiar unfolded. The **General** tab, a notorious character known for its buy-from addresses, had undergone a transformation as enigmatic as a chameleon at a grand fireworks display. Meanwhile, the **Shipping** tab, a once-trustworthy informant for ship-to locations, now whispered of changes, its words as slippery as a vat of jellied eels. And let's not forget the **Invoicing** tab, that keeper of pay-to secrets, which now paraded new addresses with the flamboyance of a peacock at a masquerade ball. Each tab, in a display of coordinated mischief, showcased the [common address changes](/StreetAs/common-address-field-changes#common-address-changes), leaving the users to deduce the truth behind this address alteration whodunit. The plot thickens, dear Watson, as we navigate the labyrinth of links to unveil the mastermind of this caper.

# Purchase Return Order

The purchase return order page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

Due to the way pay-to addresses are handled, if the correct address fields don't show after you have changed the address country, refresh your browser. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Purchase Return Order Archive

The purchase return order archive page has addresses for buy-from (**General** tab), ship-to, and pay-to (both on the **Shipping and Payment** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected. 

# Reminder

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Remit Address

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Resource Card

The address fields on the **Personal Data** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Responsibility Center Card

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Sales Credit Memo

The sales credit memo page has addresses for sell-to (**General** tab) and bill-to (**Billing** tab). Each of the addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Sales Invoice

The sales invoice page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected.

Due to the way bill-to addresses are handled, if the correct address fields don't show after you have changed the address country, refresh your browser. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Sales Order

The sales order page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected.

Due to the way bill-to addresses are handled, if the correct address fields don't show after you have changed the address country, refresh your browser. The reasons for this are explained more in the [Blanket Purchase Order](#blanket-purchase-order) description.

# Sales Order Archive

The sales order archive page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). Unlike the sales order page, the sales order archive does not require the **Show more** to show the full address.  

# Sales Quote

The sales quote page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected.

# Sales Quote Archive

The sales quote archive page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). 

# Sales Return Order

The sales return order page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes) and also only show a limited set of address fields unless the **Show more** option is selected.

# Sales Return Order Archive

The sales return order archive page has addresses for sell-to (**General** tab), ship-to, and bill-to (both on the **Shipping and Billing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Service Contract

The service contract page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). This page is a little unusual in that the addresses cannot be changed on the page but are shown as lookup fields from the related customer or in the case of the ship-to address the customer and the ship-to code.

# Service Contract Quote

The service contract quote page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes). This page is a little unusual in that the addresses cannot be changed on the page but are shown as lookup fields from the related customer or in the case of the ship-to address the customer and the ship-to code.

# Service Credit Memo

The service credit memo page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Service Invoice

The service invoice page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Service Item Card

The service item card page has addresses for sell-to (**Customer** tab), and ship-to (**Shipping** tab). Each of the addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Service Order

The service order page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Service Quote

The service quote page has addresses for sell-to (**General** tab), ship-to (**Shipping** tab), and bill-to (**Invoicing** tab). Each of the three sets of addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Ship-to Address

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Street As Setup

## New Zealand Country Code

Specifies the Country/Region Code that is used to identify whether the New Zealand address format should be used. A New Zealand address format includes the ability to lookup a suburb code as well as removing the standard post code/city validation. To allow blank country codes to use the New Zealand address format, set the *Default Country Address Format* to New Zealand.

## Active

A tick box that indicates the Street As functionality is active. In order to activate the extension, you must have specified the **New Zealand Country Code** first. If the **Active** field is not on, the appearance of address fields on all other pages will use the standard field captions and visibility. The country code will still be at the start of each address regardless of whether this extension is active or not.

## Default Country Address Format

Specifies the country address format that will be used when the country/region code is left blank. This should be set to match the country in which your company is located. The options available are *Other* and *New Zealand*.

## Keep Single Delivery Line

An address line for a New Zealand address can comprise a **Unit Line**, **Building**, and **Delivery**. These values are all entered in to the single Address field and are separated by a comma. When the address is formatted for printing, the default behaviour is to split the three fields into separate lines. If you would like to keep **Address** field as it was entered with commas and all, tick this box to set a new default behaviour. It is possible to override this setting for individual reports using the [Address Format Callers](#address-format-callers) list page.

## Include Contact as Recipient

Specifies whether the contact should be included as the recipient in the formatted address. The options are applied to all printed address, although this setting can be overridden on individual reports using the [Address Format Callers](#address-format-callers) list page. The option for *Include Contact* has the following possible values and meanings:

| Value | Meaning |
| - | - |
| Never | The recipient line for New Zealand addresses will never be included. |
| Always | The recipient line for New Zealand addresses will always be included. |
| Only When Matches Regular Expression | The recipient line for New Zealand addresses will only be included when it matches the regular expression that is defined in the *Recipient Regular Expression* field. |


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

# Transfer Order

The transfer order page has addresses for transfer-from (**Transfer-from** tab) and transfer-to (**Transfer-to** tab). Both of the addresses has been changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Vendor Bank Account Card

The address fields on the **General** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Vendor Card

The address fields on the **Address & Contact** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

# Vendor Templ. Card 

The address fields on the **Address & Contact** tab have changed to show the [common address changes](/StreetAs/common-address-field-changes#common-address-changes).

---

[^1]: Or Cmd+R if you're using a Mac.

[^2]: The lookup trigger is on the table field and not the page field. There is currently no way for a page extension to detect that a record has changed as a result of a lookup trigger that executes on the table field.

[^3]: I could create a new field to replace the Name field and then call the same lookup code that exists on the table field and use this to refresh the page once the lookup has completed. I decided against this approach (even though it worked OK) because it added a change that might cause complications if changes are made to the standard application in this area. Considering the obscure scenario that will trigger this odd behaviour and the fact there is a simple standard work-around (just refresh the browser) helped me to decide to minimise the changes and live with this odd glitch.

[^4]: I know right! The archive has different fields and layout compared to the non-archived document. Weird.

[^5]: I've made a note to log this with Microsoft. Who know's by the time you're reading this, it may have been fixed already and you're wondering what on earth I'm talking about.

[^6]: I'm beginning to think I should have written some clever script to automate the generation of these help topic entries.

[^7]: This is what happens when you let generative AI write your help topics.
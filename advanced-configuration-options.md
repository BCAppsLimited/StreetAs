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

# Street As Setup (Clever Stuff)

Some of the fields on the Street As Setup are a little more advanced than picking the country code for New Zealand. Here's an explanation of those fields and what they do.

![alt text](/screenshots/StreetAsSetup.png)


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
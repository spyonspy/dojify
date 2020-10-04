---
layout: page
title: Discord Bot
---

# About Dojify Bot

Dojify Bot allows user to easily add and close trade on [dojify.com](dojify.com){:target="_blank"} directly from discord channels. You can also interact with the [Dojify bot](https://discord.com/channels/@me/762185200708091924){:target="_blank"} directly similar to how you DM to other discord.


# Configuration

## Discord Server Admin
Enable Dojify Bot on your channel so that users in your channel can interact with dojify bot. 

<p class="message">
Dojify Bot reads command entered by users and responds accordingly. Please make sure it has both both read and write permission in a channel.
</p>

Please follow these steps for enabling bot on your channel
* [open](https://discord.com/oauth2/authorize?client_id= 748461911758340156&scope=bot){:target="_blank"} bot.
* Select your server
* Click on 'Authorize'

## Users

You can interact with the Dojify Bot either from a discord channel or directly. You can directly message dojify bot by clicking [here](https://discord.com/channels/@me/762185200708091924){:target="_blank"} 

<p class="message">
Make sure Dojify Bot is enabled in the discord channel and it has both read and write permission. You can run '!help' to verify if bot works correctly.
</p>

Please follow these steps for attching discordID to your dojify username.
* Register on [dojify.com](dojify.com){:target="_blank"}. Skip this step if you are already registered.
* Update your [profie](https://dojify.com/profile){:target="_blank"} with the username.
* From discord send following command '!configure {dojify-username}' without quotes. 
For example 
>!configure spyonspy
* Go to [profie](https://dojify.com/profile){:target="_blank"} and click *verify* in Discord Id.
* All set you are done!

# Commands
## Add Trade
Add trade command has following format
>!at {trade-type} {symbol} {options} @{price-per-contract} q{quantity}

**trade-type**: can be either ``BTO`` or ``STO``

**symbol**: Stock symbol for example ``AMZN``, ``GOOGL``, ``FB`` etc.

**options**: ``options`` consist of one or more than one options separated by space i.e. ``{option}`` or ``{option} {option}``  etc.

**option**: ``option`` has format ``{strikes} {strike-date}``

**strikes**: ``strikes`` consist of one or two ``{strike-prices}/{option-type}`` separated by space

**strike-prices**: ``strike-prices`` consist of one or more ``{strike-price}`` of same option type separated by ``/``. for example ``500/600/700``. 

When trade type is ``BTO`` first strike price is buy, second price is sell, third strike price is again buy and so on.

When trade type is ``STO`` first strike price is sell, second strike price is buy, third strike price is again sell and so on.


**strike-price**: ``strike-price`` is strike price for contract.

**option-type**: ``option-type`` can be either ``C`` or ``P`` C for call and P for put.

**strike-date**: has format ``mm/dd`` or ``mm/dd/yy``

**price-per-contract**: can be a positive or negative number. 
<p class="message">
When you collect premium for example when you sell credit spread, price-per-contract must be negative.
</p>

**quantity**: no. of contracts opened.

<p class="message">
Input is NOT case sensitive so feel free to enter lower case or upper case letters. your choice :)
</p>

### Examples
#### Buy call

>!at bto amzn 3500c 10/02 @8 Q1

![BTO call](/public/images/bto-call.png){:class="img-responsive"}

Will be shown on dojify as
![BTO call on dojify](/public/images/bto-call-dojify.png){:class="img-responsive"}

#### Sell Call

>!at sto amzn 3500c 10/02 @-5 Q1
![STO call](/public/images/sto-call.png){:class="img-responsive"}

Will be shown on dojify as
![STO call on dojify](/public/images/sto-call-dojify.png){:class="img-responsive"}

#### Buy Put
to be added
#### Sell Put
to be added
#### Debit Spread
to be added
#### Credit Spread
to be added
#### Iron Condor
to be added
#### buy call of different dates
to be added
#### sell call of different dates
to be added
#### buy call of different dates
to be added
#### sell call of different dates

Feel free to reach out [support@dojify.com](mailto:support@dojify.com){:target="_blank"} for any questions and feedback.

## Close Trade
Quote the response from the open trade or list trades and use the close command.
Close command Format is

>!ct {closing-price-per-contract}

In case of ``BTO``, If close price is higher than the open price then its profitable.

In case of ``STO``, If close price is lower than absolute value of the open price then its profitable. For exampe if open price is -5 then close price should be less than 5 to be profitable.

### Example
>!ct 0

![Close Trade](/public/images/ct.png){:class="img-responsive"}

On Dojify, it will be shown as

![Close Trade Dojify](/public/images/ct-dojify.png){:class="img-responsive"}


## See user stats
>!user-stats {username}

for exampe 
>!user-stats spyonspy

![User stats](/public/images/user-stats.png){:class="img-responsive"}

On dojify user stats is shown by visiting a user profile

![User stats on dojify](/public/images/user-stats-dojify.png){:class="img-responsive"}


## Change dojify username
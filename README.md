# Prowlcoin : prowl notifications for bitcoin exchanges in bash

## DESCRIPTION :


Shell script to query bitcoin exchanges (mtgox, bc-central as of now)
for the  current exchange rate, and send PROWL alerts in case the
rate is higher/lower than a predetermined limit

## Setup

Clone this repository somewhere

    $ git clone https://github.com/ygritte/prowlcoin.sh.git
    $ cd prowlcoin

Enter your Prowl API key in the `.prowlapikey` file

    $ echo ".....YOUR_PROWL_API_KEY....." > .prowlapikey

## USAGE:

    ./prowlcoin tick exchange currency treshold direction alert_level has_banner [toCUR]

where

     tick        = delay in seconds between two calls (integer > 30)

     exchange    = [GOX|BCC]

     currency    = [EUR|USD]

     value       = real number (dot as decimal separator)

     direction   = [up|down]

                    * up : prowl alert if price is topped
                    * down : prowl alert id price is bottomed

     alert_level = prowl alert level (either one of -2, -1, 0, 1, 2)

     has_banner  = [banner|nobanner] : display a banner on top of
                                       terminal

     toCUR       = [toUSD|toEUR] optionnal : also displays converted value to
                                             alternate currency, at the currency's
                                             current exchange rate
## Examples

>**Poll** every 40 seconds the **MtGox** exchange in **USD** and place
>an alert at **50.5** USD if the price goes **under** that level, with a
>prowl alert level equal to **2**, display **no banner**, and
>display that price **converted to EURO**

    ./prowlcoin 40 GOX USD 50.5 down 2 banner toEUR


>**Poll** every 120 seconds the **Bitcoin-central** exchange in **EUR** and place
>an alert at **70** EUR if the price goes **over** that level, with a
>prowl alert level equal to **-1**, display **a banner**, and
>display that price **converted to DOLLAR**

    ./prowlcoin 120 BCC EUR 70 up -1 nobanner toUSD

>Just Poll GOXEUR for >50 already

    ./prowlcoin 31 GOX EUR 50 up 2 nobanner

>etc...


##LICENSE :

Applies to all files in this repository except for the submodule
[JSON.sh](https://github.com/dominictarr/JSON.sh.git) which is licensed
by its author under its own terms

###prowlcoin license

      DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                   Version 2, December 2004

    Copyright (C) 2013 Ygritte

    Everyone is permitted to copy and distribute verbatim or modified
    copies of this license document, and changing it is allowed as long
    as the name is changed.

              DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
     TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

    0. You just DO WHAT THE FUCK YOU WANT TO.


###prowlcoin DISCLAIMER :

     This program is free software. It comes without any warranty, to
     the extent permitted by applicable law. You can redistribute it
     and/or modify it under the terms of the Do What The Fuck You Want
     To Public License, Version 2, as published by Sam Hocevar. See
     http://www.wtfpl.net/ for more details.

###JSON.sh license

See [https://github.com/dominictarr/JSON.sh.git](https://github.com/dominictarr/JSON.sh.git) for
JSON.sh's license


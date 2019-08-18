# CryptoPriceWatcher
Monitors profit/loss from different currency permutations and differences between exchanges

This software is provided as is. 

The permutations take the bid/ask prices as sent from the exchange and calculate the amount left after starting with one unit. This looks for cases where you start with one coin of a crypto currency and hop through at least two others and (possibly) have more than one coin at the end.

The second function monitors the loss/gain between exchanges. It looks at the net result of selling one coin in an exchange and selling the same coin in another. Where the gain is between 0 and 0.5% the cells are red. Between 0.5 and 1 the cells are blue. Above 1% they are green. These calculations do not take into account the transaction fees so the fees should be monitored.

# Description

This software is not complete. It function as is but needs to be modified to handle other exchanges with different json formats. I was built based on Bittrex api model and other exchanges added later. 

The software relies on the "Settings" folder for what to monitor and calculate. Each exchange has three files for different settings. 

Settings.txt is the main settings file. You can add or remove exchanges by adding or removing their names. The files for the exchange must start with the exchange name followed by the settings file name.

# Examples

BittrexJSONMappings.txt 
This file gives the path to follow in the json result to get the value needed.

BittrexPairs.txt 
This file contains the different pairs to be used in the calculations and whether the pairs will be included in the multi-market or the multi-pair windows.

BittrexUrls.txt
This file tells the software what URL to call. The "tick" url is for a specific pair. The "tickfull" url is for exchanges that give all results in one go.

MultiplePairs.txt

This file tells the program what to do when calculating the price. For example, when buying eth with btc the "ask" price is used in a "divide" calculation, while when buying btc with eth the "bid" price is used in a "multiply" calculation.


# ToDo
The "StandaloneMode" was intended to be invisible but it simply displays a summarized view of the data that removes many of the general information fields. The "MultiCurrencyNotificationThreshold" value displays any permutations that give a gain/loss value equal to or greater than the value in the setting. This is found in the JsonHandler.exe.config file.


# License
The MIT License (MIT)

Copyright (c) 2019

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

# ExchangeRatesByDate
Exchange rates gathered on Central Bank of Armenia for [The Open Data Armenia team](https://github.com/opendataam/opendatam-tasks/issues/9)

# Structure of files
`/ExchangeRatesByDateResult/CurrentDate` - when the current rates were set. It is also used as the name of the file  
`/ExchangeRatesByDateResult/NextAvailableDate` - date of the next rates (nil if it's still in the future)  
`/ExchangeRatesByDateResult/PreviousAvailableDate` - when the previous rates were set  
`/ExchangeRatesByDateResult/Rates`  
`/ExchangeRatesByDateResult/Rates/ExchangeRate`  
`/ExchangeRatesByDateResult/Rates/ExchangeRate/ISO` - ISO code of the foreign currency  
`/ExchangeRatesByDateResult/Rates/ExchangeRate/Amount` - how much will you get `ISO`  
`/ExchangeRatesByDateResult/Rates/ExchangeRate/Rate` - how much you need to pay AMD  
`/ExchangeRatesByDateResult/Rates/ExchangeRate/Difference` - difference with previous `Rate` = Current `Rate` - Previous `Rate`  
`Rate` AMD = `Amount` `ISO`, and it's `Difference` AMD higher then previous one

# Known Errors in Data
- There are some currencies that I can not recognise:
    - TAD from 2000-01-01 to 2000-12-31
    - USM from 2000-01-01 to 2006-12-30
- TM in 2013-05-22 is Turkmenistan manat (TMT)
- There is no internal mechanism (in the CBA) to manage relevance of currency codes. Thus RUR is encountered till 2006-12-30 (it is RUB since 1998-01-01). Similar situation could be in Eurozone as it has been expanding over the years.

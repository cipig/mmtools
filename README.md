## setprices

`./setprices KMD cmcv2` sets prices for all coins from margins.conf and uses CMC API v2  
`./setprices KMD cmcpaid` does the same, but uses CMC paid API. $apikey must be configured.  

userpass is taken from the environment variable, so it must be set, eg `source userpass`  
setprice-call is used to set prices, so the script must be called regularly.  
If bidmargin or askmargin is not set, bid/ask will not be set.  
margins.conf must contain cmcid for every coin, taken from https://api.coinmarketcap.com/v2/listings/  

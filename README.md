## setprices

`./setprices KMD cmcv2` sets prices for all coins from margins.conf and uses CMC API v2  
`./setprices KMD cmcpaid` does the same, but uses CMC paid API ($apikey must be configured)  

`margins.conf` must contain cmcid for every coin, taken from https://api.coinmarketcap.com/v2/listings/  
If `bidmargin` or `askmargin` is not set, bid/ask will not be set  

script to set prices every 2 minutes (`~/SuperNET/iguana/dexscripts/autoprice_kmd`):
```
#!/bin/bash
source userpass

while true; do
  ~/mmtools/setprices/setprices KMD cmcpaid
  sleep 120
done
```
can be started with `nohup ./autoprice_kmd > ~/setprices.log &` in the background  
config file `~/mmtools/setprices/margins.conf` can be edited and prices will be updated without the need to restart

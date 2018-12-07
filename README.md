## setprices

`./setprices KMD cmcpaid` sets prices for all coins from margins.conf and uses CMC paid API ($apikey must be configured)  

`margins.conf` must contain cmcid for every coin, taken from https://api.coinmarketcap.com/v2/listings/  
If `bidmargin` or `askmargin` is not set, bid/ask will not be set  

script to set prices with CMC paid API:
```
#!/bin/bash
source userpass

while true; do
  ~/mmtools/setprices/setprices KMD cmcpaid
  sleep 600
done
```

can be started with `nohup ./autoprice_kmd > ~/setprices.log &` in the background  
config file `~/mmtools/setprices/margins.conf` can be edited and prices will be updated without the need to restart  

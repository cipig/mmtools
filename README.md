## mpm

`./mpm coinpaprika` sets prices for all coins from mpm.conf and uses coinpaprika for DEX price calculation  

cmcid/papid in `mpm.conf` are taken from https://api.coinmarketcap.com/v2/listings/ and  https://api.coinpaprika.com/v1/coins  
If `bidmargin` or `askmargin` is not set, bid/ask will not be set  

can be started with `stdbuf -oL nohup ~/mmtools/mpm/mpm.sh > /tmp/mpm.log &` in the background  
`tail -f /tmp/mpm.log` to watch mpm TV
config file `~/mmtools/mpm/mpm.conf` can be edited and prices will be updated without the need to restart  

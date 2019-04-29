## mpm

```
sudo apt-get install libjson-perl libfile-slurp-perl
cd && git clone https://github.com/cipig/mmtools
cd ~/mmtools/mpm
vi mpm
my $cex_apikey = "Binance API Key";
my $cex_seckey = "Binance API secret";
```

`~/mmtools/mpm/mpm coinpaprika binance` sets prices for all coins from mpm.conf in mm2 (KMD/$coin) and uses coinpaprika as price source  
it also sets KMD/BTC bids/asks with size $quantity in Binance  

cmcid/papid in `mpm.conf` are taken from https://api.coinmarketcap.com/v2/listings/ and  https://api.coinpaprika.com/v1/coins  
If `bidmargin` or `askmargin` is not set, bid/ask will not be set  

can be started with `stdbuf -oL nohup ~/mmtools/mpm/mpm.sh > /tmp/mpm.log &` in the background and will update the prices every minute  
`tail -f /tmp/mpm.log` to watch mpm TV  
config file `~/mmtools/mpm/mpm.conf` can be edited and prices will be updated without the need to restart  

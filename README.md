## mpm

```
sudo apt-get install jq libdatetime-perl libdatetime-format-strptime-perl libjson-perl libjson-rpc-perl libfile-slurp-perl liblwp-protocol-https-perl
cd && git clone https://github.com/cipig/mmtools
```

The script expects a file `~/atomicDEX-API/etomic_build/client/userpass` that contains the userpass(rpc_password) like this `export userpass="whatever"`. It is the same that was used to start mm2 (`\"rpc_password\":\"$userpass\"`).

`stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex_gecko KMD LTC USDT-BEP20 > /tmp/mpm.log.dex &` to start and set prices for all coins using KMD, LTC and USDT-BEP20 as base coins  
`tail -f /tmp/mpm.log.dex` to watch mpm TV  

The following base coins are supported: KMD, KMD-BEP20, BTC, BTC-BEP20, ETH-BEP20, LTC, BCH, DOGE, DOGE-BEP20, USDT-BEP20, BUSD-BEP20, DAI-BEP20, PAX-BEP20, TUSD-BEP20, USDC-BEP20  
The config file is `mpm.conf.dex` and is located in the same directory as the script. The following price sources are supported in addition to `geckoid`:  
- `binance_usd_symbol`
- `binance_btc_symbol`
- `safetrade_btc_symbol`
- `freiexchange_btc_symbol`
- `crex24_btc_symbol`
- `bittrex_btc_symbol`
- `coinex_usd_symbol`
- `hitbtc_btc_symbol`

For all the above sources, except Binance, the script use (ask + bid + last) / 3 as reference price.  
All volumes (`minaskvolume`, `minbidvolume`, `maxbidvolume`) set in the config file are expressed in USD.  


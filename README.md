## mpm

```
sudo apt-get install jq libdatetime-perl libjson-perl libjson-rpc-perl libfile-slurp-perl liblwp-protocol-https-perl
cd && git clone https://github.com/cipig/mmtools
```

`~/mmtools/mpm/mpm dex KMD kmd-komodo`  
- sets prices for all coins from mpm.conf.dex.KMD in AtomicDEX and uses coinpaprika as price source  

papid in `mpm.conf.dex.KMD` are taken from https://api.coinpaprika.com/v1/coins  
If `bidmargin` or `askmargin` is not set, bid/ask will not be set  

can be started with `stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex KMD kmd-komodo > /tmp/mpm.log.dex.kmd &` in the background and will update the prices  
`tail -f /tmp/mpm.log.dex.kmd` to watch mpm TV  

## mpm

```
sudo apt-get install libjson-perl libjson-rpc-perl libfile-slurp-perl liblwp-protocol-https-perl
cd && git clone https://github.com/cipig/mmtools
```

`~/mmtools/mpm/mpm dex`  
- sets prices for all coins from mpm.conf.dex in AtomicDEX (base is KMD) and uses coinpaprika as price source  

papid in `mpm.conf.dex` are taken from https://api.coinpaprika.com/v1/coins  
If `bidmargin` or `askmargin` is not set, bid/ask will not be set  

can be started with `stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex > /tmp/mpm.log &` in the background and will update the prices every minute  
`tail -f /tmp/mpm.log` to watch mpm TV  

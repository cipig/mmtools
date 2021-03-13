## mpm

```
sudo apt-get install jq libdatetime-perl libdatetime-format-strptime-perl libjson-perl libjson-rpc-perl libfile-slurp-perl liblwp-protocol-https-perl
cd && git clone https://github.com/cipig/mmtools
```

`stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex_paprika KMD kmd-komodo > /tmp/mpm.log.dex.kmd &` to update prices from coinpaprika  
`stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex_gecko KMD komodo > /tmp/mpm.log.dex.kmd &` to update prices from coingecko  
`tail -f /tmp/mpm.log.dex.kmd` to watch mpm TV  

## mpm

```
sudo apt-get install jq libdatetime-perl libdatetime-format-strptime-perl libjson-perl libjson-rpc-perl libfile-slurp-perl liblwp-protocol-https-perl
cd && git clone https://github.com/cipig/mmtools
```

The script expects a file `~/atomicDEX-API/etomic_build/client/userpass` that contains the userpass(rpc_password) like this `export userpass="whatever"`. It is the same that was used to start mm2 (`\"rpc_password\":\"$userpass\"`).

`stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex_gecko KMD komodo > /tmp/mpm.log.dex.kmd &` to start and update prices from coingecko every 2 minutes  
`tail -f /tmp/mpm.log.dex.kmd` to watch mpm TV  

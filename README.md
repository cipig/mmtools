## mpm

```
sudo apt-get install jq libdatetime-perl libdatetime-format-strptime-perl libjson-perl libjson-rpc-perl libfile-slurp-perl liblwp-protocol-https-perl
cd && git clone https://github.com/cipig/mmtools
```

The script expects a file `~/atomicDEX-API/etomic_build/client/userpass` that contains the userpass(rpc_password) like this `export userpass="whatever"`. It is the same that was used to start mm2 (`\"rpc_password\":\"$userpass\"`).

`stdbuf -oL nohup ~/mmtools/mpm/mpm.sh.dex_gecko KMD LTC USDT-BEP20 > /tmp/mpm.log.dex &` to start and set prices for all coins using KMD, LTC and USDT-BEP20 as base coins  
`tail -f /tmp/mpm.log.dex` to watch mpm TV  

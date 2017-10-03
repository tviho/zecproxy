# Description 
This is a Stratum Proxy for Zcash using JSON-RPC.
Originally developed by Cryptense SAS. Working with [flypool](http://zcash.flypool.org/) and [nanopool](http://zec.nanopool.org)

![alt text](http://g.recordit.co/8oX3Pj77BN.gif)


**WARNING** This work is still in development. Please report any broken features or issues.


# Features
* Additional up to 10-20% increase of earning compared to standard pools
* Zcash stratum proxy
* Pool failover system
* Only one connection to the pool
* Workers get new jobs immediately
* Submit of shares without network delay, it's like solo-mining but with benefits of professional pool
* Central Wallet configuration, miners doesn't need wallet as username
* Bypasse worker_id for detailed statistic and per rig monitoring - not supported on flypool yet / working on nanopool
* PM2 support


# How it Works
```
   Pool A <---+                        +-------------+ Rig1 / PC1
 (Active)      |                       |
               |                       +-------------+ Rig2 / PC2
               |                       |
  Pool B <---+-----StratumProxy  <-----+-------------+ Rig3 / PC3
(FailOver)                             |
                                       +-------------+ Rig4 / PC4                                      
```


# Todo
* Logfile setup
* ASCII UI
* Watchdog system (alive / gpu failure) 
* Hashrate computation


# Installation and Start
* git clone git@github.com:BScrk/zecproxy.git
* cd zec_stratum
* npm install
* node proxy.js

The proxy will automatically listen on port 8000 for miners.


# Configuration
* all configs in file config.json to change settings. 


# Miners command line
* ./miner --server <PROXY_ADDRSS> --user <RIG_NAME> --pass <PASS> --port <PROXY_PORT>
exemple : ./miner --server 192.168.0.10 --user miner_1 --pass "x" --port 8000 --solver 0


# Donations
* ETH:  0x1212eF39d945aB9A9568Aa5a72c5CBA99Bbe46c1
* ZEC:  t1YAdYcnKR2ozADWPUvmgnDgf86gfsxQEEE


# Requirements
zec_stratum is build with nodeJS. The requirements for running zec_stratum are:

* linux (recommend)
* nodeJS
* npm


# Contact
* We are available via dev@cryptense.com


# License
This software is provides AS-IS without any warranties of any kind.
**Please use at your own risk.**


# Protocol Documentation
* https://slushpool.com/help/manual/stratum-protocol
* https://github.com/ctubio/php-proxy-stratum/wiki/Stratum-Mining-Protocol
* https://github.com/slushpool/poclbm-zcash/wiki/Stratum-protocol-changes-for-ZCash

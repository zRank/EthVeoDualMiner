# EthVeoDualMiner
This is a dual miner for Ethereum and AmoVeo. You can configure EthVeoDualMiner for many different hash rates of Ethereum and Amoveo:
* 75% of Amoveo plus 70% of Ethereum with -erat 128 and -vrat depending on GPU
* 98% of Ethminer plus 50-40% of AmoVeo with -erat 192 and -vrat depending on GPU
* 90% of Amoveo plus 15% of Ethereum with -erat 128 and -vrat 200

EthVeoDualMiner has builds for Windows and Ubuntu, and it works with both NVidia and AMD GPUs.

Optimal GPU model efficiency for -vrat is usually found by setting -erat 192, and then let -vrat auto-tune until the Ethereum hash rate drops below 98%. The console will print where the VeoRatio finalizes. This gives you the optimal GPU model efficiency. If you want very high AmoVeo hash rates instead of targetting maximum efficiency, you can set very high -vrat values manually.

The deafult settings of -erat at 128 and not setting -vrat values will put EthVeoDualMiner in a "AmoVeo greedy" mode. The -vrat will increase aggressively until AmoVeo hash rate has deminishing returns, and Ethereum hash rate will decrease significantly. On most GPU models, this configuration will auto-tune the -vrat values to 80-85% AmoVeo speed + 20-25% Ethereum hash rates.

## Downloads
   [Download EthVeoDualMiner Releases](https://github.com/zRank/ethVeoDualMiner/releases)

## How to run EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal ETH_ADDRESS -vwal AMOVEO_ADDRESS
```

### All Configuration Settings
* -ewal     Ethereum Wallet
* -epool    Ethereum Pool
* -epsw     Ethereum Stratum Password
* -vwal     AmoVeo Wallet
* -vpool    AmoVeo Pool
* -vpsw     AmoVeo Stratum Password
* -erat     Ethereum Ratio controls Ethereum work versus AmoVeo. Default 128. Allowed Range: 60-256. Typical: 128 or 192
* -vrat     AmoVeo Ratio controls Veo work amount per GPU thread. Default: Auto-tune. Allowed Range: 1-400+. Typical: 28-96
* -dveo     Device List to Mine AmoVeo Only
* -dskip    Device Skip List for no mining
* -pool     Print pool info with New Work events
* -date     Print timestamp with New Work events

## Full Usage for EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal 0xF8991390e8089173C0365b6bf8e2dfdA54998BC8 -epool stratum+tcp://eu1.ethermine.org:4444 -vwal BOyTm/uIxBUfK5WFb3HA05mk+0kKUEMvrmLTmd/fYx/+g+lK+YmUeah08N63mCqvTieQS5mxXkhQ6SW1irdQbvc= -vpool stratum+tcp://stratum.amoveopool.com:8822
```

## Advanced Usage for EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal 0xF8991390e8089173C0365b6bf8e2dfdA54998BC8 -epool stratum+tcp://eu1.ethermine.org:4444 -vwal BOyTm/uIxBUfK5WFb3HA05mk+0kKUEMvrmLTmd/fYx/+g+lK+YmUeah08N63mCqvTieQS5mxXkhQ6SW1irdQbvc= -vpool stratum+tcp://stratum.amoveopool.com:8822 -vrat 1:28,2:40 -dveo 3,4 -dskip 0,5 -date -pool

This example shows:
  - Veo ratio (-vrat) of 28 on device 1, and 40 on device 2
  - Only mine AmoVeo on device 2 and 3. (No Ethereum.)
  - Do not use device 0 and 5 for any mining
  - Print pool and timestamp info with New Work events
```

## Dependencies
* NVidia GPU requires CUDA installed.
* AMD GPU require OpenCL installed.
* Windows release zips contain the required DLLs.
* Ubuntu requires these packages installed:
```
sudo apt-get install libcurl4-gnutls-dev libjansson-dev libssl-dev 
```

## Notes
* EthVeoDualMiner supports both Getwork and Stratum protocol for AmoVeo
* EthVeoDualMiner supports Stratum and ETH-Proxy protocols for Ethereum. It has been tested against Ethermine and DwarfPool.

## Developer Fee
This software has an effective total developer fee under 1%. It mines with a 0% Eth mining fee and a 2% AmoVeo mining fee.

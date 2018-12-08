# EthVeoDualMiner
This is a dual miner for Ethereum and Amoveo. The hash rate is 98% of Ethminer plus 59-42% of Amoveo speeds depending on your GPU model.

EthVeoDualMiner has builds for Windows and Ubuntu, and it works with both NVidia and AMD GPUs.

## Releases
   [Download EthVeoDualMiner Release](https://github.com/zRank/ethVeoDualMiner/releases)

## How to run EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal ETH_ADDRESS -vwal AMOVEO_ADDRESS
```

### All Configuration Settings
* -ewal     Ethereum Wallet
* -epool    Ethereum Pool
* -epsw     Ethereum Stratum Password
* -vwal     Amoveo Wallet
* -vpool    Amoveo Pool
* -vpsw     Amoveo Stratum Password
* -vrat     Amoveo Ratio
* -dskip    Device Skip List

## Full Example for EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal 0x07D47A1C6de0FD4E1608641f27a156b4692Be72e -epool stratum+tcp://eu1.ethermine.org:4444 -vwal BOPvbgrso8GakBw2Xxkc1A2lt0OiKg/JqjBuCPfP0bTI/djsM9lgp/8ZMmJgPs/aDlxQL2dT+PYfEywsaRthrmE= -vpool stratum+tcp://stratum.amoveopool.com:8822
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
* EthVeoDualMiner supports both Getwork and Stratum protocol for Amoveo
* EthVeoDualMiner supports Stratum and ETH-Proxy protocols for Ethereum. It has been tested against Ethermine and DwarfPool.

## Developer Fee
This software is free to use. It has an effective total developer fee of 0.8%. It mines with a 0% Eth mining fee and a 2% Amoveo mining fee.

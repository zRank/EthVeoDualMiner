# EthVeoDualMiner
This is a dual miner for Ethereum and AmoVeo. The hash rate is 98% of Ethminer plus 59-42% of AmoVeo speeds depending on your GPU model.

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
* -vwal     AmoVeo Wallet
* -vpool    AmoVeo Pool
* -vpsw     AmoVeo Stratum Password
* -vrat     AmoVeo Ratio controls Veo work versus Eth work
* -dveo     Device List to Mine AmoVeo Only
* -dskip    Device Skip List for no mining

## Full Example for EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal 0x07D47A1C6de0FD4E1608641f27a156b4692Be72e -epool stratum+tcp://eu1.ethermine.org:4444 -vwal BOPvbgrso8GakBw2Xxkc1A2lt0OiKg/JqjBuCPfP0bTI/djsM9lgp/8ZMmJgPs/aDlxQL2dT+PYfEywsaRthrmE= -vpool stratum+tcp://stratum.amoveopool.com:8822
```

## Advanced Example for EthVeoDualMiner
```
EthVeoDualMiner.exe -ewal 0x07D47A1C6de0FD4E1608641f27a156b4692Be72e -epool stratum+tcp://eu1.ethermine.org:4444 -vwal BOPvbgrso8GakBw2Xxkc1A2lt0OiKg/JqjBuCPfP0bTI/djsM9lgp/8ZMmJgPs/aDlxQL2dT+PYfEywsaRthrmE= -vpool stratum+tcp://stratum.amoveopool.com:8822 -vrat 1:28,2:40 -dveo 3,4 -dskip 0,5

This example shows:
  - Veo ratio (-vrat) of 28 on device 1, and 40 on device 2
  - Only mine AmoVeo on device 2 and 3. (No Ethereum.)
  - Do not use device 0 and 5 for any mining
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
This software has an effective total developer fee of 0.8%. It mines with a 0% Eth mining fee and a 2% AmoVeo mining fee.

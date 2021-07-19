# Liquidator-V2
QIDAO Liquidator Script Version 2

## Improvements
With V2, we make the assumption that users of the QIDAO protocol are not going to be changing their debt or collateral amounts that often, so we grab their vault details and determine their MATIC in collateral and their MAI in debt. Once we have built all valid vaults into a database, we grab the MATIC price repetitively and determine if a vault is eligbile for liquidation. I have also added the getPaid() and derisk() functions (which can be buggy in their current state).

## Set Up
Similar to V1, you will need to create your own Python3 environment and pip install web3 to have your environment ready. Then, you will need to fill out the url variable with a MATIC RPC endpoint, myAddress variable with your wallet address and priv variable with your wallet private key. The script will first scan the vaults and build up data about them, then will begin scanning for liquidations. All you need to do is hold some MAI in your wallet and you have a small chance at some liquidations.

## Considerations
If I am posting a liquidator script, it likely means I have already developed one much faster. As such I do not expect this script to be competitive with newer scripts I have made and may even lose money on failed transactions. Also, the derisk function has lacked thorough testing as I had some bugs that prevented me from testing the function at all and I have forked to a different copy since. getPaid should be working properly, but the liqLoop has a tendency to fail midway through and never reach getPaid. Again have yet to do super thorough testing, but I have only see it do one liq per liqLoop, so the issue seems to be somewhere in the liqLoop for loop. This script is only valid on MATIC vaults, it will not work on camWMATIC vaults without some alteration.

## Help Me Out
I accept payments on both MATIC and ETH networks, thank you frens <3

0xe0f1F6d9b57DB098a1c786a835A55A1Ff64d39EE

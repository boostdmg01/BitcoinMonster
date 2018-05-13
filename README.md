# BitcoinMonster 
Shell script to install a [BitcoinMonster Masternode](https://www.bitcoinmonster.org) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/boostdmg01/BitcoinMonster/master/btcm_install.sh
bash btcm_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the BitcoinMonster Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000** MON to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 6 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
startmasternode "alias" "0" "MN1"
``` 
14. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
bitcoinmonster-cli masternode status
```
***

## Usage:
```
bitcoinmonster-cli mnsync status
bitcoinmonster-cli masternode status  
bitcoinmonster-cli getinfo
```
Also, if you want to check/start/stop **BitcoinMonster**, run one of the following commands as **root**:

```
systemctl status BitcoinMonster #To check if BitcoinMonster service is running  
systemctl start BitcoinMonster #To start BitcoinMonster service  
systemctl stop BitcoinMonster #To stop BitcoinMonster service  
systemctl is-enabled BitcoinMonster #To check if BitcoinMonster service is enabled on boot  
```  
***

## Donations

Any donation is highly appreciated

**BTC**: 16QpY5EEzfsPeWscjtXss2RNNw1GwY9oMz  
**LTC**: LgXDj5SXFZ1sz2XxqpPmAWfck3hXLkpxe3  
**MON**: MEN61iTxNSFGeU4DnEStanfZxRjxSf3X1K

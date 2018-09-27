# Ourcoin
Shell script to install an [Ourcoin Masternode](https://ourplatform.io/) on a Linux server running Ubuntu 16.04..
***


## VPS installation
```
wget -N https://raw.githubusercontent.com/zoldur/Ourcoin/master/ourcoin_install.sh
bash ourcoin_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the OurcoinCore Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** OUR to **MN1**. You need to send all 1000 coins in one single transaction
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug Console"**
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
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias false MN1
```
14. Login to your VPS and check your masternode status by running the following command. If you get **status 4**, it means your masternode is active.
```
ourcoin-cli masternode status
```
***

## Usage:
```
ourcoin-cli mnsync status
ourcoin-cli masternode status
ourcoin-cli getinfo
```
Also, if you want to check/start/stop **Ourcoin**, run one of the following commands as **root**:
```
systemctl status OurcoinCore.service #To check if OurcoinCore service is running
systemctl start OurcoinCore.service #To start OurcoinCore service
systemctl stop OurcoinCore.service #To stop OurcoinCore service
systemctl is-enabled OurcoinCore.service #To check if OurcoinCore service is enabled on boot
```
***

## Donations

Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  


# BCZ
Use this shell script to install a [BCZ Masternode](https://www.bitcoincz.org/) on a Linux server running Ubuntu 16.04.  
This will require a VPS, I use [Vultr](https://www.vultr.com/?ref=7310394).  I recommend using a $5 server.
This script will install **BCZ Core v6.0.0.9 **.
***

## Installation:
Log into the server using ssh (Putty for windows or terminal for Mac users) and run the following commands:
```
wget -q https://raw.githubusercontent.com/lockdawg/BCZ/master/bcz_install.sh
bash bcz_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows/Mac Wallet:
1. Open the BCZ Core Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **5000** **BCZ** to **MN1**.
4. Wait for ~15 confirmations before starting the node.
5. Go to **Help -> "Debug window - Console"**
6. Type the following command: **masternode outputs**
7. Type the following command: **masternode genkey**
8. Open masternode.conf from the following folder %appdata%\bcz (windows) or ~/Library/Application Support/ (hidden folder for Mac users)
9. Add the following entry:
```
Alias Address Genkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:29500**
* Genkey: **Masternode GenKey**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
10. Click OK and exit the Wallet.
11. Open BCZ Core Wallet, go to **Masternode Tab**.
12. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
13. Click **Start All** or **Start Alias**
12. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
bcz-cli getinfo
bcz-cli masternode status
```
Also, if you want to check/start/stop **BCZ** , run one of the following commands as **root**:
```
systemctl status BCZ #To check the service is running.
systemctl start BCZ #To start BCZ service.
systemctl stop BCZ #To stop BCZ service.
systemctl is-enabled BCZ #To check whether BCZ service is enabled on boot or not.
```
***

## Updating BCZ
The first line (rm bcz_update.sh) is not required the very first time you update the node and will return an error if you run it.  This is fine, continue with the update script.
```
rm bcz_update.sh*
wget -q https://raw.githubusercontent.com/lockdawg/BCZ/master/bcz_update.sh
bash bcz_update.sh
```
***

## Donations:  

**BCZ**: BPeu4NDf1NkczD35FuWQLENPkh8DYyiodG  
**BTC**: 33mkLq6fmwfCz5dfK54giowZYygtBxypXr  
**ETH**: 0x1CCa2B182516a2bdC6989606F52E28407751A9D3  
**LTC**: MTkeGVv99gTeoyGnGppPCVDQ2Xz9sF6UVn

Updates:<br>
11/17/17 - Version 0.1.5.1. Updated image assets according to new branding. <br>
4/5/17 - Version 0.1.5.0. Upgraded openssl and added checkpoints. <br>
7/15/14 - Upgraded Protocol to 60007 and version upgrade to v 0.1.4.3. This disconnects old clients to avoid Stake Forking problem that was fixed in previous version, but still vulnerable to old clients forking.<br>
7/12/14 - Fixed Stake forking problem. Please update your client to version 0.1.4.2<br>
4/29/14 - version 0.1.4.0 upgraded to OpenSSL 1.01g 7 Apr 2014 to correct for Heartbleed vulnerability. Added support to disable POS mining in paccoin.conf "staking=0". Also added contrib folder which includes easywinbuilder for building on windows based machines.<br>

paccoin a crypto currency based on SHA256D with Proof of Work and Proof of Stake.
 
Paccoin is the “Peoples Alternative Choice” digital currency that allows users to send or receive paccoins to each other on the internet without the need for banks.

Official Website for Paccoin is http://paccoin.net/

<h1>Installation Instructions: Windows</h1>

Use easywinbuilder in the "contrib" folder

<h1>Installation Instructions: Ubuntu 14.04</h1>

* Install the following dependencies using your terminal program:

apt-get update<br>
sudo apt-get install build-essential libssl-dev libboost-all-dev libminiupnpc-dev<br>
sudo apt-get install libqrencode-dev qt4-dev-tools qt4-qmake libqt4-dev git<br>
sudo apt-get install libdb4.8++-dev<br>

For 16.04 use libdb++-dev
(Some versions of Ubuntu do not have libminiupnpc-dev available. You can download miniupnpc libraries here: http://miniupnp.free.fr/files/download.php?file=miniupnpc-1.8.tar.gz) Use the instructions to install in doc section.

* Download the paccoin repository

cd ~<br>
git clone https://github.com/PaccoinCommunity/Paccoin.git paccoin

This will create a directory called "paccoin" and copy the files into it. 

* Next we're going to compile the programs.

cd paccoin/src<br>
make -f makefile.unix

This will generate the headless paccoind file. (rpc commands can be made from the terminal ie. "./paccoind help")

* Run this by using the following command.

./paccoind

The file should end and state that an rpcuser and rpcpassword needs to be added. By running this you have now created 
a hidden directory located at ~/.paccoin. 

* Enter that directory.

cd ~/.paccoin

* Using a text editor create your file paccoin.conf and change the rpcuser and rpcpassword for security 
reasons. 

nano paccoin.conf

rpcuser=yourname<br>
rpcpassword=yourpassword<br>
addnode=pacifica-nation.com

if you intend to solo mine use the following as an example:

rpcallowip=192.168.1.* (for lan, or use a direct IP)<br>
server=1<br>
gen=0 (use 1 to generate coins (this will cause your computer to run at 100% cpu))<br>

Save this file. 

* Now you're ready to compile and run your wallet.

cd ~/paccoin<br>
qmake paccoin-qt.pro<br>
make

You should see the file paccoin-qt which you can execute by double clicking on it in file manager. This is your wallet 
gui.

It is also recommended that you change the passphrase to something you can remember. If you lose your passphrase 
there is no way to get it back and you will lose any money in your wallet, so be careful.

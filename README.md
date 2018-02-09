# fldc-cure_Ubuntu1710
The steps required to get Folding Coin and Cure Coin mining going on an Ubuntu 17.10 rig, with a Nvidia GPU. 

## Explanation
If you are interested in Merged Mining of Folding Coin and Cure Coin, on Ubuntu 17.10, and you have a GPU of some kind...
this is for you. If you do not have a GPU, you could still follow these steps, but much of it won't be applicable to you.

Broadly we are going to:
* Compile the CureCoin wallet and record our address (after installing dependencies)
* Install Folding@Home 
* Install CUDA (Nvidia specific)
* Launch Folding@Home manually, verifying that the GPU was detected
* Setup a Counterparty Wallet for Folding Coin
* Generate a Folding Coin Compliant FAH compliant Username, and join the CureCoin team
* Sign up on the CureCoin Mining Pool
* Fold / Mine away

### CureCoin Wallet Compilation (Assuming that you want the Qt GUI)
Per the build instructions, you are going to have to install some dependencies for Cure Coin. 
<code>
sudo apt-get install git qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libminiupnpc-dev libdb5.3++-dev dh-make build-essential
git clone https://github.com/cygnusxi/CurecoinSource.git
cd ./Curecoin*
qmake && make
</code>
You can then try launching the wallet with 
<code>
./Curecoin*/curecoin-qt
</code>
Allow it to sync the blockchain (fairly small in 02/2018) and then be sure to Encrypt the wallet. 
Once encrypted, go ahead and take note of the automatic address in the Receiving section. You'll need this later. 

### Install Folding@Home

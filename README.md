1. Rent a Linux server from Hezner or another provider

 a server 8 CPU / 16 GB / 240 GB.
After deploying the smart contract, we will remove the server.
We need to update the server and install the packages for Linux:

sudo apt update && sudo apt upgrade -y

sudo apt install curl

. <(wget -qO- https://raw.githubusercontent.com/SecorD0/utils/main/installers/rust.sh)

sudo apt-get install git-all

sudo apt-get install cmake

sudo apt-get install libssl-dev
sudo apt-get install pkg-config

sudo apt-get install libclang-dev

sudo apt-get install libpq-dev

sudo apt-get install build-essential

sudo apt-get install gcc
Install Sui binaries:

cargo install --locked --git https://github.com/MystenLabs/sui.git --branch devnet sui

Create a new Sui wallet:

sui client active-address

y

enter (default)

write 0 or 1 or 2 (I wrote 1)

❗️Save Secret Recovery Phrase and note down your Sui Wallet address❗️

Go to Sui Discord https://discord.gg/sui and send !faucet *your wallet address* in devnet-faucet.

Clone the Sui repository:

git clone https://github.com/MystenLabs/sui.git --branch devnet

In the root/sui/sui_programmability folder we can see examples of smart contract code.

We can publish the first smart contract on Sui:

sui client publish sui/sui_programmability/examples/move_tutorial --gas-budget 30000

We have a Transaction Hash and we can go to Sui Explorer https://explorer.sui.io/?network=devnet to make sure that the transaction was successful.
Repeat these actions for other smart contracts:

sui client publish sui/sui_programmability/examples/nfts --gas-budget 30000

sui client publish sui/sui_programmability/examples/games --gas-budget 30000

etc.

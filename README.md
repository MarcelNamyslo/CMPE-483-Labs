# CMPE-483-Labs

## First Lab
First lab aimed to:

   1. set-up your browser to use the three Ethereum based blockchains: Bloxberg and Ava Fuji Test and Polygon Matic Mumbai test chains.
    
   2. to obtain free ethers from faucets and
    
   3. to practice sending ethers and exploring your transactions and addresses in the block explorers. 
   
Look up the instructions on the first lab [pdf](https://github.com/Mercyrion/CMPE-483-Labs/blob/main/1.%20Lab/lab01.pdf)

## Second Lab
First follow the [instructions](#installation-of-geth) below to install geth and set up the developer mode


## Installation of geth

Arch Linux via pacman

The Geth package is available from the community repo. It can be installed by running:
```sh
pacman -S geth
```

You can find the suitable installation option for your OS [here](https://geth.ethereum.org/docs/getting-started/installing-geth)

Go-Ethereum downloadpage is linked [here](https://geth.ethereum.org/downloads)

## Developer mode
You find the full instructions on the [Developer page](https://geth.ethereum.org/docs/developers/dapp-developer/dev-mode) of Go-Ethereum
<br />
### Start Geth in Dev Mode 

1. Open a terminal and use this to start Geth in Dev Mode

    ```sh
    geth --datadir [DIR] --dev --http --http.api eth,web3,net --http.corsdomain "http://remix.ethereum.org" --allow-insecure-unlock
    ```
    [DIR] should be the path to a local folder in which the geth files/keys etc. will be safed.

    A terminal will display the specific logs, confirming Geth has started successfully in developer mode and the local node is running.

    This terminal must be left running throughout the entire tutorial. 
 <br />

2. In a second terminal, attach a Javascript console. 
    ```sh
    geth attach [path to geth.ipc]
    ```
    the path should be the same as the path us used to start geth. You can also find the file in the folder you created in the command before
     <br />
    
3. Now the javacsript console is running. You can test it and display the existing accounts using eth.accounts:
    ```sh
    eth.accounts
    ```

# CMPE-483-Labs

## First Lab
First lab aimed to:

   1. set-up your browser to use the three Ethereum based blockchains: Bloxberg and Ava Fuji Test and Polygon Matic Mumbai test chains.
    
   2. to obtain free ethers from faucets and
    
   3. to practice sending ethers and exploring your transactions and addresses in the block explorers. 
   
Look up the instructions on the first lab [pdf](https://github.com/Mercyrion/CMPE-483-Labs/blob/main/1.%20Lab/lab01.pdf)

## Second Lab
1. For the first task A, you have to follow the [instructions](#installation-of-geth) below to install geth and set up the developer mode.

2. For the second task B, you can test your geth installation with the following commands:
    * ```sh
      eth.getBalance(eth.accounts[0])
      ```
    * ```sh
      eth.defaultAccount=eth.coinbase
      ```
    * ```sh
      eth.sendTransaction({from:eth.coinbase, to:
      "<Adress of a created Account>", value:web3.toWei(3, "ether"),
      gas:90000000, gasPrice: 200})
      ```
    * ```sh
      personal.unlockAccount(eth.accounts[0);
      ```
   Afterwards, you can try to load the javaScript file named rndsend.js into your javascript console. Herefore, you should use the full path
      ```sh
      loadScript("<path to file>/rndsend.js")
      ```
   Now you can call every function inside the rndsend.js function, e.g.
   
   ```sh
   sleep(10)
   ```
 <br />
 
3. In Task C, you will practice the Deployment of a Ethereum Smart Contract

    In your browser, visit the online compiler at the address: : https://remix.ethereum.org/ 
    
    Create a new file, name it helloworld and paste the following code:
    
    ```sh
    pragma solidity ^0.7.3;
    // SPDX-License-Identifier: AGPL-3.0-only
    
       contract HelloWorld {
             string public mymessage ;
             /* constructor */
             constructor(string memory mymsg) {
             mymessage = mymsg ;
       } 
       function message() public view returns (string memory) {
           return(mymessage);
       }
   }
    ```
    <br />
    
   Afterwards, you have to compile the helloworld.sol file in remix.
   
   
   
   ![image](https://github.com/Mercyrion/CMPE-483-Labs/assets/57272836/47c197de-b87f-4738-b7f6-6734cb031bc7)
   
   <br />
   
   To run the contract, you will have to create a javascript file to execute it in your javascript console. 
   Copy the abi in remix and paste it into abicontract[]. You can use the helloworldjavascript.js file which is located in the repo for this.
   
   ```sh
   var addresscontract = "0x………………………………." ;
   abicontract = [
   ……….
   ] ;
   hellocontract = web3.eth.contract(abicontract).at(addresscontract);
   eth.defaultAccount=eth.accounts[0] ;
   personal.unlockAccount(eth.accounts[0],"password",100) ;
   hellocontract.message() ;
   hellocontract.message({gas:4700000}) ;
   ```
    <br />
    
    Afterwards, you can try to load the javaScript file into your javascript console again. Use full path again!
    
      ```sh
      loadScript("<path to file>/helloworldjavascript.js")
      ```


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
     <br />
4. You can create a new account using Clef. Open up a new Terminal. A new account is then generated using the newaccount function on the command line:

      ```sh
      clef newaccount --keystore <path-to-keystore>
      ```
      
    

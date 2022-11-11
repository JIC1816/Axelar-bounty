# Link to the address that I used to "call contract with token" in Axelar Testnet

https://testnet.axelarscan.io/address/0xA0F2db443e98683d0fcf0b85de0ba54e5522f077

NOTE: this is my main testnet address but no my learnweb3 address. I didn't used my learnweb3 address because that's my personal address too; and as Haardik have teached us: you never should use your personal address if you are going to upload your work in a public repository.

# About what I did

In order to contribute to the documentation, here are some updates:

First of all, before using the commands to switch to the version of node specified by the "axelar-local-gmp-examples" repository, it is preferable to first try the version you already have. In principle there should be no problems. In my case it was like that.

Then, to deploy the "call-contract-with-token" contract, it is first necessary to change the index.js file associated with that contract. The fundamental change is to specify the Gas Limit, as shown here (credits to @hakymulla):

```bash
const sendTx = await source.contract.sendToMany(destination.name, destination.distributionExecutable, accounts, 'aUSDC', amount,
        {
            value: BigInt(4e17),
            gasLimit: 3e6
        });
```
Once the contract has been deployed, to run the tests it is necessary to update the "testnet.json" file located in the "info" folder. As you can see, that file contains the rpc and chainId of the Ropsten network, which is now deprecated. So the important thing is to change it to Goerli's data. In any case, if it doesn't work that way, it is possible to call the function using a network other than Ethereum's testen, eg Moonbeam and Polygon.

If everything went well, you can see here (https://testnet.axelarscan.io) that if you put your address it will show you the cross-chain transactions made thanks to Axelar.



        

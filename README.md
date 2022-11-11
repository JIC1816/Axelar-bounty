# Link to the address that I used to "call contract with token" in Axelar Testnet

https://testnet.axelarscan.io/address/0xA0F2db443e98683d0fcf0b85de0ba54e5522f077

NOTE: this is my main testnet address but no my learnweb3 address. I didn't used my learnweb3 address because that's my personal address too; and as Haardik have teached us: you never should use your personal address if you are going to upload your work in a public repository.

# About what I did

In order to contribute to the documentation, here are some updates:

First of all, before using the commands to switch to the version of node specified by the "axelar-local-gmp-examples" repository, it is preferable to first try the version you already have. In principle there should be no problems. In my case it was like that.

Then, to deploy the "call-contract-with-token" contract, it is first necessary to change the index.js file associated with said contract. The fundamental change is to specify the Gas Limit, as shown here:

```bash
const sendTx = await source.contract.sendToMany(destination.name, destination.distributionExecutable, accounts, 'aUSDC', amount,
        {
            value: BigInt(4e17),
            gasLimit: 3e6
        });
        ```
        

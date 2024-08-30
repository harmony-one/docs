# Using Hardhat

Follow until step 7 of the [Hardhat tutorial](https://hardhat.org/tutorial/)

Add Harmony testnet or mainnet entries to `hardhat.config.js` file.

```
require("@nomiclabs/hardhat-waffle");

// Replace this private key with your Harmony account private key
// To export your private key from Metamask, open Metamask and
// go to Account Details > Export Private Key
// Be aware of NEVER putting real Ether into testing accounts
const HARMONY_PRIVATE_KEY = "YOUR HARMONY PRIVATE KEY";

module.exports = {
  solidity: "0.8.0",
  networks: {
    testnet: {
      url: `https://api.s0.b.hmny.io`,
      accounts: [`0x${HARMONY_PRIVATE_KEY}`]
    },
    mainnet: {
      url: `https://api.harmony.one`,
      accounts: [`0x${HARMONY_PRIVATE_KEY}`]
    }
  }
};
```

Finally run:

```
npx hardhat run scripts/deploy.js --network testnet
```

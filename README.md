<div align=center> 
<img src="https://avatars.githubusercontent.com/u/88427645?s=200&v=4" style="border-radius:10px">
</div>

<center> Starter Kits React DAPP </center>

<center> An Polygon Starter Kit Tutorial containing React, @web3-react, Infura. </center>

## 0.Environment Setup

### Requirements 

#### Install ganache 
```javascripts
Download Package from https://www.trufflesuite.com/ganache
```

#### Create Your first Dapp
```javascripts
npx create-react-app {YOUR_PROJECT_NAME} --template polygon-starter-kit
cd {YOUR_PROJECT_NAME}
npm run start 
```


(npx comes from npm 5.2+ or later)

Then fireup your browser and go to http://localhost:3000/ to check your application.

When you are preparing to deploy your project to production settings, use npm run build to create a compressed bundle and deploy.

##### Immediate Configuration
There is no need for you to install or configurate tools like Webpack or Babel. They comes pre-configurated and hiddened, therefore you are provided with the full environment pack where you only need to worry about coding part.

Just create a project with the template, then you are good to go!


```javascripts
{YOUR_PROJECT_NAME}
├── README.md
├── node_modules
├── package.json
├── migrations 
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   └── manifest.json
└── src
	├── App.css
	├── App.js
	├── App.test.js
	├── assets
	│   ├── icon-devx.svg
	│   ├── logo512.png
	│   └── polygon-logo.svg
	├── components
	│   ├── Contents
	│   │   └── index.js
	│   ├── Footer
	│   │   ├── footer.css
	│   │   └── index.js
	│   ├── Headers
	│   │   └── index.js
	│   └── Wallet
	│       ├── ConnectWallet.js
	│       └── WalletInfo.js
	├── contracts
	│   └── Migrations.sol
	├── hooks
	│   └── index.js
	├── index.css
	├── index.js
	├── lib
	│   └── connectors
	│       └── index.js
	├── reportWebVitals.js
	└── setupTests.js
└── truffle-config.js
```

##### truffle-config.js  
```javascripts
const mnemonic = process.env.MNEMONIC;
const HDWalletProvider = require("@truffle/hdwallet-provider");


module.exports = {
  networks: {
    development: {
      host: "127.0.0.1",
      port: 7545,     
      network_id: "*" // Match any network id
    },
    polygon: {
      provider: new HDWalletProvider(mnemonic, process.env.POLYGON_RPC),
      network_id: 137,
      confirmations: 2,
      timeoutBlocks: 200,
      skipDryRun: true
    },
    mumbai: {
      provider: new HDWalletProvider(mnemonic, process.env.POLYGON_MUMBAI_RPC),
      network_id: 8001,
      confirmations: 2,
      timeoutBlocks: 200,
      skipDryRun: true
    }
```

Configure `.env` file
 ```
 vim .env
 MNEMONIC=" {YOUR_MNEMONIC OR YOUR_PRIVATE_KEY} "
 POLYGON_RPC = " {PUBLIC_POLYGON_RPC} OR https://rpc-mainnet.matic.network"
 POLYGON_MUMBAI_RPC = " {PUBLIC_POLYGON_MUMBAI_RPC} or https://rpc-mumbai.maticvigil.com/"
 ```
 
 More about `PUBLIC_RPC` ：[Development Docs](https://docs.matic.network/docs/develop/network-details/network)
 
## 1. Project Structure 	

#### Polygon-Starter-Kit
```javascripts
{YOUR_PROJECT_NAME}
├── README.md
├── node_modules
├── package.json
├── migrations 
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   └── manifest.json
└── src
	├── App.css
	├── App.js
	├── App.test.js
	├── assets
	│   ├── icon-devx.svg
	│   ├── logo512.png
	│   └── polygon-logo.svg
	├── components
	│   ├── Contents
	│   │   └── index.js
	│   ├── Footer
	│   │   ├── footer.css
	│   │   └── index.js
	│   ├── Headers
	│   │   └── index.js
	│   └── Wallet
	│       ├── ConnectWallet.js
	│       └── WalletInfo.js
	├── contracts
	│   └── Migrations.sol
	├── hooks
	│   └── index.js
	├── index.css
	├── index.js
	├── lib
	│   └── connectors
	│       └── index.js
	├── reportWebVitals.js
	└── setupTests.js
└── truffle-config.js
```


- `migrations` is used to contain JS scripts for smart contract migration and deployment
- `src` DAPP Client source code
- `src/contracts` For containing `smart contract`，and its also the contract location pointer in the truffle configuration
- `src/abis` for containing abi files after Truffle Compilation
- `hooks/index.js` initialize `Provider‘s` request hook in `@web3-react`

### Final Output
![sans-dapp](https://user-images.githubusercontent.com/67673060/154673761-a64b5ef0-360f-4b64-8cb1-357f4638fa4e.PNG)

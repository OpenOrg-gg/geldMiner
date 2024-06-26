
# Geld ERC20 Token Miner

The following repo is based on the 0xBitcoin miner.

This software has not been extensively tested nor updated for Geld.

Only the *BASIC* CPU miner model, when build from source, is confirmed working.

Given how hold this repo is, there is risk of supply chain attacks or other vulns in upstream packages that have not been vetted.

You should *ONLY* mine Geld with a new fresh wallet.

To proceed, build from source and use the miner-config-sample.json to create your config file named miner-config.json 

You'll need to ensure your wallet has enough ETH to pay gas fees.

### Building from Source

#### Setup (Windows/Linux)
1. Install NodeJS 10 (nvm install 10)
2. Clone/download the project
3. Open a terminal, cd into the project folder and run 'npm install' to install dependencies
4. Run the command 'npm run build' to build C files with node-gyp
6. Set up the config file 'miner-config.json' (duplicate miner-config-sample as a reference)
7. Start the miner with 'npm run miner'

#### Setup (Mac)
1. Install Homebrew & NodeJS 10
2. Run 'brew install yarn' to install yarn package manager
3. Clone/download this project
4. Open a terminal, cd into the project folder and run 'yarn'
5. Run the command 'yarn build' to build C files with node-gyp
6. Set up the config file 'miner-config.json' (duplicate miner-config-sample as a reference)
7. Start the miner with 'node index.js'


### NOT WORKING ?
Make sure you have build-essential installed to compile C code and make sure you have python3.

Try these commands:
> node-gyp rebuild



## Miner-Config.js File

You must create a file called 'miner-config.json' in the same directory as index.js.  Duplicate 'miner-config-sample.json' and rename it.  

If you do not have a public address or private key, use Metamask or another Etherum wallet to make them.

REMINDER: You >can< set the web3provider to a ropsten, mainnet, or other type of test-network provider and the software will still work. If solo mining (not to a pool) just be sure to define the correct contract address for that network and be sure your account has a small amount of ether (or test-ether).

    "mining_account_public_address":"0x111111",
    "mining_account_private_key":"1234567",
    "mining_style":"solo" OR "pool",
    "contract_address":"0xb6...",
    "pool_url":"http://tokenminingpool.com:8080",
    "gas_price_gwei":10,
    "cpu_thread_count": 1,
    "web3provider": "https://infura.io/API/apikey...."

---------------

### Getting Started
1. Duplicate the 'miner-config-sample.json' file and rename it to 'miner-config.json'
2. Set the parameters in this file appropriately
3. In the console, run the command 'node index.js' to start mining

### Solo Mining
- IF SOLO MINING it is necessary to fill the mining account (it is an Ethereum account) with a small amount of ether.  
- Typically 0.005 eth is good enough to get started.  The ether is used for gas to make function calls to the token smart contract when your miner finds a solution to the Proof of Work.  
- When the gas is spent that means that you have found a solution! If you were the first to find it, you will be rewarded with 0xbitcoin tokens.  (See the block explorer for typical gas prices at the current moment.)







### Testing

npm run test


## Credits

1. Zegordo (Developed the accelerated CPU Miner)

        ETH address [0x8AE981d92875C88f713600EB7dC4D23FA7E0E621]



## Tokens that can be mined using Proof of Work:

1. 0xBitcoin token - http://0xbitcoin.org - https://github.com/0xbitcoin/0xbitcoin-token

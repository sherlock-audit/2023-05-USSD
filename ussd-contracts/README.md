# USSD: Autonomous on-chain stablecoin

Solidity smart Contracts for USSD stablecoin.
First published draft for code review.

## Test instructions

`npm install`

In the course of your audit, you can and should use real contract data from the mainnet (Uniswap, DAI, etc.). Here is how you can set it up:

Firstly, install and start Ganache with the command below. Replace 'APIKEY' with the mainnet RPC of your choice:

    `ganache --fork.url https://mainnet.infura.io/v3/APIKEY`

Once Ganache is active, run Truffle using the default Ganache port as specified in truffle-config.js.
 
  networks: {
    mainnet_fork: {
      host: "127.0.0.1",     // Localhost (default: none)
      port: 8545,            // Standard Ethereum port (default: none)
      network_id: 1,       // Any network (default: none)
    },
  },
 
Then, you can run this using the standard command:

`yarn truffle console --network mainnet_fork`

After this, simply type `test` and it will run the provided test stand. This process will take between 60 to 120 seconds.

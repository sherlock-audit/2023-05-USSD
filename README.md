
# USSD - Autonomous Secure Dollar contest details

- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)

# Q&A

### Q: On what chains are the smart contracts going to be deployed?
Ethereum mainnet

The principle of what is wanted to be achieved is described in
https://github.com/USSDofficial/ussd-whitepaper/blob/main/whitepaper.pdf

The extended test/sim of the contract activity is written in
test/USSDsimulator.test.js
(please use ganache, fork mainnet and run it, it uses real DAI, Uniswap contracts. etc. to perform full cycle of operations)
___

### Q: Which ERC20 tokens do you expect will interact with the smart contracts? 
DAI, WETH, WBTC, WBGL
___

### Q: Which ERC721 tokens do you expect will interact with the smart contracts? 
none
___

### Q: Which ERC777 tokens do you expect will interact with the smart contracts? 
none
___

### Q: Are there any FEE-ON-TRANSFER tokens interacting with the smart contracts?

none
___

### Q: Are there any REBASING tokens interacting with the smart contracts?

none
___

### Q: Are the admins of the protocols your contracts integrate with (if any) TRUSTED or RESTRICTED?
There are DEFAULT_ADMIN_ROLE and STABLECONTROL roles defined. They have elevated privileges and are assumed to be TRUSTED actors.
___

### Q: Is the admin/owner of the protocol/contracts TRUSTED or RESTRICTED?
TRUSTED
___

### Q: Are there any additional protocol roles? If yes, please explain in detail:
STABLECONTROL, perform setting of some addresses and values regarding USSD and USSDRebalancer contract behaviour (realancing treshold, pool address, collateral ratios, base asset address)

None.
___

### Q: Is the code/contract expected to comply with any EIPs? Are there specific assumptions around adhering to those EIPs that Watsons should be aware of?
None.
___

### Q: Please list any known issues/acceptable risks that should not result in a valid finding.
Dependence on DAI and Uniswap. (however, risks related to price estimation etc. are valid)
___

### Q: Please provide links to previous audits (if any).

None.
___

### Q: Are there any off-chain mechanisms or off-chain procedures for the protocol (keeper bots, input validation expectations, etc)?
none. But it's expected for the USSDRebalancer.rebalance() function to be triggered at intervals, conditions (backend/keeper/anyone - it's public)
___

### Q: In case of external protocol integrations, are the risks of external contracts pausing or executing an emergency withdrawal acceptable? If not, Watsons will submit issues related to these situations that can harm your protocol's functionality.
No, we don't expect that this contract activity could be paused from outside.


___



# Audit scope


[ussd-contracts @ f44c726371f3152634bcf0a3e630802e39dec49c](https://github.com/USSDofficial/ussd-contracts/tree/f44c726371f3152634bcf0a3e630802e39dec49c)
- [ussd-contracts/contracts/USSD.sol](ussd-contracts/contracts/USSD.sol)
- [ussd-contracts/contracts/USSDRebalancer.sol](ussd-contracts/contracts/USSDRebalancer.sol)
- [ussd-contracts/contracts/interfaces/IStableOracle.sol](ussd-contracts/contracts/interfaces/IStableOracle.sol)
- [ussd-contracts/contracts/interfaces/IStaticOracle.sol](ussd-contracts/contracts/interfaces/IStaticOracle.sol)
- [ussd-contracts/contracts/interfaces/IUSSDRebalancer.sol](ussd-contracts/contracts/interfaces/IUSSDRebalancer.sol)
- [ussd-contracts/contracts/oracles/StableOracleDAI.sol](ussd-contracts/contracts/oracles/StableOracleDAI.sol)
- [ussd-contracts/contracts/oracles/StableOracleWBGL.sol](ussd-contracts/contracts/oracles/StableOracleWBGL.sol)
- [ussd-contracts/contracts/oracles/StableOracleWBTC.sol](ussd-contracts/contracts/oracles/StableOracleWBTC.sol)
- [ussd-contracts/contracts/oracles/StableOracleWETH.sol](ussd-contracts/contracts/oracles/StableOracleWETH.sol)



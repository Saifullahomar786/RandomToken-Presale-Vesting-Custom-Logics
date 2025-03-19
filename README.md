# RandomTokenPresale Contract README

## Overview

This is a Solidity smart contract for a presale of RandomToken tokens. It allows users to purchase tokens using either ETH or USDT. The contract includes features such as a bonus for early buyers, a wallet limit, vesting period for claiming tokens, and an owner who can start/end the presale and withdraw funds.

## Contract Details

### Key Features

- **Token Purchase**: Users can buy RandomToken tokens using either ETH or USDT.
- **Bonus Tokens**: The first 60 million tokens sold come with a 50% bonus.
- **Wallet Limit**: Each wallet can purchase up to 20 million tokens.
- **Vesting Period**: Tokens are vested over a period of 5 minutes (for testing purposes; should be longer in production).
- **Claim Tokens**: Users can claim their vested tokens after the presale ends.
- **Owner Controls**: The contract owner can start/end the presale and withdraw funds.

### Constants

- `TOKEN_PRICE`: The price of one RandomToken token in USDT (6 decimals).
- `TOTAL_TOKENS_FOR_SALE`: The total number of tokens available for sale.
- `BONUS_LIMIT`: The number of tokens that qualify for the 50% bonus.
- `WALLET_LIMIT`: The maximum number of tokens a wallet can purchase.
- `VESTING_PERIOD`: The time period for token vesting.
- `VESTING_DURATION`: The total duration of the vesting period.

### Events

- `TokensPurchased`: Emitted when tokens are purchased.
- `PresaleStarted`: Emitted when the presale is started.
- `PresaleEnded`: Emitted when the presale is ended.

### Functions

- `startPresale`: Starts the presale.
- `buyWithETH`: Buys tokens using ETH.
- `buyWithUSDT`: Buys tokens using USDT.
- `claimTokens`: Allows users to claim their vested tokens.
- `endPresale`: Ends the presale.
- `withdrawFunds`: Withdraws funds from the contract.

## Usage

### Prerequisites

- Install the OpenZeppelin and Chainlink contracts.
- Deploy the RandomToken token contract and the USDT token contract.
- Deploy the Chainlink price feed contract.

### Deployment

1. Compile the contract using a Solidity compiler.
2. Deploy the contract to the desired blockchain network.
3. Set the `owner` address during deployment.

### Interacting with the Contract

#### Starting the Presale

```solidity
contract.startPresale();
```

#### Buying Tokens with ETH

```solidity
contract.buyWithETH{value: amountInWei}();
```

#### Buying Tokens with USDT

```solidity
contract.buyWithUSDT(usdtAmount);
```

#### Claiming Tokens

```solidity
contract.claimTokens();
```

#### Ending the Presale

```solidity
contract.endPresale();
```

#### Withdrawing Funds

```solidity
contract.withdrawFunds();
```

## Security Considerations

- Ensure the Chainlink price feed is reliable and secure.
- Implement proper access controls for the owner functions.
- Test the contract thoroughly to avoid any vulnerabilities.

## License

This contract is licensed under the MIT License.


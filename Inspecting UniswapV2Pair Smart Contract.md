# Inspecting UniswapV2Pair Smart Contract

## Introduction

- Protocol Name: Uniswap V2
- Category: DeFi
- Smart Contract: UniswapV2Pair

## Function Analysis

- Function Name: `_safeTransfer`
- Block Explorer Link: https://etherscan.io/address/0xB4e16d0168e52d35CaCD2c6185b44281Ec28C9Dc#code
- Function Code:

Refer - https://etherscan.io/address/0xB4e16d0168e52d35CaCD2c6185b44281Ec28C9Dc#code#L343

```solidity
bytes4 private constant SELECTOR = bytes4(keccak256(bytes('transfer(address,uint256)')));

function _safeTransfer(address token, address to, uint value) private {
    (bool success, bytes memory data) = token.call(abi.encodeWithSelector(SELECTOR, to, value));
    require(success && (data.length == 0 || abi.decode(data, (bool))), 'UniswapV2: TRANSFER_FAILED');
}
```

- Used Encoding/Decoding or Call Method: `abi.encodeWithSelector`, `abi.decode`, `call` is used.

## Explanation

- Purpose: Explain the purpose of the function within the contract.
- Detailed Usage: Describe how the function utilizes the encoding/decoding or high/low level call. Explain why this method is used and what it achieves.
- Impact: Discuss the impact of this function on the smart contract. How does it contribute to the smart contract’s functionality within the protocol?

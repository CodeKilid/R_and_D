## lendingpool

we depoite our ETH and get WETH to make interact

we're going to create getWeth and import into aaveBorrow.

for withdraw we need Abi and contract address for call any contract. ---> in coding side.

after we compile we have the abi to interact with.

## what is Aave

https://github.com/AlizadeAlireza/defi_yeildStake_with_brownie__Token-Farm__#readme

the way Aave works is they actually have a contract, witch will point us to
the correct contract.

## lending pool contract

### ILendingPoolAddressesProvider

the contract that we're going to doing all the lending with is lending pool contract.

and we need a contract that get lending pool contract address.
the contract is LendingPoolContractAddressProvider.

for getting the contract address we create a function and try to get the address.
we need the address and Abi.
we have the address and we want to get Abi.
also we need to declare the contract compiler version in hardhat.config.js

we have a function that is getLendingPool that returns the address of lendingPool.

### ILendingPool

we have lending pool adderss and for lending pool contract we must get the contract Interface.

we must set @aave/protocolV2 and change the imports.

after that we get the pool address that is `0x7d2768dE32b0b80b7a3454c06BdAc94A69DDc7A9`
we want to deposite.

### deposite

safeTransferFrom() function going to pull the money out of our wallet.
so we need to approve the aave contract. so wa want the wethTokenAddress.

for approve we need to create approve function.

arguments:

    - contractAddress
    - spenderAddress = the contract that we're going to give the approval to to spend our token and the amount of it.
    - amountToSpend = how much to approve it.
    - account

in this function the spender address is lending pool address because we want to give the lending pool our
web token.

for deposit we call the function from contract and pass the arguments to it.
function deposit(address asset, uint256 amount, address onBehalfOf, uint16 referralCode) external;

we pass this function our weth address, amount of our token, deployer address and always zero to referralCode.

### borrowing from aave

for borrow we want to know how much we can borrow.
how much we have borrow, how much we have in collateral, how much we can borrow!!

for this we can use the function that be getUserAccountData() that Returns the user account data across all the reserves.

if our collateral is 1 ETH, don't mean we can borrow 1 ETH amount of assets.

each token has some different value like:

    - loan to value: if we deposit 1 ETH we can borrow just 75% of our collateral DAI.
    - Liquidation threshold: if we deposit 1 ETH and borrow more than 80% we got liquidated.
    and etc.

after that we create async function to get user data we can return that information just we need.

what the convertion of DAI is?!

we want to get how much we can borrow in ETH but we want to borrow DAI.
let's say like that:

    how much of DAI can we borrow based of the velue of EHT?!?!?

for this we use the priceFeeds.
in this interface we need to lastRoundData for getting the latest price of DAI.

after getting the DAI price with aggregator interface we want to know how much DAI we can borrow.
for this action we need convert it to DAI.

# REPAY

in this funtion we use amount that we want to repay, dai address and lending pool with the account.

when we borrow dai, we accrued interest.so we still owe dye back.
we can use uniswap to swap our ETH to dai for repay.

# Visualizing the Transactions

when we deposit our collateral, we actually get back what's called an aToken or interest bearing token.

this tokens keep track of how much collateral or in our case how much weth token
we have deposited in the Aave protocol.

when we want to withdraw our weth Back, we burn this atokens.

it is the token that is going up because the interest of our deposited collateral.

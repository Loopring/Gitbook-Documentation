# Submit erc20 order

## How to use `tradeCost`

To support small quantity trading, we introduce an additional concept "`tradeCost`", which is the minimum gas fee when a trade transaction is uplink to Ethereum.

Let's take LRC-ETH trading as an example.

Below are the steps:



### **1. Query api/v3/exchange/tokens to get the dust value of orderAmounts for both LRC and ETH**

The dust value is the minimum value to pass Relayer check. Any amount less than "dust" can't be traded. In this case, we will get both minTOkenLRC and minTokenETH after getting dust value. If user wants to convert LRC to ETH, the set LRC amount can't be less than minTokenLRC and the converted ETH amount can't be less than minTokenETH.



### **2. Query api/v3/user/orderUserRateAmount to get the tradeCost value.**

The parameters to call this interface are "accountId" and "market=LRC-ETH". In this example, we will get two tradeCost values for LRC and ETH as tradeCostLRC and tradeCostETH.



### **3. Set maxAllowBips = 50% as the maxFeeBips can't exceed 50%**



### **4. Set slippage as the slippage value user configured in UI (for example 0.1%)**

### **5. Caculate minCostLRC and minCostETH as below**

```
minCostLRC = max(minTokenLRC, tradeCostLRC/maxAllowBips)
minCostETH = max(minTokenETH, tradeCostETH/maxAllowBips)
```



### **6. Caculate the cost by considering slippage**

```
minCostLRCSlip = minCostLRC/(1-slippage)
minCostETHSlip = minCostETH/(1-slippage)
```



### **7. Cacluate the minimum quantity user has to set**

```
tradeCostSellLRC = max(tradeCostSellLRC, minTokenLRC) * 1.1
tradeCostSellETH = max(tradeCostSellETH, minTokenETH) * 1.1
```

Here we add additonally 10% tolerance.



### **8. Caculate the previous minimum token amount per calling api/v3/user/orderUserRateAmount (existing logic)**

This is the threshold to distinguish small quantity trading and normal trading\
We will get two values (configSellLRC and configSellETH) which are used for previous trading quantity limit (Per USD 100) caculation



### **9.Caculate the new maxFeeBips and start trading**

Let's take LRC->ETH as the example\
User inputs the amount of LRC to convert, amount = sellLRC

```
if sellLRC >= configSellLRC then 
	// Normal trading case, stay with previous logic
	maxFeeBips=63 (the default value for maxFeeBips)
	Trade 
else if sellLRC < tradeCostSellLRC then 
	// Really too small to support
	Prompt user the amount is too small to support
	Exit
else 
	// This is what we call as small quantity 
	costRate = Ceil(tradeCostETH/minbuyETH) 
	maxFeeBips = max(costRate, takerRate)
	Trade 
End If 

```

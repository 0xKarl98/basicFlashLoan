# What is this 
This is just the first challenge of damn-vulnerable-defi game , created by openzeppelin .

### Basic Idea 
We need to find another way to do the deposit job , since the balance of pool is only calculated with function depositTokens . 
If we deposit assets to the pool without using the function depositTokens , the balanceBefore would increase . However due to the assert 
statement poolBalance == balanceBefore , the poolBalance is still the same , so when we are using flashloan function , this would fail. 
After the initial transfer from the attacker to the pool , he will be able to transfer all the funds out since the security assert is no longer valid .

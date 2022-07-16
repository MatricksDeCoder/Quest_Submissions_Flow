# Quest_Submissions_Flow

# Chapter 1 

## Day 1 

1. A distributed immutable database that uses incentive schemes to ensure nont trusting parties can use the system assured that there is a single source of truth. The blocks or containers or storage of data is such that past history is linked to current data through proofs for exampel cryptographic that ensure its hard to change data hence immutability. 
2. Smart contract is just code that leaves on the blockchain and allows for reading and writing to the blockchain to achieve some desired functionalities
3. A script can only read from the Flow Blockchain is free whereas a Transaction can write or read data to the Flow Blockchain and costs money 

## Day 2

1. Safety + Security; Clarity; Developer Experience; Approachability; Resource Oriented Programming;
2. To ensure developers can quickly be onboarded to create secure smart contracts that are reliable and easy to reason about 

# Chapter 2

## Day 1 

Deploy contract + Read
```
access(all) contract JacobTucker {

  // Declare a public field of type String.
  //
  // All fields must be initialized in the init() function.
  access(all) let is: String

  // The init() function is required if the contract contains any fields.
  init() {
      self.is = "the best"
  }
  
}
------------------
import JacobTucker from 0x03

pub fun main()  {
    log(JacobTucker.is)
}

```
<img src="image1" />


## Day 2 

## Day 3 

## Day 4 



```cadence

```

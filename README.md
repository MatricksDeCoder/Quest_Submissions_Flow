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
<img src="image1.png" height="250" />

## Day 2 

1. scripts <- cant change data in the account on blockchain 
2. AuthAccount <- gives details about who is authorising and allows for access of data in the account 
3. prepare <- can access data in account and call functions on smart contract: execute <- can only call functions 
```
pub contract HelloWorld {

    pub var greeting: String
    pub var myNumber: Int

    pub fun changeGreeting(newGreeting: String) {
        self.greeting = newGreeting
    }

    pub fun updateMyNumber(newNumber: Int) {
        self.myNumber = newNumber
    }

    init() {
        self.greeting = "Hello, World!"
        self.myNumber = 0
    }
}
--------------------------------
import HelloWorld from 0x01

transaction(myNewNumber: Int) {
    prepare(account: AuthAccount) {}
    execute{
        HelloWorld.updateMyNumber(newNumber: myNewNumber)
    }
}
```
<img src="image2.png" height="250" />


## Day 3 

1. array
<img src="image3.png" height="250" />

2.
<img src="image4.png" height="250" />

3. It removes the optional from a type that allows it to take the value type or nil. For example reading object values returns the optional type so using ! forces it to be the type only. If nil is return program panics and stops execution. 
<img src="image5.png" height="250" />

4. It implies the return type which is optional String is not what is stated as return which is String type. We can fix it by unwrapping or returning Optional String
<img src="image6.png" height="250" />
<img src="image7.png" height="250" />

## Day 3 

```
pub contract BankAccount {

    pub var profiles: {Address: AccountProfile}
    
    pub struct AccountProfile {
        pub let fullName: String
        pub let birthday: String
        pub let type: String
        pub let amount: Int
        pub let account: Address

        init(_fullName: String, _birthday: String,_type: String, _account: Address) {
            self.fullName = _fullName
            self.birthday = _birthday
            self.type = _type
            self.amount = 0
            self.account = _account
        }
    }

    pub fun addProfile(fullName: String, birthday: String, type: String, account: Address) {
        let newAccountProfile = AccountProfile(_fullName: fullName, _birthday: birthday, _type: type, _account: account)
        self.profiles[account] = newAccountProfile
    }

    init() {
        self.profiles = {}
    }

}
```
<img src="image8.png" height="250" />
<img src="image9.png" height="250" />

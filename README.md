# Cadence_BC---quest-submission

# Chapter 1 Day 1

## Q1
I understand a blockchain as a database made a series of blocks which contain information. These blocks are created and stored so that they are available to the public. There is a set of rules to define how the block creation takes place, in case this rules change we can assume that the blockchain is at least an evolution of the first one, most times a different one.

## Q2
Smart contracts are automated programs stored in a blockchain that run if certain conditions are met. An example of that would be a decentralized exchange that when sending one token to a liquidity pool, it will swap it for another token and send it back.

## Q3
A transaction is some data which is processed by the blockchain and changes some of the information stored on it - like the balance of a wallet after paying for something. 
A script is a program written to read the information available on the blockchain - like reading the balance of a certain wallet on a certain date.

# Chapter 1 Day 2

## Q1
     Safety and Security
     Clarity
     Approachability
     Developer Experience
     Resource Oriented Programming
     
## Q2 
They are a very good approach to making smart contracts development better - easier to write, review, debug and maintain than other crypto programming languages and accesible to a wider group of people (not only developers). By doing this, it settles strong foundations for mainstream adoption.


# Chapter 2 Day 1

## Contract

![imagen](https://user-images.githubusercontent.com/107128136/173880586-bc5025cc-47b9-4dac-a32c-1418312ed16a.png)


## Script

```cadence 
import JakobTucker from 0x03

pub fun main(): String{
  return JakobTucker.is
}
```

![imagen](https://user-images.githubusercontent.com/107128136/173701460-bc3919cb-e163-4fd0-af04-99730d6555c7.png)

# Chapter 2 Day 2

## Q1
Since a script only reads data from the blockchain, calling the `changeGreeting` function which aims to modify the data would probably give back an error

## Q2
It allows the transaction to access data in your account by signing in the transaction.

## Q3 
The `prepare` phase aims at accessing the account data while the `execute` phase calls functions to modify the data on the blockchain. This separates the logic in two different phases but the execution coudl theoretically also work under the `prepare` phase. So takeaway is:
 - `prepare` allows you to access data in a account
 - `execute` is a different logical phase where data is modify by calling functions

## Q4

### Contract 

```cadence
pub contract JakobTucker {
  
  pub var is: String

  pub var myNumber: Int

  pub fun changeis(nowis: String) {
    self.is = nowis
  }

  pub fun updateMyNumber(newNumber: Int){
    self.myNumber = newNumber
  }

  init(){ 
    self.is = "the best" 
    self.myNumber = 0
  }
  
}
```
### Script

```cadence
import JakobTucker from 0x03

pub fun main(): Int{
  return JakobTucker.myNumber
}
```
`C2D2Q4 Script 
Result

{"type":"Int","value":"0"}`

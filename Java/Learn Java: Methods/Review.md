## LEARN JAVA: METHODS

### Review

Great work! Methods are a powerful way to abstract tasks away and make them repeatable. They allow us to define behavior for classes, so that the Objects we create can do the things we expect them to. Let’s review everything we have learned about methods so far.

* Defining a method : Methods have a method signature that declares their return type, name, and parameters
* Calling a method : Methods are invoked with a . and ()
* Parameters : Inputs to the method and their types are declared in parentheses in the method signature
* Changing Instance Fields : Methods can be used to change the value of an instance field
* Scope : Variables only exist within the domain that they are created in
* Return : The type of the variables that are output are declared in the method signature
* As you move through more Java material, it will be helpful to frame the tasks you create in terms of methods. This will help you think about what inputs you might need and what output you expect.

### Instructions

Now that we’ve learned about behavior, we can apply behavior to our SavingsAccount class using methods!

First, write a function called checkBalance() that prints:
```java
Hello!
Your balance is 
```
with the balance of the account displayed.

It should take in no parameters and return nothing.

Now, write a function called deposit() that takes in an int parameter amountToDeposit and adds it to the balance. It should return nothing.

If you want, you can also have the method print:
```java
You just deposited amountToDeposit
```
with the value of amountToDeposit displayed.

Now, write a function called withdraw() that takes in an int parameter amountToWithdraw and subtracts it from the balance. It should return the amountToWithdraw.

If you want, you can also have the method print:
```java
You just withdrew amountToWithdraw
```
with the value of amountToWithdraw displayed.

Test out your methods by trying to replace some of the code in the main() method with the equivalent methods!

Make sure to use checkBalance(), deposit(), and withdraw() at least once each.

Congratulations! You’ve made a basic SavingsAccount.

If you want, you can add more functionality to this! What other instance fields might you want to keep track of? What might a toString() look like for this class?

## My Code
```java
public class SavingsAccount {
  
  int balance;
  
  public SavingsAccount(int initialBalance){
    balance = initialBalance;
  }
  
  public void checkBalance(){
    System.out.println("Hello!");
    System.out.println("Your balance is "+balance);
  }
  
  public void deposit(int amountToDeposit){
    balance = amountToDeposit + balance;
    System.out.println("You just deposited " + amountToDeposit);
  }
  
  public int withdraw(int amountToWithdraw){
    balance = balance - amountToWithdraw;
    System.out.println("You just withdrew " + amountToWithdraw);
    return amountToWithdraw;
  }
  
  public String toString(){
    return "This is a savings account with " + balance + " saved.";
  }
  
  public static void main(String[] args){
    SavingsAccount savings = new SavingsAccount(2000);
    
    //Check balance:
    savings.checkBalance();
    
    //Withdrawing:
    savings.withdraw(300);
    
    //Check balance:
    savings.checkBalance();
    
    //Deposit:
    savings.deposit(600);
    
    //Check balance:
    savings.checkBalance();
    
    //Deposit:
    savings.deposit(600);
    
    //Check balance:
    savings.checkBalance();
    
    System.out.println(savings);
  }       
}

```

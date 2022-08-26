# Clarity Camp Concepts and Contract Calls Assignment

You've learned about `types`, `storing data`, `functions` & `control flow`, and how to make contract calls within `clarinet console`. <br><br>
Now it's time to get some hands on practice! :bowtie:

## Learning Goals :bulb:

- store data using `data members` and the correct `type signatures`
- write `functions` and use `control flow functions` as part of your expressions
- hop into `clarinet console` and practice making contract calls and using some handy commands

## Tasks :white_check_mark:

`balances.clar` has been created for you. You will write your code in this file. <br><br>

- [ ] write a `constant` called `CALLER` that represents the keyword `tx-sender`.

---

- [ ] write a `variable` called `totalTransfers` and initiate it as `u0`.

---
 
- [ ] write a `map` called `balances` to store a `principal` and corresponding balance.

*Hint: Maps store data in key value pairs. Balances will always be a positive number.*

---

As a user, I should be able to view an account’s stx balance.
- [ ] Write a function called `get-balance` that takes a single parameter of the principal whose account balance you want to find. <br>
The contract call looks like this: `(contract-call? .balances get-balance <principal>)`

*Hint: What type of function should this be? Can a built-in function expression help here? Will any parameters be needed?*

---

As a user, I should be able to transfer some stx to another account.
- [ ] Write a function called `transfer` that takes parameters of an amount you want to transfer and the principal who you are transferring that amount to.
This function should increment the value to `totalTransfers` and update the `balances` map to reflect the correct balance post-transfer for both the sender and the recipient. <br>
The contract call looks like this: `(contract-call? .balances transfer <amount> <principal>)`

*Hint: What type of function should this be? What parameters will you need from the caller? Check responses! Don't forget your constant.*

---

As a user, I should be able to view the total transfers made.
- [ ] Write a function called `get-total-transfers` that takes no parameters and retrieves the value of `totalTransfers`. <br>
The contract call looks like this: `(contract-call? .balances get-total-transfers)`
  
### Challenge! :muscle:

 - [ ] Take a look at your `transfer` function. Does it have a repeated expression? How could you clean this up?<br>
*Hint: Think about the function types available to you.*

## Contract Calls :telephone:

Now let's practice working within the console.

In your terminal, run `clarinet check`

You should get a passing check.<br>
*Note: You may get an unchecked data warning. If so, add this comment above your `transfer` function: <br>
`;; #[allow(unchecked_data)]`*

Now run `clarinet console`<br>
*Note: you can run `::help` in the console at any time to view the available commands.*

The table should display your contract identifier and available functions followed by your assets maps.<br>
Select a standard principal other than the deployer and copy the address. You will paste in this address to the calls where it says `<principal>`.

Practice by running the following calls in order within the console:

`(contract-call? .balances get-total-transfers)`<br><br>
`(contract-call? .balances transfer u1000 '<principal>)`<br><br>
`(contract-call? .balances get-balance tx-sender)`<br><br>
`(contract-call? .balances get-balance '<principal>)`<br><br>
`::get_assets_maps`<br><br>
`(contract-call? .balances get-total-transfers)`<br><br>
`(contract-call? .balances transfer u100000000000000 '<principal>)`<br><br>
`(contract-call? .balances get-total-transfers)`<br><br>
`(contract-call? .balances transfer u500 '<principal>)`<br><br>
`(contract-call? .balances get-total-transfers)`<br><br>

What do you notice?

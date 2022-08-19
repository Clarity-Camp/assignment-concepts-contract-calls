## Clarity Camp Concepts and Contract Calls Assignment

You've learned about `types`, `storing data`, `functions` & `control flow`, and how to make contract calls within `clarinet console`. <br><br>
Now it's time to get some hands on practice!

### Learning Goals

- store data using `data members` and the correct `type signatures`
- write `functions` and use `control flow functions` as part of your expressions
- hop into `clarinet console` and practice making contract calls and using some handy commands

### Tasks

- `balances.clar` has been created for you.<br><br>
  - write a `constant` called `CALLER` that represents the keyword `tx-sender`.<br><br>
  - write a `variable` called `totalTransfers` and initiate it as `u0`.<br><br>
  - write a `map` called `balances` to store a `principal` and corresponding balance.<br>
  *Hint: maps store data in key value pairs. Balances will always be a positive number.*<br><br>
  - write a function called `get-balance` that will retreive the data from the `balances map`. <br>
  *Hint: What type of function should this be? Can a built-in function expression help here? Will any parameters be needed?*<br><br>
  - write a function called `get-total-transfers` that will retreive the value of `totalTransfers`.<br><br>
  - write a function called `transfer` that will be responsible for a few things:<br><br>
  1. update the value of totalTransfers to increment by one. Go ahead and make this the first expression, this will help demonstrate how the control flow can be affected by `control-flow functions`.<br><br>
  2. transfer the specified amount of STX from the sender to the specified recipient.<br><br>
  3. update the `balances` map for both the sender and recipient with the post-transfer balance.<br>
  *Hint: What type of function should this be? What parameters will you need from the caller? Check responses! Don't forget your `constant`.*
  
#### Challenge!

If your `transfer` function has a repeated expression, how could you clean it up?<br>
*Hint: Think about the function types available to you.*

### Contract Calls

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

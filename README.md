# Vending_Machine
Project Description:
Initially, the customer must select the product followed by making the payment. After successful payment, the machine checks if the cancel button is pressed by the customer.
If the customer presses the cancel button, the money is returned to the customer. Else the machine checks the inserted money with the price of the selected product.
If both are equal, then the machine dispenses the product. If the inserted money is greater than the price, then the vending machine gives the appropriate product along with the change. If the inserted money is less than the price of the selected product, then the vending machine waits for the customer to add more money.

Key Features:
Accepts UPI payments (custom amount, not just ₹1/2/5 coins)
Offers multiple items with variable prices
Dispenses change if overpaid
Displays balance and status
Includes cancel and refund options

Inputs:
Signal Name	Width	Description
clk	1-bit	System clock
reset	1-bit	Asynchronous reset
upi_paid[7:0]	8-bit	Input amount paid via UPI in ₹ (0–255)
select_item[3:0]	4-bit	Select one of 16 items (IDs 0–15)
item_price[7:0]	8-bit	Price of selected item
cancel	1-bit	Cancel transaction
confirm	1-bit	Confirm purchase

Outputs:
Signal Name	Width	Description
vend	1-bit	Dispense item
change[7:0]	8-bit	Return change (if overpaid)
balance[7:0]	8-bit	Shows current paid amount
status[1:0]	2-bit	00=Idle, 01=Processing, 10=Vend, 11=Error

FSM States:
IDLE: Waiting for user action.
WAIT_PAYMENT: UPI amount being received.
VALIDATE_PAYMENT: Check if payment ≥ item price.
DISPENSE_ITEM: If valid, vend item and compute change.

RETURN_CHANGE: Return excess money.
CANCEL_REFUND: Refund full amount.
ERROR: Handle invalid input (e.g., insufficient funds).

The products available in the program are as follows.
Newspaper- priced at Rs.5
Cadbury bar- priced at Rs. 10
Tropicana juice- priced at Rs. 15


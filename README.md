# CashFlowMinimizer
<h2> Welcome to the Cash-Flow-Minimizer System README !! </h2>
The Cash Flow Minimizer project aims to minimize the number of transactions among multiple banks with different payment modes. It solves the problem of finding an optimal solution to settle the debts between banks using the minimum number of transactions.There is one world bank (with all payment modes) to act as an intermediary between banks that have no common mode of payment.
<br>
The algorithm used in this project is based on the concept of finding the net amount for each bank and then determining the transactions required to balance the cash flow. The algorithm consists of the following steps:<br>
1.Create a Bank class that represents each bank participating in the transactions. The Bank class has attributes such as the bank's name, net amount, and a set of payment modes it supports.
<br>
<br>
2.Implement the getMinIndex method, which finds the bank with the minimum net amount from the list of banks. It skips the bank if its net amount is already zero.
<br>
<br>
3.Implement the getSimpleMaxIndex method, which finds the bank with the maximum net amount from the list of banks. It skips the bank if its net amount is zero.
<br>
<br>
4.Implement the getMaxIndex method, which finds the bank with the maximum net amount and a common payment type with the bank having the minimum net amount. It iterates over the banks, checks if the net amount is positive, and finds the common payment type using the intersection operation on the sets of payment modes.
<br>
<br>
5.Implement the printAns method, which prints the transactions required for minimizing the cash flow. It iterates over the banks and prints the transactions between banks where the net amount is non-zero. It updates the net amounts and sets the transaction amounts to zero after printing.
<br>
<br>
6.Implement the minimizeCashFlow method, which performs the main cash flow minimization logic. It calculates the net amount for each bank and initializes an empty 2D graph to store the transaction amounts between banks. It iterates until all banks have a net amount of zero. In each iteration, it finds the bank with the minimum net amount and the bank with the maximum net amount and a common payment type. It determines the transaction amount and updates the net amounts accordingly. It also updates the graph with the transaction amounts.
<br>
<br>
7.Implement the main method, which serves as the entry point of the program. It prompts the user to input the number of banks, bank details (name, number of payment modes, and payment modes), number of transactions, and transaction details (sender bank, receiver bank, and amount). It then calls the minimizeCashFlow method with the provided inputs to calculate and print the minimum cash flow transactions.<br>
<br>
<br>
The Cash Flow Minimizer project uses data structures like arrays, lists, sets, and maps to store and process the bank and transaction information efficiently. The algorithm ensures that the cash flow is minimized by determining the optimal transactions between banks based on their net amounts and common payment types.Overall, this project provides a practical solution to optimize cash flow transactions among multiple banks, considering their different payment modes, and minimizes the number of transactions required to settle the debts.
<br>
<br>

# Cash Flow Minimizer Project

<h1> Welcome to the Cash-Flow-Minimizer System Introduction </h1>
The Cash Flow Minimizer project aims to minimize the number of transactions among multiple banks with different payment modes. It solves the problem of finding an optimal solution to settle the debts between banks using the minimum number of transactions.There is one world bank (with all payment modes) to act as an intermediary between banks that have no common mode of payment.
<br>
<br>
The algorithm used in this project is based on the concept of finding the net amount for each bank and then determining the transactions required to balance the cash flow. The algorithm consists of the following steps:
<br>
<br>
1. Create a Bank class that represents each bank participating in the transactions. The Bank class has attributes such as the bank's name, net amount, and a set of payment modes it supports.
<br>
<br>
2. Implement the getMinIndex method, which finds the bank with the minimum net amount from the list of banks. It skips the bank if its net amount is already zero.
<br>
<br>
3. Implement the getSimpleMaxIndex method, which finds the bank with the maximum net amount from the list of banks. It skips the bank if its net amount is zero.
<br>
<br>
4. Implement the getMaxIndex method, which finds the bank with the maximum net amount and a common payment type with the bank having the minimum net amount. It iterates over the banks, checks if the net amount is positive, and finds the common payment type using the intersection operation on the sets of payment modes.
<br>
<br>
5. Implement the printAns method, which prints the transactions required for minimizing the cash flow. It iterates over the banks and prints the transactions between banks where the net amount is non-zero. It updates the net amounts and sets the transaction amounts to zero after printing.
<br>
<br>
6. Implement the minimizeCashFlow method, which performs the main cash flow minimization logic. It calculates the net amount for each bank and initializes an empty 2D graph to store the transaction amounts between banks. It iterates until all banks have a net amount of zero. In each iteration, it finds the bank with the minimum net amount and the bank with the maximum net amount and a common payment type. It determines the transaction amount and updates the net amounts accordingly. It also updates the graph with the transaction amounts.
<br>
<br>
7. Implement the main method, which serves as the entry point of the program. It prompts the user to input the number of banks, bank details (name, number of payment modes, and payment modes), number of transactions, and transaction details (sender bank, receiver bank, and amount). It then calls the minimizeCashFlow method with the provided inputs to calculate and print the minimum cash flow transactions.<br>
<br>
The Cash Flow Minimizer project uses data structures like arrays, lists, sets, and maps to store and process the bank and transaction information efficiently. The algorithm ensures that the cash flow is minimized by determining the optimal transactions between banks based on their net amounts and common payment types.Overall, this project provides a practical solution to optimize cash flow transactions among multiple banks, considering their different payment modes, and minimizes the number of transactions required to settle the debts.
<br>
<h2>Getting Started</h2>
<pre>
Let's take an example. say we have the following banks:
1. World_bank
2. ICIC
3. Westpac
4. National_China_Bank
5. Goldman_Sachs
6. Nepal_national_bank
</pre>
<br>
This is represented below as a graph.

![Organization Structure Chart Infographic Graph](https://github.com/Sahruthak/CashFlowMinimizer/assets/107304838/d8527383-57bf-4a53-98f4-d3d870596620)

<pre>
Following are the payments to be done:
    Debtor Bank                  Creditor Bank           Amount
1.  Goldman_Sachs                World_Bank              Rs 300
2.  Goldman_Sachs                ICIC                    Rs 300
3.  Goldman_Sachs                National_China_Bank     Rs 200
4.  Goldman_Sachs                Westpac                 Rs 100
5.  World_Bank                   ICIC                    Rs 300
6.  ICIC                         National_China_Bank     Rs 200
7.  National_China_Bank          Westpac                 Rs 500
8.  Nepal_national_bank          World_Bank              Rs 500
9.  Nepal_national_bank          National_China_Bank     Rs 400
</pre>
<br>
This is represented below as a directed graph with the directed edge representing debts.

![Copy of Organization Structure Chart Infographic Graph](https://github.com/Sahruthak/CashFlowMinimizer/assets/107304838/aa6aad2a-e7dc-4166-84ee-5396b11aae33)

<br>
But there's a catch! Each Bank only supports a set of modes of payments and can make or receive payments only via those. Only World Bank suppports all modes of payments. In our current example we have only three payment modes:
<br>
Google_Pay
<br>
AliPay
<br>
Paytm
<br>
<hr>
<pre>
Following is the list of Banks and their supported payment modes :

World_Bank                  -   Google_Pay, AliPay, Paytm
National_China_Bank         -   AliPay, Paytm
ICIC                        -   Paytm, Google_Pay
Nepal_national _bank        -   AliPay
Westpac                     -   Google_Pay, Paytm
Goldman_Sachs               -   Paytm
</pre>
<br>
To pick the first Bank, we calculate the net amount for every Bank by using the below formula and store them in list:
<br>
<br>
net amount = [Sum of all credits(amounts to be received)] - [Sum of all debits(amounts to pay)]
<br>
<br>
Now the idea is that we are finding the bank which has minimum net amount(max debtor) (say Bank X, net amount x) and then finding the bank which has the maximum net amount( max creditor) (say Bank Y, net amount y) and also has a common payment mode (say M1) with the former bank. Then we find minimum of absolute value of x and y, lets call it z.
<br>
<br>
Now X pays the amount z to Y. Then 3 cases may arrived:
<br>
<br>
1. If (magnitude of x) < y => X is completely settled and so removed from the list.
<br>
2. If (magnitude of x) > y => Y is completely settled and so removed from the list.
<br>
3. If (magnitude of x) = y => X and Y both are completely settled and so both are removed from the list.
The same process is repeated for the remaining banks.
<br>
<br>
For the current example, the transactions for minimum cash flow are as follows:
<hr>

![Copy of Copy of Organization Structure Chart Infographic Graph](https://github.com/Sahruthak/CashFlowMinimizer/assets/107304838/6774d028-2a5d-4edd-9864-c984a2b367c8)

So this is the required answer.
<br>
<h2> How to Use? </h2>
This system is completely menu-driven. So when you will run the Java Application, it will guide you and show you the final output.
<br>
<br>
Below is the execution of our current example:
<br>
<br>

![CashOutput](https://github.com/Sahruthak/CashFlowMinimizer/assets/107304838/14b7ea60-ce2a-4f64-aeca-a3d2b8e7a0ae)

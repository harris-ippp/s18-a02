# Assignment 2: Welcome to Python

Given a loan with value `l`, `p` periods, and per-period interest rate `r`, the period payment is given mathematically as:

        r*l
    ------------
    1-(1+r)^(-p)

a. Write a python function to implementing this and save it in `mortgage.py`. Note that mortgage.py already contains the skeleton of the function:

```python
def mortgage_payment(value, periods, rate):
    return 0.0
```

b. Create an interactive mortgage calculator in the `calculator.py` file using the following steps:

 - Use the `input()` function to prompt the user to enter the following: Home Value, Down Payment, Term (in years), and (Annual) interest rate
 - Convert the inputted text values into floats
 - Calculate the loan amount (home value minus down payment)
 - Calculate the number of monthly periods in the loan
 - Calculate the monthly interest rate
 - Call your `mortgage_payment()` function
 - Print the answer rounded to the nearest cent using the [`math.round`](https://docs.python.org/3/library/functions.html#round) function.

For example, when the Home Value is $200,000 and down payment is $40,000 and the interest rate 4% and the term is 30 years, the program should look like:
```bash
$ python calculator.py
Home price: 200000
Down payment: 40000
Interest rate: 4
Loan term (years): 30

Monthly payment: 763.86
```

c. Create a new script called `table.py` that is similar to `calculator.py` except instead of prompting for a single down payment, prompts for a minimum and maximum down payment. Then for each $1000 increment in that range, print the corresponding monthly payment. For instance, in the example from (b) with down payment range $35,000 to $45,000 your output should look similar to this:

```bash
$ python table.py
Home price: 200000
Minimum down payment: 35000
Maximum down payment: 45000
Interest rate: 4
Loan term (years): 30

35000 787.74
36000 782.96
37000 778.19
38000 773.41
39000 768.64
40000 763.86
41000 759.09
42000 754.32
43000 749.54
44000 744.77
```

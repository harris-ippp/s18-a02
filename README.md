# Assignment 2: Welcome to Python

Given a loan with value `l`, `p` periods, and per-period interest rate `r`, the period payment is given mathematically as:

        r*l
    ------------
    1-(1+r)^(-p)

1. (4 points) Create a new file called `mortgage.py`. Write a python function to implementing the above calculation and save it in `mortgage.py`. Hint: start with this skeleton:
```python
# mortgage.py
def mortgage_payment(loan, periods, rate):
    return 0.0
```

2. (8 points) Create a new file called `calculator.py`. Create an interactive mortgage calculator in the `calculator.py` file using the following steps:

 - Use the `input()` function to prompt the user to enter the following: Home Value, Down Payment, Term (in years), and (Annual) interest rate
 - Convert the inputted text values into floats
 - Calculate the loan amount (home value minus down payment)
 - Calculate the number of monthly periods in the loan (years * 12)
 - Calculate the monthly interest rate (the entered rate divided by 100, then divided by 12)
 - Import the `mortgage` module from (a)
 - Call your `mortgage_payment()` function with the appropriate inputs
 - Import the `math` module
 - Print the answer rounded to the nearest cent using the [`round`](https://docs.python.org/3/library/functions.html#round) function.

For example, when the Home Value is $200,000 and down payment is $40,000 and the interest rate 4% and the term is 30 years, the program should look like:
```bash
$ python calculator.py
Home price: 200000
Down payment: 40000
Interest rate: 4
Loan term (years): 30

Monthly payment: 763.86
```

3. (8 points) Create a new file called `table.py` that is similar to `calculator.py` except instead of prompting for a single down payment, prompts for a minimum and maximum down payment. Then for each $1000 increment in that range, print the corresponding monthly payment. For instance, in the example from (b) with down payment range $35,000 to $45,000 your output should look similar to this:

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

4. (8 points) Which down payment amount results in a monthly payment of $750? Solve this problem using the bisection search method discussed in class. Put your solution in a script called `search.py` that looks like this when run:
```bash
$ python search.py
Home price: 200000
Interest rate: 4
Loan term (years): 30
Desired monthly payment: 750

Down payment: ????
```
Where the question marks are replaced with the down payment (within $.01) that results in a monthly payment of $750 per month.

Hints: Replace 

```Fc = c**2 - x``` 

that was used for the `sqrt(x)` example in class with

```Fc = mortgage_payment(...)```

Also, note that whereas the square root function was increasing in x, the mortgage payment function is decreasing in the down payment size. So you'll need to reverse the logic in the loop for updating the search interval.


**Financial Portfolio Analysis**
====================================

### Recruiter Takeaway
----------------------

• Expertise in data analysis and visualization using Python libraries (e.g., Pandas, Matplotlib)
• Ability to work with financial datasets and perform portfolio analysis
• Understanding of linear programming and optimization techniques

### Project Overview
-------------------

This project implements a financial portfolio analysis framework using linear programming. It aims to provide insights into the optimal investment strategy for a given set of funds.

### Business / Industry Context
------------------------------

The financial services industry relies heavily on data-driven decision making. This project is relevant to financial institutions, wealth managers, and investors seeking to optimize their portfolios.

### Dataset Overview
-------------------

Based on the code provided in `financial_portfolio.ipynb`, it appears that the dataset consists of two funds: 'Internet' and 'BlueChip'. The dataset also includes parameters such as total budget, maximum investment in Internet fund, and total risk.

### Key Insights
-----------------

#### Optimal Investment Strategy

The analysis shows that the optimal investment strategy for the given set of funds is to invest $20,000 in the Internet fund and $30,000 in the BlueChip fund. This results in a maximum return of $5,100.

### Tech Stack
--------------

#### Libraries Used

* Python 3.x
* Pandas for data manipulation
* Matplotlib for visualization

#### External Tools

* AMPL (Advanced Mathematical Programming Language) for linear programming and optimization

### Methodology
--------------

The methodology used in this project involves:

1. Defining the model using AMPL, including sets, parameters, decision variables, and objective function.
2. Providing input data to the model.
3. Using a solver (CBC) to optimize the objective function.

#### Code Organization

* `financial_portfolio.ipynb`: Main script for portfolio analysis
* `hw_Assignment 2_ Modeling and Solving Linear Programming Problems.pdf`: Homework assignment PDF used as context

### Business Impact
-------------------

The potential business impact of this project is to enable more informed investment decisions, leading to improved portfolio performance and potentially increased returns on investment.

### Future Work
--------------

Future work could include:

* Expanding the dataset to include additional funds
* Integrating other optimization techniques or machine learning models
* Developing a user-friendly interface for non-technical users

### Acknowledgments
-------------------

This project was completed as part of an academic assignment. The provided code and context are used solely for demonstration purposes.

### License
-----------

This project is released under the [MIT License](https://opensource.org/licenses/MIT).
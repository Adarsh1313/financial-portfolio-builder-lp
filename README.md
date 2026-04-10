# Financial Portfolio Optimization with Linear Programming

> Linear programming model for allocating capital across two investment funds under budget, risk, and fund-level exposure constraints.

---

## Problem Statement

An investment manager needs to allocate a fixed budget across available funds while respecting the client's risk tolerance and any fund-specific exposure limits. This project formulates the decision as a linear optimization problem so the portfolio can maximize projected annual return without violating the total budget or total risk constraints. Without this optimization, the allocation would rely more heavily on manual judgment and could leave return on the table or exceed the client's acceptable risk level.

---

## Dataset

| Property | Detail |
|----------|--------|
| Source | Portfolio parameters documented in the project report and implemented in the notebook and AMPL model. |
| Size | 2 investment options and 3 active decision constraints. |
| Key Features | Annual return rate, risk contribution per dollar invested, total budget, maximum Internet fund investment, total risk capacity |
| Target Variable | Investment amount in each fund that maximizes projected annual return |

---

## Methodology

The problem is modeled as a linear program with two decision variables: investment in the Internet fund and investment in the Blue Chip fund. The objective function maximizes projected annual return using fund return rates of 12% and 9%, while the constraints limit total investment to $50,000, cap Internet fund exposure at $35,000, and restrict total risk contribution to 240. The same optimization logic is implemented both in SciPy using `linprog` and in AMPL with the CBC solver, which provides a second implementation path for validation.

---

## Results

The optimal allocation invests $20,000 in the Internet fund and $30,000 in the Blue Chip fund, producing a maximum projected annual return of $5,100. In practical terms, the model recommends using the full available budget while keeping the portfolio exactly at the client's risk ceiling.

<!-- Metrics source: project report and notebook outputs -->

| Metric | Score | What It Means |
|--------|-------|---------------|
| Total budget used | $50,000 | The optimal solution deploys the full available investment budget. |
| Internet fund allocation | $20,000 | The higher-return fund is used, but not up to its maximum limit because the risk constraint is tighter. |
| Blue Chip fund allocation | $30,000 | The remaining capital is allocated to the lower-risk fund to preserve return while satisfying the portfolio constraints. |
| Maximum projected annual return | $5,100 | This is the best achievable return given the stated budget and risk limits. |
| Total risk contribution | 240 | The solution exactly uses the full allowed portfolio risk capacity. |
| Internet fund return rate | 12% | This fund offers the higher projected return but also the higher risk contribution. |
| Blue Chip fund return rate | 9% | This fund offers lower return with lower risk contribution, helping balance the portfolio. |

---

## Key Findings

- The portfolio reaches its optimum by fully using both the capital budget and the total risk allowance.
- The risk constraint is more influential than the Internet fund cap, since the optimal Internet allocation remains below the $35,000 maximum.
- A mixed allocation outperforms placing all available capital in the lower-risk fund while still avoiding excessive exposure to the higher-risk option.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core modeling language for the SciPy implementation |
| SciPy | Solves the linear program using `linprog` |
| Jupyter Notebook | Interactive implementation and preserved solver outputs |
| AMPL | Mathematical programming formulation of the same optimization problem |
| CBC Solver | Solves the AMPL model and confirms the optimal solution |

---

## How to Run

```bash
git clone https://github.com/Adarsh1313/financial-portfolio-builder-lp
cd financial-portfolio-builder-lp
pip install scipy notebook
jupyter notebook financial_portfolio.ipynb
```

If you want to run the AMPL version as well, you will also need an AMPL installation and a compatible solver such as CBC.

---

## Future Scope

- Expand the portfolio from two funds to a larger universe of assets with sector, liquidity, and concentration constraints.
- Add scenario analysis so the portfolio can be stress-tested under different return and risk assumptions.
- Package the optimization logic into a reusable decision tool for advisors who want to compare client portfolios under multiple risk tolerances.

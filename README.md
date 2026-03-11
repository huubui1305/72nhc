"""
72nhc - Vietnam Personal Income Tax Calculator (2026)

Updated for the new tax policy starting Jan 1, 2026
"""

PERSONAL_DEDUCTION = 15500000
DEPENDENT_DEDUCTION = 6200000

TAX_BRACKETS = [
    (10000000, 0.05),
    (30000000, 0.10),
    (60000000, 0.20),
    (100000000, 0.30),
    (float("inf"), 0.35),
]


def calculate_tax(income, dependents=0):
    """
    Calculate monthly PIT in Vietnam (2026)

    income: gross monthly income
    dependents: number of dependents
    """

    taxable_income = income - PERSONAL_DEDUCTION - dependents * DEPENDENT_DEDUCTION

    if taxable_income <= 0:
        return {
            "taxable_income": 0,
            "tax": 0
        }

    tax = 0
    previous_limit = 0

    for limit, rate in TAX_BRACKETS:

        if taxable_income > limit:
            tax += (limit - previous_limit) * rate
            previous_limit = limit
        else:
            tax += (taxable_income - previous_limit) * rate
            break

    return {
        "taxable_income": taxable_income,
        "tax": round(tax, 0)
    }

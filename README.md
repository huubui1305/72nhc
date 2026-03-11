from tax_calculator import calculate_tax

income = 35000000
dependents = 1

result = calculate_tax(income, dependents)

print("Income:", income)
print("Dependents:", dependents)
print("Taxable income:", result["taxable_income"])
print("Personal income tax:", result["tax"])

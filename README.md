# 72nhc

A simple open-source calculator for **Vietnam Personal Income Tax (PIT)** using the progressive tax system.

## Features

- Calculate monthly personal income tax
- Supports dependent deduction
- Based on Vietnam progressive tax brackets

## Tax Formula

Taxable income is calculated as:

Income - Personal Deduction - Dependent Deduction

Personal deduction: 11,000,000 VND  
Dependent deduction: 4,400,000 VND / person

## Tax Brackets

| Income Range | Tax Rate |
|---------------|-----------|
| 0 – 5M | 5% |
| 5M – 10M | 10% |
| 10M – 18M | 15% |
| 18M – 32M | 20% |
| 32M – 52M | 25% |
| 52M – 80M | 30% |
| >80M | 35% |

## Example

```bash
python example.py

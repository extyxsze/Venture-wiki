---
sidebar_position: 3
---

# Business Multipliers

## Rules

- One building can host **only one business**.
- Building fit affects three values:
  - `demand_mult` (customer interest)
  - `income_mult` (revenue efficiency)
  - `upkeep_mult` (operational cost)
- Final economy uses these multipliers in server-side calculation.

## Building Types

- `SKYSCRAPER`
- `OFFICE`
- `RETAIL`

## Multipliers by Business

| Business | SKYSCRAPER (D/I/U) | OFFICE (D/I/U) | RETAIL (D/I/U) |
|---|---:|---:|---:|
| coffeeshop | 0.82 / 0.90 / 1.10 | 0.90 / 0.95 / 1.04 | 1.12 / 1.08 / 0.98 |
| newsstand | 0.78 / 0.88 / 1.12 | 0.88 / 0.94 / 1.05 | 1.15 / 1.10 / 0.97 |
| foodtruck | 0.80 / 0.90 / 1.08 | 0.92 / 0.96 / 1.03 | 1.10 / 1.07 / 0.98 |
| laundromat | 0.86 / 0.92 / 1.10 | 1.00 / 1.00 / 1.04 | 1.08 / 1.06 / 0.99 |
| barbershop | 0.84 / 0.90 / 1.10 | 0.98 / 1.00 / 1.04 | 1.12 / 1.08 / 0.98 |
| carwash | 0.88 / 0.94 / 1.12 | 1.02 / 1.03 / 1.05 | 1.06 / 1.05 / 0.99 |
| gym | 0.94 / 0.98 / 1.09 | 1.05 / 1.04 / 1.03 | 1.06 / 1.05 / 1.00 |
| pharmacy | 0.90 / 0.96 / 1.10 | 1.00 / 1.01 / 1.04 | 1.14 / 1.10 / 0.98 |
| restaurant | 0.84 / 0.90 / 1.12 | 0.94 / 0.97 / 1.05 | 1.15 / 1.12 / 0.99 |
| lawoffice | 1.16 / 1.12 / 1.08 | 1.12 / 1.08 / 1.03 | 0.88 / 0.92 / 1.01 |
| nightclub | 0.90 / 0.95 / 1.14 | 0.96 / 0.98 / 1.07 | 1.10 / 1.08 / 1.02 |
| techstartup | 1.20 / 1.15 / 1.08 | 1.14 / 1.10 / 1.03 | 0.82 / 0.88 / 1.01 |
| hq | 1.00 / 1.00 / 1.00 | not available | not available |

> Legend: `D/I/U = demand_mult / income_mult / upkeep_mult`
> **Note:** `HQ` can only be established in a `SKYSCRAPER`.

## How it works

- **`demand_mult`** scales the base demand for the business. A **higher** value increases customer interest. Formula is: `demand = base_demand * demand_mult`
- **`income_mult`** scales the base income for the business. A **higher** value increases income. Formula is: `income = base_income * income_mult`
- **`upkeep_mult`** scales the base upkeep for the business. A **higher** value increases upkeep costs. Formula is: `upkeep = base_upkeep * upkeep_mult`

### Example
```bash
Let's say you have a coffeeshop in a RETAIL building (Base values = 100).

| Metric | Multiplier | Calculation | Final Result |
| Demand |    1.12    |  100 * 1.12 |      112     |
| Income |    1.08    |  100 * 1.08 |      108     |
| Upkeep |    0.98    |  100 * 0.98 |       98     |
```

So the coffeeshop in a RETAIL building will have:

- 112 % demand
- 108 % income
- 98 % upkeep

This means the income will be higher, because demand is also higher, and upkeep costs are gonna be lower then normally.
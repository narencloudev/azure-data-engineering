# Normalization and Relational Data Modeling

## Why normalize?
Normalization organizes data to reduce unnecessary duplication and prevent insert, update, and delete anomalies.

## Common normal forms
- **1NF**: each column holds atomic values; no repeating groups.
- **2NF**: in 1NF, and each non-key attribute depends on the whole candidate key (relevant to composite keys).
- **3NF**: in 2NF, and non-key attributes do not depend transitively on candidate keys.
- **BCNF**: every determinant is a candidate key.

## Example
Instead of repeating customer address details on every order row, store customer details in a customer table and reference the customer from orders.

## OLTP vs analytics modeling
- OLTP systems commonly use normalized models for reliable transactions.
- Analytical warehouses often use dimensional models, such as star schemas, to make reporting easier.

## Dimensional modeling basics
- **Fact table**: measurable business events, such as sales.
- **Dimension table**: descriptive context, such as customer, product, and date.
- **Grain**: exactly what one fact row represents.
- **Surrogate key**: warehouse-generated dimension key.
- **Slowly Changing Dimension**: technique for managing changes in dimension attributes.

## Practice
Define the grain of an order-line fact table and identify suitable dimensions.

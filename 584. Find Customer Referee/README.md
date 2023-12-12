# 584. Find Customer Referee

- Information: [Click Here!](https://leetcode.com/problems/find-customer-referee/?envType=study-plan-v2&envId=top-sql-50)

# 1. Introduction 

## Table: Customer

| Column Name | Type    |
|-------------|---------|
| id          | int     |
| name        | varchar |
| referee_id  | int     |

- In SQL, `id` is the primary key column for this table.
- Each row of this table indicates the id of a customer, their name, and the id of the customer who referred them.

## Problem Statement

Find the names of the customers that are not referred by the customer with `id = 2`.

Return the result table in any order.

### Example

#### Input:
Customer table:

| id | name | referee_id |
|----|------|------------|
| 1  | Will | null       |
| 2  | Jane | null       |
| 3  | Alex | 2          |
| 4  | Bill | null       |
| 5  | Zack | 1          |
| 6  | Mark | 2          |

#### Output:

| name |
|------|
| Will |
| Jane |
| Bill |
| Zack |

Explanation: Customers Will, Jane, Bill, and Zack are not referred by the customer with `id = 2`.

# 2. Solusion

<p align="right"> Using Microsoft SQL Server </p>

```sql
select name
from customer
where referee_id != 2 or referee_id is null;
```
#### Output:

| name |
|------|
| Will |
| Jane |
| Bill |
| Zack |

# 1378. Replace employee id with the unique identifier

- Information: [Click Here!](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/description/?envType=study-plan-v2&envId=top-sql-50)

# 1. Introduction 

## Table: Employees

| Column Name | Type    |
|-------------|---------|
| id          | int     |
| name        | varchar |

- `id` is the primary key (column with unique values) for this table.
- Each row of this table contains the `id` and the `name` of an employee in a company.

## Table: EmployeeUNI

| Column Name | Type    |
|-------------|---------|
| id          | int     |
| unique_id   | int     |

- `(id, unique_id)` is the primary key (combination of columns with unique values) for this table.
- Each row of this table contains the `id` and the corresponding `unique_id` of an employee in the company.

## Problem Statement

Write a solution to show the unique ID of each user. If a user does not have a unique ID, replace it with `null`.

Return the result table in any order.

### Example

#### Input:
Employees table:

| id | name     |
|----|----------|
| 1  | Alice    |
| 7  | Bob      |
| 11 | Meir     |
| 90 | Winston  |
| 3  | Jonathan |

EmployeeUNI table:

| id | unique_id |
|----|-----------|
| 3  | 1         |
| 11 | 2         |
| 90 | 3         |

#### Output:

| unique_id | name     |
|-----------|----------|
| null      | Alice    |
| null      | Bob      |
| 2         | Meir     |
| 3         | Winston  |
| 1         | Jonathan |

Explanation: 
- Alice and Bob do not have a unique ID; we will show `null` instead.
- The unique ID of Meir is 2.
- The unique ID of Winston is 3.
- The unique ID of Jonathan is 1.

# 2. Solusion

<p align="right"> Using Microsoft SQL Server </p>

```sql
select 
    unique_id,
    name
from Employees e
left join EmployeeUNI em on em.id = e.id;
```
#### Output:
| unique_id | name     |
|-----------|----------|
| null      | Alice    |
| null      | Bob      |
| 2         | Meir     |
| 3         | Winston  |
| 1         | Jonathan |

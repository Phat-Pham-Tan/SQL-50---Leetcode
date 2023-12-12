# 1683. Invalid Tweets

- Information: [Click Here!](https://leetcode.com/problems/invalid-tweets/?envType=study-plan-v2&envId=top-sql-50)

# 1. Introduction 

## Table: Tweets

| Column Name | Type    |
|-------------|---------|
| tweet_id    | int     |
| content     | varchar |

- `tweet_id` is the primary key (column with unique values) for this table.
- This table contains all the tweets in a social media app.

## Problem Statement

Write a solution to find the IDs of the invalid tweets. A tweet is considered invalid if the number of characters used in the content of the tweet is strictly greater than 15.

Return the result table in any order.

### Example

#### Input:
Tweets table:

| tweet_id | content                          |
|----------|----------------------------------|
| 1        | Vote for Biden                   |
| 2        | Let us make America great again! |

#### Output:

| tweet_id |
|----------|
| 2        |

Explanation: 
- Tweet 1 has a length of 14. It is a valid tweet.
- Tweet 2 has a length of 32. It is an invalid tweet.

# 2. Solusion

<p align="right"> Using Microsoft SQL Server </p>

```sql
select
    tweet_id
from tweets
where len(content) > 15;
```
#### Output:

| tweet_id |
|----------|
| 2        |

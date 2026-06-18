---
order: 1
---

# Top LeetCode SQL (Easy)

These questions test the absolute core of DQL (Data Query Language)—how well you can extract, filter, group, and perform simple math on data.

---

## The List

1. **[Combine Two Tables (175)](https://leetcode.com/problems/combine-two-tables/)**
   - *Concepts:* Basic `LEFT JOIN`, dealing with NULLs when the right side has missing data.

2. **[Employees Earning More Than Their Managers (181)](https://leetcode.com/problems/employees-earning-more-than-their-managers/)**
   - *Concepts:* Simple `SELF JOIN`. A fundamental test that you can join a table to itself effectively.

3. **[Customers Who Never Order (183)](https://leetcode.com/problems/customers-who-never-order/)**
   - *Concepts:* `NOT IN` vs `LEFT JOIN` where right table `IS NULL`. Testing set logic efficiency.

4. **[Classes More Than 5 Students (596)](https://leetcode.com/problems/classes-more-than-5-students/)**
   - *Concepts:* `GROUP BY` and utilizing the `HAVING` clause. They want to see if you know how to filter grouped aggregates correctly.

5. **[Big Countries (595)](https://leetcode.com/problems/big-countries/)**
   - *Concepts:* Boolean logic and `OR` efficiency vs `.UNION`.

6. **[Not Boring Movies (620)](https://leetcode.com/problems/not-boring-movies/)**
   - *Concepts:* Modulo operator `%` for checking odd numbers, mixed with string matching (`!=`).

7. **[Swap Salary (627)](https://leetcode.com/problems/swap-salary/)**
   - *Concepts:* Writing an `UPDATE` statement bundled with a `CASE` expression.

8. **[Duplicate Emails (182)](https://leetcode.com/problems/duplicate-emails/)**
   - *Concepts:* Finding duplicates quickly using `GROUP BY COUNT() > 1`.

9. **[Rising Temperature (197)](https://leetcode.com/problems/rising-temperature/)**
   - *Concepts:* Simple Date arithmetic natively (e.g., `DATEDIFF()` or `LAG()` on a Date axis).

10. **[Article Views I (1148)](https://leetcode.com/problems/article-views-i/)**
    - *Concepts:* Removing duplicate views via `DISTINCT` while comparing identical ids.

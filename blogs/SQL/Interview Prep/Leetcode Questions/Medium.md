---
order: 2
---

# Top LeetCode SQL (Medium)

Medium SQL questions typically test your capability to handle rolling calculations, handle complex aggregations over time/partition boundaries, or use subqueries heavily. Be prepared to deploy Window Functions on almost every question.

---

## The List

1. **[Second Highest Salary (176)](https://leetcode.com/problems/second-highest-salary/)**
   - *Concepts:* Testing if you know how to handle `NULL` gracefully if a second record doesn't exist. Often solved with `LIMIT` / `OFFSET` and `IFNULL`, or dense ranking.

2. **[Nth Highest Salary (177)](https://leetcode.com/problems/nth-highest-salary/)**
   - *Concepts:* Wrapping logic inside an actual SQL Function, treating `N` as an algorithmic parameter.

3. **[Rank Scores (178)](https://leetcode.com/problems/rank-scores/)**
   - *Concepts:* Core Window function problem: `DENSE_RANK() OVER (ORDER BY score DESC)`. A classic test of tie-breaking scenarios.

4. **[Consecutive Numbers (180)](https://leetcode.com/problems/consecutive-numbers/)**
   - *Concepts:* Checking successive historical rows. You can either use three nested self-joins, or more efficiently, deploy `LEAD()` and `LAG()`.

5. **[Exchange Seats (626)](https://leetcode.com/problems/exchange-seats/)**
   - *Concepts:* Heavy `CASE` logic integrated with modulo mathematics to swap ids dynamically without raw updates.

6. **[Department Highest Salary (184)](https://leetcode.com/problems/department-highest-salary/)**
   - *Concepts:* Correlated sub-query or Window function `RANK() OVER (PARTITION BY department_id)`. Testing your ability to find maxima grouped per category.

7. **[Managers with at Least 5 Direct Reports (570)](https://leetcode.com/problems/managers-with-at-least-5-direct-reports/)**
   - *Concepts:* Advanced aggregations spanning across a Self-Join relation.

8. **[Tree Node (608)](https://leetcode.com/problems/tree-node/)**
   - *Concepts:* Tricky categorical `CASE` definitions checking `IS NULL` on an adjacency list hierarchical data-model.

9. **[Investments in 2016 (585)](https://leetcode.com/problems/investments-in-2016/)**
   - *Concepts:* `IN` clauses bundled with counting Window Functions (`COUNT() OVER(PARTITION BY lat, lon)`).

10. **[Active Businesses (1126)](https://leetcode.com/problems/active-businesses/)**
    - *Concepts:* CTEs paired with conditional aggregation. Finding metrics across different groupings and comparing them against global averages simultaneously.

---
order: 3
---

# Top LeetCode SQL (Hard)

Hard questions on LeetCode mirror Senior Data Engineering loop questions. They expect robust, gapless queries that deal with nasty edge cases, complex time-series data gaps, graph traversals, and multi-layered CTE architectures.

---

## The List

1. **[Department Top Three Salaries (185)](https://leetcode.com/problems/department-top-three-salaries/)**
   - *Concepts:* The quintessential Hard SQL problem. Deploying `DENSE_RANK()` partitioned over a department group and wrapped inside a CTE to easily filter `WHERE rank <= 3`. 

2. **[Trips and Users (262)](https://leetcode.com/problems/trips-and-users/)**
   - *Concepts:* High-volume conditional aggregation calculating percentages. Requires careful handling of floating-point math (`ROUND(expr, 2)`) and double `JOIN` logic against banned status identifiers.

3. **[Human Traffic of Stadium (601)](https://leetcode.com/problems/human-traffic-of-stadium/)**
   - *Concepts:* One of the hardest "consecutive sequences" problems. Utilizing `ROW_NUMBER()` cleverness. Subtracting row number from an actual ID to create a static grouping identifier (the "Gaps and Islands" problem).

4. **[Tournament Winners (1194)](https://leetcode.com/problems/tournament-winners/)**
   - *Concepts:* Intense aggregation across disparate game columns (home vs away) requiring `UNION ALL` setups before summing scores. Followed immediately by tie-breaker ranking.

5. **[Market Analysis II (1159)](https://leetcode.com/problems/market-analysis-ii/)**
   - *Concepts:* Finding the `nth` particular action per user in a time series using Window functions, taking caution not to lose users who never hit that `nth` threshold (Left join caveats).

6. **[Average Salary: Departments VS Company (615)](https://leetcode.com/problems/average-salary-departments-vs-company/)**
   - *Concepts:* Time-based window aggregations overlaid against standard categorical groupings. Testing how you format periods dynamically (e.g., `YYYY-MM`).

7. **[Students Report By Geography (618)](https://leetcode.com/problems/students-report-by-geography/)**
   - *Concepts:* Manual creation of pivot tables using raw `CASE WHEN` aggregation paired against `ROW_NUMBER()`. Proves you deeply understand how `GROUP BY` functions natively parse arrays under the hood.

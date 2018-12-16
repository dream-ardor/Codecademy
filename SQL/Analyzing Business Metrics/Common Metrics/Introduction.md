Introduction

As a data scientist, when you're not investigating spikes or dips in your data, you might be building dashboards of KPIs, or key performance indicators for a company.

KPIs are often displayed on TVs on the walls of the office, and serve as high level health metrics for the business. While every company's metrics are defined slightly differently, the basics are usually very similar.

In this lesson we'll take a look at basic KPIs like Daily Revenue, Daily Active Users, ARPU, and Retention for a video game, Mineblocks.
This company has two tables, gameplays and purchases. The purchases table lists all purchases made by players while they're playing Mineblocks.

Complete the query to select from purchases.

The gameplays table lists the date and platform for each session a user plays.

Select from gameplays.

**My Code:**
```sql
select *
from gameplays
order by id
limit 10;
```

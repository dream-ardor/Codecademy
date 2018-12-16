Grouping with Case Statements

To see if our smoothie suspicion has merit, let's look at purchases by category. We can group the order items by what type of food they are, and go from there. Since our order_items table does not include categories already, we'll need to make some!

Previously we've been using group by with a column (like order_items.name) or a function (like date(orders.ordered_at)).

We can also use group by with expressions. In this case a case statement is just what we need to build our own categories. case statements are similar to if/else in other languages.

Here's the basic structure of a case statement:
```sql
case {condition}
  when {value1} then {result1}
  when {value2} then {result2}
  else {result3}
end
```

**Instructions:**
We'll build our own categories using a case statement. Complete the query below with a case condition of name that lists out each product, and decides its group.
```sql
select *,
  /**/
    when 'kale-smoothie'    then 'smoothie'
    when 'banana-smoothie'  then 'smoothie'
    when 'orange-juice'     then 'drink'
    when 'soda'             then 'drink'
    when 'blt'              then 'sandwich'
    when 'grilled-cheese'   then 'sandwich'
    when 'tikka-masala'     then 'dinner'
    when 'chicken-parm'     then 'dinner'
     else 'other'
  end as category
from order_items
order by id
limit 100;
```
Note that the else 'other' block catches all the products that don't meet the previous conditions.

Complete the query by using the category column created by the case statement in our previous revenue percent calculation. Add the denominator that will sum the amount_paid.

**Solution:**
```sql
select
  case name
    when 'kale-smoothie'    then 'smoothie'
    when 'banana-smoothie'  then 'smoothie'
    when 'orange-juice'     then 'drink'
    when 'soda'             then 'drink'
    when 'blt'              then 'sandwich'
    when 'grilled-cheese'   then 'sandwich'
    when 'tikka-masala'     then 'dinner'
    when 'chicken-parm'     then 'dinner'
    else 'other'
  end as category, round(1.0 * sum(amount_paid) /
    (select sum(amount_paid) from order_items) * 100, 2) as pct
from order_items
group by 1
order by 2 desc;
```

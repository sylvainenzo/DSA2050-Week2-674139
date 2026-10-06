BIKET NKOT SYLVAIN ENZO 
674139
## Objective

The goal of this lab was to combine three data sources (customers, orders and a regions lookup) into one reliable view of sales. You loaded them into pandas and SQLite, joined them and checked the join for problems before trusting any totals. You then used the cleaned data to find which customer segment, region and customers bring in the most money.

## Key findings

**1. Two data quality problems would have distorted the results.**
- Customer C004 (David) was listed twice, so his order was counted twice. That turned 15 orders into 16 rows and inflated sales from 113,500 to 122,600.
- Order O015 (9,900) belongs to customer C999, who isn't in the customers table. It has no name, segment or region.
- Dropping the duplicate fixed the totals, which now match at 113,500. The orphan order was kept because it is real revenue.

**2. Corporate is the top segment because its orders are larger, not more numerous.**
- Corporate earned 46,800 from 4 orders, about 41% of sales and an average of 11,700 per order.
- Retail had the most orders (6) but the lowest average (about 4,933).

**3. Nairobi is the top region mainly because it has more customers and orders.**
- Nairobi brought in 39,800 from 7 orders, about 35% of sales.
- Its average order is only about 5,686, compared with about 10,000 in Nakuru and Kisumu.
- The 9,900 orphan order can't be assigned to any region.

## Conclusion

The duplicate customer and the missing customer C999 were the biggest data quality problems. After cleaning, Corporate (46,800) is the top segment and Nairobi (39,800) is the top region and Brian being the customer with most number of totalsales. The main limitation is the small dataset of 15 orders, so these are patterns, not proof. The analysis also doesn't show how order count versus order size drives sales.
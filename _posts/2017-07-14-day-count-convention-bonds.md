---
ID: 536
post_title: Day Count Convention In Bonds
author: Naved
post_excerpt: ""
layout: post
permalink: >
  http://www.navedali.com/finance/fixed-income/bonds/day-count-convention-bonds
published: true
post_date: 2017-07-14 23:31:54
---
Day-count convention is used to calculate accrued interest between coupon payments. This convention helps to determine the number of days between payment, thus helping with calculation of how interest is accrued over a period. This convention dictates how the period between payments is calculated, by deciding numbers of days in a month and a year.
<ul>
 	<li><b>Coupon Value Calculation:</b> For sub annual coupon payments, day-count convention are used to calculate fraction of year on the payment day to determine payout.</li>
 	<li><b> Dirty Price Calculation:</b> To calculate how to what fraction of next coupon the seller is eligible based upon how long hes kept the security with him.</li>
</ul>
Most common day-count conventions are as follow.
<h3> 30/360  Method</h3>
This method assumes every year to be of 360 days with everything month having 30 days in them. A simple formula to calculate year fraction between two dates <code>D1/M1/Y1</code>and <code>D2/M2/Y2</code> could be.
<p align="center">
$latex 
{Fraction =\frac{ 360(Y_2 - Y_1) + 30(M_2 - M_1) + (D_2 - D_1)}{360}}&s=2
$
</p>
However, in reality not all the months are of 30 days, hence <code>D2-D1</code> will not render the result we expected. To counter handle this scenario, a more accurate formula will be as below.
<p align="center">
$latex 
{Fraction =\frac{ 360(Y_2 - Y_1) + 30(M_2 - M_1 - 1) + max(0, 30 - D_1) + min(30, D_2)}{360}}&s=2
$
</p>
Sample python class for such calculation
[code language="python"]

class Thirty360DayCountCalculator( DayCountCalculator ):
    &quot;&quot;&quot;
    A month is considered of 30 days and a year is of 360 days.
    ISDA recommended method for day count is
    360(y2-y1)+30(m2-m1-1)+max(0,30-d1)+min(30,d2)
    * Take year diff
    * Take month diff + 1 month to be adjusted by date
    * Since every month is 30 and reduce d1 from it, and take
    max with 0 in case result is negative ( days to 30 )
    * days in d2, min if more than 30
    &quot;&quot;&quot;
    @property
    def numerator(self):
        return 30

    @property
    def denominator(self):
        return 360

    def day_count(self, start, end):
        if end &lt;= start:
            return 0
        return 360*(end.year - start.year)\
               + 30*(end.month - start.month -1)\
               + max(0, 30 - start.day)\
               + min(30, end.day)
[/code]
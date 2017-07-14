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
 	<li>
<h4>Coupon Value Calculation:</h4>
For sub annual coupon payments, day-count convention are used to calculate fraction of year on the payment day to determine payout.</li>
 	<li>
<h4> Dirty Price Calculation:</h4>
To calculate how to what fraction of next coupon the seller is eligible based upon how long hes kept the security with him.</li>
</ul>
Most common day-count conventions are as follow.
<h3> 30/360  Method</h3>
This method assumes every year to be of 360 days with everything month having 30 days in them. Rough formula to calculate year fraction between two dates <span style="color: #222222; font-family: monospace;"><span style="background-color: #e9ebec;">D1/M1/Y1 </span></span>and <code>D2/M2/Y2</code> could be.

$latex \normal

Fraction = \frac{ 360(Y_2 - Y_1) + 30(M_2 - M_1) + (D_2 - D_1)}{360}

$
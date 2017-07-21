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
Day-count convention is used to calculate accrued interest between coupon payments. This convention helps to determine the number of days between payment, thus helping with calculation of how interest is accrued over a period. This convention dictates how the period between payments is calculated, by deciding numbers of days in a month and a year for below.
<ul>
 	<li><b>Coupon Value Calculation:</b> For sub annual coupon payments, day-count convention are used to calculate fraction of year on the payment day to determine payout.</li>
 	<li><b> Dirty Price Calculation:</b> To calculate how to what fraction of next coupon the seller is eligible based upon how long hes kept the security with him.</li>
</ul>
Most common day-count conventions are as follow.
<h3> 30/360  Method</h3>
This method assumes every year to be of 360 days with everything month having 30 days in them. Since 360 is highly factor-able, calculation of payment frequency is easier and payment amount is constant over payment periods. It is often used in calculation of accrued interest for Corporate, Agency, Municipal Bonds and also MBS. A simple formula to calculate year fraction between two dates <code>D1/M1/Y1</code>and <code>D2/M2/Y2</code> could be.
<p align="center">$latex
{Fraction =\frac{ 360(Y_2 - Y_1) + 30(M_2 - M_1) + (D_2 - D_1)}{360}}&amp;s=2
$</p>
However, in reality not all the months are of 30 days, hence <code>D2-D1</code> will not render the result we expected. To counter handle this scenario, a more accurate formula will be as below.
<p align="center">$latex
{Fraction =\frac{ 360(Y_2 - Y_1) + 30(M_2 - M_1 - 1) + max(0, 30 - D_1) + min(30, D_2)}{360}}&amp;s=2
$</p>

<h3>Actual/360  Method</h3>
This convention calculates actual differences between dates, but assumes year to be of 360 day. It is mostly used in used in money markets for short-term lending of currencies with maturity of one year or less it. This method is also called the French convention.A simple formula to calculate year fraction between two dates <code>D1/M1/Y1</code>and <code>D2/M2/Y2</code> could be.
<p align="center">$latex
{Fraction =\frac{ (D_2/M_2/Y_2 - D_1/M_1/Y_1)Days}{360}}&amp;s=2
$</p>

<h3>Actual/Actual Method</h3>
This is the convention used for US Treasury bonds and notes, among other securities. This method calculates fractions of leap and non leap years separately and then combines them.
<p align="center">$latex
{Fraction =\frac{(Days not in leap year)}{365} }+\frac{(Days in leap year)}{366} }&amp;s=2
$</p>
<a href="https://github.com/anaved/bond-concepts/blob/master/src/calc/daycounter.py">Python implementation of day count conventions</a> can be found at my <a href="https://github.com/anaved/bond-concepts">GitHub Bond Concepts repository .</a>
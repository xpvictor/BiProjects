<h2><p>Percentual of average of Order by customer related of same period of last year</p></h2>

>_%SPLY avg Order by customer = <br>
>var vLastYear = <br>
>CALCULATE(<br>
>    [[_AVG Order by customer]](/Measures/Overall/_AVG%20Order%20by%20customer.md),<br>
>    SAMEPERIODLASTYEAR(dimCalendar[Date]))<br>
>
>var vPercent = <br>
>DIVIDE([[_AVG Order by customer]](/Measures/Overall/_AVG%20Order%20by%20customer.md) - vLastYear, vLastYear)<br>
>
>return vPercent
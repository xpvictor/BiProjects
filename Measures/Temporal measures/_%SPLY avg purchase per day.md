<h2><p>Percentual of average of purchase per day related of same period of last year</p></h2>

>_%SPLY avg purchase per day = <br>
>var vLastYear = <br>
>CALCULATE(<br>
>    [[_AVG purchase interval]](/Measures/Overall/_AVG%20purchase%20interval.md),
>    SAMEPERIODLASTYEAR(dimCalendar[Date]))
>
>var vPercent = 
>DIVIDE([[_AVG purchase interval]](/Measures/Overall/_AVG%20purchase%20interval.md) - vLastYear, vLastYear)
>
>return vPercent
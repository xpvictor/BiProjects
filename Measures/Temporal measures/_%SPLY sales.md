<h2><p>Percentual sales related of same period of last year</p></h2>

>_%SPLY sales = <br>
>var vLastYear = <br>
>CALCULATE(<br>
>    [[_Sales]](/Measures/Overall/_Sales.md),
>    SAMEPERIODLASTYEAR(dimCalendar[Date]))
>
>var vPercent =<br> 
>DIVIDE([[_Sales]](/Measures/Overall/_Sales.md) - vLastYear, vLastYear)
>
>return vPercent
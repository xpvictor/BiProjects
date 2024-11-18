<h2><p>Percentual of average of units sold per order related of same period of last year</p></h2>

>_%SPLY avg quantity per sales = <br>
>var vLastYear = <br>
>CALCULATE(
>    [[_AVG quantity per sales]](/Measures/Overall/_AVG%20quantity%20per%20sales.md),
>    SAMEPERIODLASTYEAR(dimCalendar[Date]))
>
>var vPercent = <br>
>DIVIDE([[_AVG quantity per sales]](/Measures/Overall/_AVG%20quantity%20per%20sales.md) - vLastYear, vLastYear)
>
>return vPercent
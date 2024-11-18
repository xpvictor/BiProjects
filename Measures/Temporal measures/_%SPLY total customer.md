<h2><p>Percentual Customers related of same period of last year</p></h2>

>_%SPLY total customer = <br>
>var vLastYear = <br>
>CALCULATE(
>    [[_Total customers]](/Measures/Overall/_Total%20customers.md),
>    SAMEPERIODLASTYEAR(dimCalendar[Date]))
>
>var vPercent = <br>
>DIVIDE([[_Total customers]](/Measures/Overall/_Total%20customers.md) - vLastYear, vLastYear)
>
>return vPercent
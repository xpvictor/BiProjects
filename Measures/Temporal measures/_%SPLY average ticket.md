<h2><p>Percentual of average ticket related of same period of last year</p></h2>

>_%SPLY average ticket =  <br>
>var vLastYear = <br>
>CALCULATE(<br>
>    [[_$ average ticket]](/Measures/Overall/_$%20average%20ticket.md),<br>
>    SAMEPERIODLASTYEAR(dimCalendar[Date]))<br>
>
>var vPercent = <br>
>DIVIDE([[_$ average ticket]](/Measures/Overall/_$%20average%20ticket.md) - vLastYear, vLastYear)<br>
>
>return vPercent


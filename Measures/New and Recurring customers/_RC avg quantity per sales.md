<h2><p>Measure transformed into text </p></h2>

>_RC avg quantity per sales = <br>
>CALCULATE(<br>
>    [[_AVG quantity per sales]](/Measures/Overall/_AVG%20quantity%20per%20sales.md),<br>
>    ALL(factSales[Customer type]),<br>
>    factSales[Customer type] = "Recurring Customer")
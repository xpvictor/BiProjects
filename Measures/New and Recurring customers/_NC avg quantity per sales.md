<h2><p>Average units per sales only for for New customers</p></h2>

>_NC avg quantity per sales = <br>
>CALCULATE(<br>
>    [[_AVG quantity per sales]](/Measures/Overall/_AVG%20quantity%20per%20sales.md),<br>
>    ALL(factSales[Customer type]),<br>
>    factSales[Customer type] = "New customer")
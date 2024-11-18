<h2><p>Total of customers only for for Recurring customers</p></h2>

>_NC total customer = <br>
>CALCULATE(<br>
>    [[_Total customers]](/Measures/Overall/_Total%20customers.md),<br>
>    ALL(factSales[Customer type]),<br>
>    factSales[Customer type] = "Recurring customer")
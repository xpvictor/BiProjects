<h2><p>Average ticket only for for Recurring customers</p></h2>

>_RC  average ticket = <br>
>CALCULATE(<br>
>    [[_S average ticket]](/Measures/Overall/_$%20average%20ticket.md),<br>
>    ALL(factSales[Customer type]),<br>
>    factSales[Customer type] = "New customer")
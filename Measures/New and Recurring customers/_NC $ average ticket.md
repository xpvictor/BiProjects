<h2><p>Measure transformed into text </p></h2>

>_NC average ticket = <br>
>CALCULATE(<br>
>    [[_$ average ticket]](/Measures/Overall/_$%20average%20ticket.md),<br>
>    ALL(factSales[Customer type]),<br>
>    factSales[Customer type] = "New customer")
<h2><p>Dynamic measure used to change the measures inserted in the graphs - Only for Recurring Customers </p></h2>

>_RC dynamic measures = <br>
>SWITCH(<br>
>    TRUE(),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 1,<br>
>    [[_RC total customer]](/Measures/New%20and%20Recurring%20customers/_RC%20total%20customer.md),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 2,<br>
>    [[_RC S average ticket]](/Measures/New%20and%20Recurring%20customers/_RC%20$%20average%20ticket.md),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 3,<br>
>    [[_RC avg quantity per sales]](/Measures/New%20and%20Recurring%20customers/_RC%20avg%20quantity%20per%20sales.md)   <br> 
>    )
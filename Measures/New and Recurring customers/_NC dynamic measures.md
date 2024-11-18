<h2><p>Dynamic measure used to change the measures inserted in the graphs - Only for New Customers </p></h2>

>_NC dynamic measures = <br>
>SWITCH(<br>
>    TRUE(),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 1,<br>
>    [[_NC total customer]](/Measures/New%20and%20Recurring%20customers/_NC%20total%20custome.md),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 2,<br>
>    [[_NC S average ticket]](/Measures/New%20and%20Recurring%20customers/_NC%20$%20average%20ticket.md),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 3,<br>
>    [[_NC avg quantity per sales]](/Measures/New%20and%20Recurring%20customers/_NC%20avg%20quantity%20per%20sales.md)   <br> 
>    )
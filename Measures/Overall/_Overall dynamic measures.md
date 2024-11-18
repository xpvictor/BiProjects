<h2><p>Dynamic measure used to change the measures inserted in the graphs </p></h2>

>_Overall dynamic measures = <br>
>SWITCH(<br>
>    TRUE(),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 1,<br>
>    [[_Total customers]](/Measures/Overall/_Total%20customers.md),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 2,<br>
>    [[_$ average ticket]](/Measures/Overall/_$%20average%20ticket.md),<br>
>    SELECTEDVALUE('_Dynamic buttons'[Button ID]) = 3,<br>
>    [[_AVG quantity per sales]](/Measures/Overall/_AVG%20quantity%20per%20sales.md)    <br>
>    )
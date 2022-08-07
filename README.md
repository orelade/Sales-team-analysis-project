# Sales-team-analysis-project
This is the analysis of sales data for a team of sales persons stakeholders.

in this report i created a data model,measures and columns in power bi to derive a user centred dashboard 
-----------------------------------------------------------------------------------------------
Welcome text = 
VAR Hour = HOUR(NOW())
VAR Greeting =
SWITCH(
    TRUE(),
    HOUR >= 0 && HOUR < 5, "Good Night",
    HOUR >= 5 && HOUR < 12, "Good Morning",
    HOUR >= 12 && HOUR < 18, "Good Afternoon",
    HOUR >= 18 && HOUR < 24, "Good Evening"
)
RETURN
Greeting & " " & SELECTEDVALUE(sales[Sales Person])
---------------------------------------------------------------------------------------------
Total Profit = [Revenue] - [Total Cost]
---------------------------------------------------------------------------------------------
Total Cost = SUM(sales[Cost])
---------------------------------------------------------------------------------------------
Revenue = SUM(sales[Amount])
----------------------------------------------------------------------------------------------
Profit% = DIVIDE([Total Profit],[Revenue])
----------------------------------------------------------------------------------------------
Cost = [Boxes] * RELATED(products[Cost per box]) 

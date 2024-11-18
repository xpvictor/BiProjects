<h2><p>This folder contains all the data sources used in the project with the steps applied</p></h2>

<h3>_Dynamic buttons</h3>
<h4>This data source was built using the <i>Enter data</i> option with the following information:</h4>

| Button ID | Button name     |
|-----------|-----------------|
| 1         | Total customer  |
| 2         | Average ticket  |
| 3         | Qt. per sales   |


<h3>dimCalendar</h3>

> let<br>
>     dataMin = List.Min(factSales[Date first purchase]),<br>
>     dataMax = List.Max(factSales[Date first purchase]),<br>
>     qtdDays = Duration.Days(dataMax - dataMin) +1,<br>
>     listDates = List.Dates(dataMin, qtdDays, #duration(1,0,0,0)),<br>
>     #"Converted to Table" = Table.FromList(listDates, Splitter.SplitByNothing(), null, null, ExtraValues.Error),<br>
>     #"Changed Type" = Table.TransformColumnTypes(#"Converted to Table",{{"Column1", type date}}),<br>
>     #"Renamed Columns" = Table.RenameColumns(#"Changed Type",{{"Column1", "Date"}}),<br>
>     #"Inserted Year" = Table.AddColumn(#"Renamed Columns", "Year", each Date.Year([Date]), Int64.Type),<br>
>     #"Inserted Month" = Table.AddColumn(#"Inserted Year", "Month", each Date.Month([Date]), Int64.Type),<br>
>     #"Inserted Month Name" = Table.AddColumn(#"Inserted Month", "Month Name", each Date.MonthName([Date]), type text),<br>
>     #"Inserted First Characters" = Table.AddColumn(#"Inserted Month Name", "Month abrev", each Text.Start([Month Name], 3), type text),<br>
>     #"Inserted Merged Column" = Table.AddColumn(#"Inserted First Characters", "mont/year", each Text.Combine({[Month abrev], "/", Text.From([Year], "pt-BR")}), type text),<br>
>     #"Inserted Merged Column1" = Table.AddColumn(#"Inserted Merged Column", "index", each Text.Combine({Text.From([Year], "pt-BR"), Text.From([Month], "pt-BR")}), type text),<br>
>     #"Added Custom Column" = Table.AddColumn(#"Inserted Merged Column1", "Month abr/year", each Text.Combine({[Month abrev], "-", Text.Middle(Text.From([Year], "pt-BR"), 2)}), type text)<br>
> in<br>
>     #"Added Custom Column"<br>

<h3>factSales</h3>

> let<br>
>     Source = Python.Execute("import pandas as pd#(lf)import numpy as np#(lf)df_sales = pd.read_excel('C:/Users/victo/OneDrive/Documentos/Cursos/Projetos em Power BI/Análise de cliente/sales_data.xlsx')#(lf)df_customer = pd.read_excel('C:/Users/victo/OneDrive/Documentos/Cursos/Projetos em Power BI/Análise de cliente/customer_data_analysis.xlsx')#(lf)df_customer = df_customer[['CustomerKey','Gender','Birth Date','Date first purchase']]#(lf)#Creating a dataframe with values grouped by CustomerKey#(lf)df_sales = df_sales.groupby('CustomerKey').agg({#(lf)    'Quantidade SKU' : 'sum',#(lf)    'Receita' : 'sum',#(lf)    'ID order' : 'count'}).rename(columns ={#(lf)    'ID order' : 'Sales',#(lf)    'Quantidade SKU' : 'Quantity SKU',#(lf)    'Receita' : 'Amount'})#(lf)#Adding a column to identify the customer type#(lf)df_sales['Customer type'] = np.where(df_sales['Sales'] == 1, 'New customer', 'Recurring customer')#(lf)df_sales = df_sales.reset_index()#(lf)df_sales = df_sales.merge(df_customer,on='CustomerKey')#(lf)df_sales['Amount'] = df_sales['Amount'].apply(lambda x: str(x).replace('.',','))#(lf)"),<br>
>     df_sales1 = Source{[Name="df_sales"]}[Value],<br>
>     #"Changed Type" = Table.TransformColumnTypes(df_sales1,{{"Amount", Currency.Type}, {"Date first purchase", type date}, {"Birth Date", type date}, {"Sales", Int64.Type}, {"Quantity SKU", Int64.Type}})<br>
> in<br>
>     #"Changed Type"<br>

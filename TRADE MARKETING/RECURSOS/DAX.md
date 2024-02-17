<div align="center">
<table>
<thead>
<tr>
<th>Nombre</th>
<th>Expresión DAX</th>
</tr>
</thead>
<tbody>
<tr>
<td># COUNTRYS</td>
<td>DISTINCTCOUNT(marketing_data[Country])</td>
</tr>
<tr>
<td>% COMPLAINTS</td>
<td>CALCULATE( SUMX(marketing_data, marketing_data[Complain]), marketing_data[Complain] = 1 ) / COUNTROWS(marketing_data) * 1</td>
</tr>
<tr>
<td>AVG (AGE/INCOMES/RECENCY)</td>
<td>AVERAGE(marketing_data[Name])</td>
</tr>
<tr>
<td>purchasing channel</td>
<td>SUM(marketing_data[NumDealsPurchases]) + SUM(marketing_data[NumWebPurchases]) + SUM(marketing_data[NumCatalogPurchases]) + SUM(marketing_data[NumStorePurchases])</td>
</tr>
<tr>
<td>MultipleClientsCampaigns</td>
<td>CALCULATE( COUNTROWS(marketing_data), marketing_data[AcceptedCmp1] + marketing_data[AcceptedCmp2] + marketing_data[AcceptedCmp3] + marketing_data[AcceptedCmp4] + marketing_data[AcceptedCmp5] > 1 )</td>
</tr>
<tr>
<td>CMP RESPONSE</td>
<td>DIVIDE( SUM(marketing_data[Response]), COUNTROWS(marketing_data), 0 ) * 1</td>
</tr>
<tr>
<td>CMP[1,2,3,4,5]</td>
<td>DIVIDE( SUM(marketing_data[Name]), COUNTROWS(marketing_data), 0 ) * 1</td>
</tr>
<tr>
<td>WithResponseCampaigns</td>
<td>COUNTROWS( FILTER( marketing_data, (marketing_data[AcceptedCmp1] + marketing_data[AcceptedCmp2] + marketing_data[AcceptedCmp3] + marketing_data[AcceptedCmp4] + marketing_data[AcceptedCmp5] + marketing_data[Response]) = 1 ) )</td>
</tr>
<tr>
<td>DEALS PURCHASES</td>
<td>SUM(marketing_data[NumDealsPurchases])</td>
</tr>
<tr>
<td>TOTAL (FISH/FRUITS/GOLD/WINES/MEAT/SWEET)</td>
<td>SUM(marketing_data[Name])</td>
</tr>
<tr>
<td>INCOMES</td>
<td>SUM(marketing_data[MntWines]) + SUM(marketing_data[MntFruits]) + SUM(marketing_data[MntMeatProducts]) + SUM(marketing_data[MntFishProducts]) + SUM(marketing_data[MntSweetProducts]) + SUM(marketing_data[MntGoldProds])</td>
</tr>
<tr>
<td>LTV</td>
<td>DIVIDE( [INCOMES], COUNTROWS(marketing_data), 0 )</td>
</tr>
<tr>
<td>MEDIAN INCOMES</td>
<td>MEDIAN(marketing_data[ Income ])</td>
</tr>
<tr>
<td>No Teenagers / No Children</td>
<td>CALCULATE ( COUNTROWS(marketing_data), marketing_data[Name]=0 )</td>
</tr>
<tr>
<td>One Child / One Teenagers</td>
<td>CALCULATE ( COUNTROWS(marketing_data), marketing_data[Name] = 1 )</td>
</tr>
<tr>
<td>AverageExpenseTotal</td>
<td>VAR TotalWines = SUM(marketing_data[MntWines]) VAR TotalFruits = SUM(marketing_data[MntFruits]) VAR TotalMeat = SUM(marketing_data[MntMeatProducts]) VAR TotalFish = SUM(marketing_data[MntFishProducts]) VAR TotalSweets = SUM(marketing_data[MntSweetProducts]) VAR TotalGold = SUM(marketing_data[MntGoldProds]) VAR TotalGastos = TotalWines + TotalFruits + TotalMeat + TotalFish + TotalSweets + TotalGold VAR NumeroClientes = COUNTROWS(marketing_data) RETURN TotalGastos / NumeroClientes</td>
</tr>
<tr>
<td>Total customer</td>
<td>COUNTROWS(marketing_data)</td>
</tr>
<tr>
<td>Z CHILD =</td>
<td>SUMX(marketing_data,marketing_data[Kidhome])</td>
</tr>
<tr>
<td>Two Children/Two Teenagers</td>
<td>CALCULATE ( COUNTROWS(marketing_data), marketing_data[Name]=2 )</td>
</tr>
</tbody>

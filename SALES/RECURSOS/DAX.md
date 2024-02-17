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
<td># AVG VENTAS</td>
<td>AVERAGE(VENTAS[VENTAS])</td>
</tr>
<tr>
<td># TRATOS</td>
<td>COUNT(VENTAS[TAMAÑO_TRATOS])</td>
</tr>
<tr>
<td># VENTAS</td>
<td>SUM(VENTAS[VENTAS])</td>
</tr>
<tr>
<td># CANTIDAD</td>
<td>SUM(VENTAS[CANTIDAD PEDIDA])</td>
</tr>
<tr>
<td>AVG CANTIDAD</td>
<td>AVERAGE(VENTAS[CANTIDAD PEDIDA])</td>
</tr>
<tr>
<td>COLORES MAX-MIN</td>
<td>VAR VentasMax = MAXX(ALL(CalendarTable[Month Name],CalendarTable[Month]), [#Ventas]) VAR VentasMin = MINX(ALL(CalendarTable[Month Name],CalendarTable[Month]), [#Ventas]) RETURN SWITCH( TRUE(), [#Ventas] = VentasMin, "#FF5A52", [#Ventas] = VentasMax, "#53C22B", "" )</td>
</tr>
<tr>
<td>COLORES PAIS MAX - MIN</td>
<td>VAR VentasMaxP = MAXX(ALLEXCEPT(Lugar,Lugar[Pais_ID]), [#Ventas]) VAR VentasMinP = MINX(ALLEXCEPT(Lugar,Lugar[Pais_ID]), [#Ventas]) RETURN SWITCH( TRUE(), [#Ventas] = VentasMinP, "#FF5A52", [#Ventas] = VentasMaxP, "#fbae32", "#D9D9D9" )</td>
</tr>
<tr>
<td># VENTAS</td>
<td>= COUNTROWS(VENTAS)</td>
</tr>
<tr>
<td>COLORES PRODUCTO - MAX</td>
<td>VAR MaxVentasPorProducto = MAXX(ALLEXCEPT(Linea_Producto, Linea_Producto[LÍNEA DE PRODUCTO]), [#Ventas]) RETURN IF( MaxVentasPorProducto, "D9D9D9", BLANK()) // Aplica el color amarillo al valor máximo</td>
</tr>
<tr>
<td>Crecimiento Ventas YoY</td>
<td>[Ventas Año Actual] - CALCULATE ( [Ventas Año Actual], SAMEPERIODLASTYEAR('CalendarTable'[Date]) )</td>
</tr>
<tr>
<td>Porcentaje Crecimiento YoY</td>
<td>DIVIDE( [Crecimiento Ventas YoY], [Ventas Año Anterior], BLANK() )</td>
</tr>
<tr>
<td>Ventas Año Actual</td>
<td>SUM('VENTAS'[VENTAS])</td>
</tr>
<tr>
<td>Ventas Año Anterior</td>
<td>CALCULATE ( [Ventas Año Actual], SAMEPERIODLASTYEAR('CalendarTable'[Date]) )</td>
</tr>
</tbody>
</table>
</div>

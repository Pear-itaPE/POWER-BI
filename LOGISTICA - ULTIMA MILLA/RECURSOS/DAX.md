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
<td>% SERVICIO</td>
<td>[PESO ENTREGADO]/[PESO REQUERIDO]</td>
</tr>
<tr>
<td>COLORES KM/GL</td>
<td>VAR RendimientoMax = MAXX(ALL(CalendarTable[Day]), [RENDIMIENTO]) VAR RendimientoMin = MINX(ALL(CalendarTable[Day]), [RENDIMIENTO]) RETURN SWITCH( TRUE(), [RENDIMIENTO] = RendimientoMin, "#FF5A52", [RENDIMIENTO] = RendimientoMax, "#53C22B", "" )</td>
</tr>
<tr>
<td>CONSUMO</td>
<td>SUM(TRACKING[CONSUMO D2])</td>
</tr>
<tr>
<td>ENTREGAS EFECTUADAS</td>
<td>SUM(TRACKING[NRO ENTREGAS EFECTUADAS (Nro Guias)])</td>
</tr>
<tr>
<td>ENTREGAS RECHAZADAS</td>
<td>SUM(TRACKING[KM RECORRIDO (KM Inicial - KM Final)])</td>
</tr>
<tr>
<td>KM RECORRIDO</td>
<td>MAX(TRACKING[KM/GL])</td>
</tr>
<tr>
<td>MAX KM/GL</td>
<td>MIN(TRACKING[KM/GL])</td>
</tr>
<tr>
<td>MIN KM/GL</td>
<td>COUNTROWS(TRACKING)</td>
</tr>
<tr>
<td>PEDIDOS</td>
<td>SUM(TRACKING[PESO ENTREGADO])</td>
</tr>
<tr>
<td>PESO ENTREGADO</td>
<td>SUM(TRACKING[PESO REQUERIDO])</td>
</tr>
<tr>
<td>PESO REQUERIDO</td>
<td>[KM RECORRIDO]/[CONSUMO]</td>
</tr>
<tr>
<td>RENDIMIENTO</td>
<td>[PESO ENTREGADO]/[PESO REQUERIDO]</td>
</tr>
</tbody>
</table>
</div>

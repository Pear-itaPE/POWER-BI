![image](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/assets/143855758/ebc35e7b-9975-40f1-84e3-3f87fd673ef1)![image](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/assets/143855758/9e78aee3-a246-4177-a041-b757654cc336)## ANALISIS DE VENTAS 💰
Entorno: POWER BI

Versión: 2.124.2028.0 64-bit (diciembre de 2023)


[![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)

## DESCRIPCIÒN📝

Este dashboard proporciona un análisis detallado de las ventas a lo largo de varios años, destacando información sobre el rendimiento de ventas por categoría de producto, tamaño de la empresa y temporadas del año. Utiliza visualizaciones avanzadas para mostrar la evolución de las ventas y los patrones de pedidos promedio, ofreciendo una vista clara del rendimiento de ventas a lo largo del tiempo.

## OBJETIVO ✅

El objetivo principal es ofrecer una visión clara del desempeño de ventas de la empresa, permitiendo a los analistas y gerentes de ventas identificar tendencias, evaluar la efectividad de diferentes estrategias de venta y tomar decisiones informadas basadas en datos históricos y actuales.

## PREGUNTAS DE NEGOCIO💡

💳 ¿Cómo han evolucionado las ventas totales a lo largo de los años y por trimestres?
💳 ¿Cuál ha sido el valor promedio de los pedidos en cada año?
💳 ¿Cómo difieren las ventas entre empresas de diferentes tamaños (medianas, pequeñas, grandes)?
💳 ¿Hay patrones estacionales o mensuales en las ventas?

## Resultados 

🪙Estados Unidos lidera con $1.216 millones en ventas.

📢Le siguen España, Francia, Australia y el Reino Unido, con ventas que varían desde $631 millones hasta $246 millones.
Esta distribución muestra la importancia de la diversificación del mercado y la necesidad de estrategias de marketing localizadas.
Ventas por Producto:

🪙Los Coches Clásicos son la categoría más vendida, alcanzando los $1.903 millones.

📢Los Coches Vintage y las Motocicletas también muestran ventas fuertes, con $1.166 millones y $1.128 millones respectivamente.
Este resultado destaca las categorías de productos más populares y puede informar el desarrollo de inventario y promociones.
Ventas por Estado de Pedido:

🪙Las ventas de pedidos enviados dominan claramente con $2.292 millones.

📢Los pedidos cancelados y en espera representan $194 millones y $179 millones respectivamente.
Estos datos son cruciales para la gestión de operaciones y la mejora de la eficiencia del proceso de ventas.
Ventas por Tamaño del Trato:

🪙Los tratos de tamaño medio representan la mayoría de las ventas con $6.087 millones, seguidos por los tratos pequeños y grandes.

📢Este insight es fundamental para entender el comportamiento del cliente y ajustar las estrategias de ventas y negociación.
Cada uno de estos aspectos proporciona un ángulo único sobre el rendimiento de las ventas, y juntos ofrecen una visión comprensiva que puede ayudar a formular estrategias de negocio efectivas. 

Estos resultados destacan la importancia de analizar las ventas desde múltiples dimensiones para obtener una imagen completa del rendimiento de la empresa.

## MODELO DE DATOS
<p align="center">
  <img src="https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/blob/main/SALES/RECURSOS/MODELO%20DE%20DATOS.png" alt="MODELO DE DATOS">
</p>

## FORMULAS DAX

| Nombre                | Expresión DAX                                                                                                        <div align="center">
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


## DASHBOARD 📶
Para explorar el dashboard interactivo de Ventas, visita [SALES POWER BI](https://app.powerbi.com/view?r=eyJrIjoiNDdkMjUyMjktNTE2ZC00ZmE2LTgyMDQtMDZiNTM4MmQ2ZTRhIiwidCI6Ijc4ODEzZTVjLWRmODYtNGZhYy04NWI0LTYwOGM0MjZlZmY2NiIsImMiOjR9).

![SALES](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/blob/main/SALES/RECURSOS/SALES.png)



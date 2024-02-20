## ANÁLISIS LOGÍSTICA - ÚLTIMA MILLA 🚚 
Entorno: POWER BI

Versión: 2.124.2028.0 64-bit (diciembre de 2023)


[![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)

## DESCRIPCIÒN📝

El dashboard está diseñado para realizar un seguimiento exhaustivo y análisis de la eficiencia logística, específicamente en el consumo de combustible y la distribución de pedidos. Emplea una serie de visualizaciones de datos para monitorear métricas operacionales críticas como kilómetros por galón, número de entregas, y cumplimiento de pedidos. Los datos son filtrados por unidad vehicular, lo que permite una evaluación precisa del desempeño de cada activo móvil dentro de la flota. El uso de indicadores de rendimiento mínimo y máximo en el gráfico de líneas proporciona una referencia inmediata para identificar variaciones significativas en el consumo de combustible que puedan requerir acción correctiva.


## OBJETIVO ✅

El objetivo del dashboard es maximizar la eficiencia operacional y la efectividad en la gestión de la cadena de suministro. Busca identificar oportunidades de ahorro de costos, optimizar la asignación de recursos, y mejorar el nivel de servicio a través del análisis detallado de datos de rendimiento de la flota. Además, pretende apoyar la toma de decisiones estratégicas mediante la identificación de patrones y tendencias en el comportamiento operativo de las unidades de reparto.


## PREGUNTAS DE NEGOCIO💡

🚍 ¿Cómo podemos optimizar las rutas y la planificación de las entregas para mejorar la eficiencia del combustible y reducir costos operativos?

🚍 ¿Cómo se está desempeñando la flota en términos de cumplimiento de entregas y cómo se puede mejorar el porcentaje de nivel de servicio?

🚍 ¿Qué relación hay entre los kilómetros recorridos y el combustible consumido y cómo podemos utilizar esta información para mejorar el mantenimiento y la eficiencia de los vehículos?

🚍 ¿Estamos maximizando la capacidad de carga de los vehículos y cómo afecta esto a la eficiencia general de la flota?

🚍 ¿En qué áreas geográficas estamos viendo un mayor número de pedidos y cómo podemos ajustar nuestra logística para atender mejor estas demandas?

🚍¿Cómo podemos mejorar la planificación de recursos basándonos en las tendencias de los pedidos y la eficiencia del reparto?


## Resultados 

🚘Consumo de Combustible: Rendimiento variando entre 316 km/gln y 4186 km/gln, destacando la eficiencia energética.

🚘Kilometraje Total: 20,403 km recorridos, un indicador de la extensión de las operaciones logísticas.

🚘Kilómetros por Galón (KM/GLN): Promedio de 1,971 KM/GLN, reflejando la eficiencia en el consumo de combustible.

🚘Total de Órdenes Entregadas: 268 órdenes, representando la capacidad operativa de la flota.

🚘Fuel-to-Run (FTR): Total de 1,035.31, una medida del combustible utilizado frente a las distancias recorridas.

🚘Peso Requerido vs. Peso Entregado: Mantenimiento de un alto nivel de servicio con un promedio del 96.43%, lo que indica la precisión en la entrega de pedidos.

🚘La unidad analizada muestra una alta variabilidad en la eficiencia del combustible, señalando posibles áreas para la optimización de rutas o mantenimiento de vehículos.

🚘El cumplimiento de peso entregado frente al peso requerido se mantiene en un porcentaje excepcionalmente alto, evidenciando una operación logística robusta y confiable.

## RECOMENDACIONES 🚀

📚 La variabilidad en la eficiencia del combustible indica oportunidades para optimizar las rutas. El rango entre el mínimo y máximo de kilómetros por galón sugiere que hay margen para mejorar la eficiencia a través de mejor planificación de ruta o mantenimiento de vehículos.

📚 Con un porcentaje de servicio promedio del 96.43%, el cumplimiento de entregas es alto. Sin embargo, hay margen de mejora, especialmente en casos donde el porcentaje de servicio cae por debajo del promedio.

📚 El promedio de kilómetros por galón proporciona una base para analizar el rendimiento del vehículo y posiblemente ajustar los horarios de mantenimiento para mantener la eficiencia del combustible.

 📚La diferencia entre el peso requerido y el peso entregado es mínima, indicando que la optimización de carga es efectiva. No obstante, se debe continuar monitoreando para mantener y mejorar la precisión en la carga.

 📚Podría usarse analisis predictivo para identificar tendencias en la demanda por ubicación y ajustar la logística de distribución en consecuencia.

 📚Basándose en el volumen de pedidos y la eficiencia del reparto, la planificación de recursos puede mejorarse al asignar más vehículos y conductores a las rutas con mayor demanda o al reajustar las rutas para mejorar la eficiencia.
 
## MODELO DE DATOS
Formulas DAX textuales [aquí](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/blob/main/LOGISTICA%20-%20ULTIMA%20MILLA/RECURSOS/DAX.md)

 <p align="center">
  <img src="https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/raw/main/LOGISTICA%20-%20ULTIMA%20MILLA/RECURSOS/845294b1-45c0-4114-9093-94434d30ba1b.png" alt="MODELO DE DATOS">
</p>

## FORMULAS DAX

Formulas DAX textuales [aquí](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/blob/main/LOGISTICA%20-%20ULTIMA%20MILLA/RECURSOS/DAX.md)

![image](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/raw/main/LOGISTICA%20-%20ULTIMA%20MILLA/RECURSOS/845294b1-45c0-4114-9093-94434d30
Nombre	Expresión DAX
	
% SERVICIO 	[PESO ENTREGADO]/[PESO REQUERIDO]
	
COLORES KM/GL 	VAR RendimientoMax = MAXX(ALL(CalendarTable[Day],CalendarTable[Day]), [RENDIMIENTO])
	VAR RendimientoMin = MINX(ALL(CalendarTable[Day],CalendarTable[Day]), [RENDIMIENTO])
	RETURN
	    SWITCH(
	        TRUE(),
	        [RENDIMIENTO] = RendimientoMin, "#FF5A52",  // Rojo para el valor mínimo de rendimiento
	        [RENDIMIENTO] = RendimientoMax, "#53C22B",  // Marrón para el valor máximo de rendimiento
	        ""  // Amarillo para todos los demás valores
	    )
	
CONSUMO  	SUM(TRACKING[CONSUMO D2])
	
ENTREGAS EFECTUADAS  	SUM(TRACKING[NRO ENTREGAS EFECTUADAS (Nro Guias)])
	
ENTREGAS RECHAZADAS  
	
KM RECORRIDO 	SUM(TRACKING[KM RECORRIDO (KM Inicial - KM Final)])
	
MAX KM/GL 	MAX(TRACKING[KM/GL])
	
MIN KM/GL 	MIN(TRACKING[KM/GL])
	
PEDIDOS 	COUNTROWS(TRACKING)
	
PESO ENTREGADO 	SUM(TRACKING[PESO ENTREGADO])
	
PESO REQUERIDO 	 SUM(TRACKING[PESO REQUERIDO])
	
RENDIMIENTO 	[KM RECORRIDO]/[CONSUMO]
![image](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/assets/143855758/86386083-a3c6-433c-a334-f349b585361c)

	
## DASHBOARD 📶
Para explorar el dashboard interactivo de Ultima Milla, visita [TRACKING ULTIMA MILLA ](https://app.powerbi.com/view?r=eyJrIjoiNDM0NWMzMDQtNDM1Yy00ZGViLTk5MWYtNTQxZjc1NDczODUyIiwidCI6Ijc4ODEzZTVjLWRmODYtNGZhYy04NWI0LTYwOGM0MjZlZmY2NiIsImMiOjR9).

![SALES](https://github.com/Pear-itaPE/PORTFOLIO-POWER-BI/blob/main/LOGISTICA%20-%20ULTIMA%20MILLA/RECURSOS/DASHBOARD.png)

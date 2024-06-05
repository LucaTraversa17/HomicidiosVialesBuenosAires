# Homicidios Viales Buenos Aires
### Introducción
El presente trabajo se enfoca en analizar el [dataset](https://docs.google.com/spreadsheets/d/1nq00jGIZHQ1RLSET43zKnUsMsoFb-pBg/edit#gid=1625530738) de los homicidios viales en la ciudad de Buenos Aires. El mismo cuenta con la información de los homicidios viales registrados en la capital de la República Argentina entre 2016 y 2021. En la carpeta Datasets del repositorio encontrarán los Datasets utilizados como insumos del dashboard de PowerBI. En el archivo EDA podrán observar como se fueron armando esos datasets y para qué fin serán utilizados. 

El objetivo del presente análisis es desglosar la información del Dataset para poder observar las distintas variables que lo integran y diagramar un plan de trabajo que tenga como objetivo la reducción de los accidentes viales fatales en la ciudad de Buenos Aires. Hay que tener en cuenta que en el contexto de una ciudad como Buenos Aires, los siniestros viales pueden ser una preocupación importante debido al alto volumen de tráfico y la densidad poblacional. Estos incidentes pueden tener un impacto significativo en la seguridad de los residentes y visitantes de la ciudad, así como en la infraestructura vial y los servicios de emergencia.

Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Estas tasas se calculan, generalmente, como el número de muertes por cada cierto número de habitantes o por cada cierta cantidad de vehículos registrados. Reducir estas tasas es un objetivo clave para mejorar la seguridad vial y proteger la vida de las personas en la ciudad.

### EDA del Dataset
Como primer paso para el análisis, llevamos a cabo un estudio preeliminar del Dataset con la ayuda de la librería ydata_profiling. Dicho análisis se encuentra en el archivo del repositorio llamado "EDA.ipynb". Lo que primero pudimos observar es que el dataset está muy completo, sin filas duplicadas y con unas pocas columnas con algunas filas con valores nulos. 

#### Conclusiones preeliminares:

En base a todo el análisis llevado a cabo hemos observado los siguientes datos de forma preeliminar: 
1. La distribución de víctimas presenta la siguiente concentración:
    * La gran mayoría son hombres y la categoría de la víctima se centra en motociclista o peatones. Y los hechos ocurren principalmente en calles o avenidas. 
    * Si agrupamos por edad observamos que la mayoría de las víctimas se encuentran entre los 20 y los 45 años. 
2. La distribución temporal de los hechos tiene una leve concentración en los horarios 6 y 7 de la mañana. Sin embargo no encontramos ningún tipo de distribución anormal en cuanto a los días de la semana. Hay una leve concentración de hechos en diciembre por sobre los demás meses. 
3. Los acusados de los hechos se concentran principalmente en tres categorías: Auto, Pasajeros y Vehículos de Carga.

### Análisis con PowerBI

Luego del EDA preeliminar, hemos exportado los datasets emprolijados para poder ser analizados en más detalle con PowerBI. Esta poderosa herramienta nos permitió cruzar variables de manera más rápida, intuitiva y visual para poder sacar conclusiones un poco más profundas que las llevadas a cabo previamente. En el repositorio encontrarán el dashboard bajo el nombre Proyecto.pbix 

#### Conclusiones del Dashboard:
En base a todo el análisis llevado a cabo hemos observado la siguiente información: 
1. Las víctimas jóvenes (edad entre 17 y 35 años) pertenecen principalmente a la categoría de motos (un 65%) y el 84% de esos jóvenes son hombres.
2. Contrariamente, las víctimas mujeres son principalmente peatones (62%) de edad avanzada (50 a 70 años).
3. El horario con más accidentes fatales para las motos se ubica entre las 5 y las 8 de la mañana.
4. En cambio para los peatones la hora más "segura" es la madrugada y el número de accidentes fatales se concentra entre las 9hs de la mañana y las 22hs.
5. Las categorías de acusado que tiene más relación con los accidentes mortales de las motos son los autos 28% y los vehículos de carga con el 26%.
6. Las categorías de acusado que tiene más relación con los accidentes mortales de los peatones son los vehículos de pasajeros con el  40% y los autos con el 30%.
7. En cuanto a la distribución espacial de los accidentes observamos que la comuna 1, integrada por los barrios de Retiro, San Nicolás, Puerto Madero, San Telmo, Monserrat y Constitución, es donde ocurren la mayor cantidad de accidentes. Esto no es ninguna sorpresa ya que corresponde a la comuna con más tráfico al ser el corazón turístico, laboral y financiero de la ciudad.

Creemos que estos análisis son vitales para focalizar las posibles políticas públicas a llevar a cabo para reducir la tasa de homicidios viales. La eficiencia y la efectividad de las mismas estarán directamente relacionadas con la utilidad e implicancia que se le brinde a la información que nos otorgan los hechos observados en el pasado. 

### KPIs
Se nos ha propuesto la creación de tres KPIs para monitorear la evolución de los siniestros viales en determinado intervalo de tiempo y según distintas variables como veremos a continuación. La idea de los mismos es poder implementar mejoras o cambios en las políticas de la ciudad que puedan mejorar estos indicadores a lo largo del tiempo y así construir una ciudad más segura. Es importante destacar que la prevención de siniestros viales involucra medidas como la educación vial, el cumplimiento de las normas de tráfico, la infraestructura segura de carreteras y calles, así como la promoción de vehículos más seguros. El seguimiento de las estadísticas y la implementación de políticas efectivas son esenciales para abordar este problema de manera adecuada.

#### KPI N°1: Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

Definimos a la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

En la siguiente imagen podemos observar la evolución en % respecto al año anterior. Para mayor información sugerimos consultar el dashboard. 

![image](https://github.com/LucaTraversa17/HomicidiosVialesBuenosAires/assets/88990751/35322779-26ff-463d-bc66-5d2e84f3f970)


#### KPI N°2: Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año respecto al año anterior.

Definimos a la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

En la siguiente imagen podemos observar la evolución en % respecto al año anterior. Para mayor información sugerimos consultar el dashboard. 

![image](https://github.com/LucaTraversa17/HomicidiosVialesBuenosAires/assets/88990751/b7f88ea3-fd1b-401a-999f-55abdc37d94f)


#### KPI N°3: Reducir en un 10% la cantidad de accidentes mortales producidos por vehículos de carga o pasajeros en el último año respecto al año anterior.

Definimos la cantidad de accidentes mortales producidos por vehículos de carga o pasajeros como el número absoluto de accidentes fatales en los que el acusado, sin que implique responsabilidad o culpabilidad, fue un vehículo de carga o pasajeos. Su fórmula para medir la evolución es: (Número de accidentes mortales con acusados vehículo de carga o pasajeros en el año anterior - Número de accidentes mortales con acusados vehículo de carga o pasajeros en el año actual) / (Número de accidentes mortales con acusados vehículo de carga o pasajeros en el año anterior) * 100

En la siguiente imagen podemos observar la evolución en % respecto al año anterior. Para mayor información sugerimos consultar el dashboard. 

![image](https://github.com/LucaTraversa17/HomicidiosVialesBuenosAires/assets/88990751/e0649a7c-45c8-4a0e-ab32-0cf9b08f0c3a)


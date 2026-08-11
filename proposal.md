# TPI-Soporte-2026-G14

El siguiente proyecto consta del desarrollo de un negocio la cual permite visualizar y/o comparar diversas metricas historicas o actuales (según el tipo de comparación) de un o varios barrios privados. 
Estas son las posibles situaciones en las cuales se puede obtener las métricas historicas (si o si se debe elegir un periodo):
- Ver la situación de cierto barrio privado en una fecha previa al dia de hoy
- Comparación de un solo barrio privado, pero en distintos momentos (se selecciona un periodo)
- Comparación entre dos barrios privados, donde uno pertenece a un momento diferente al otro

En cambio, las métricas actuales se obtienen a partir de:
- Seleccionar un barrio privado y obtener sus datos del día de hoy
- Comparación entre dos o más barrios según sus métricas actuales 

Las metricas historicas son: 

- Tasa de crecimiento entre las fechas elegidas
- Número de aumento de casas
- Aumento del porcentaje de terreno utilizado
- Disminución del porcentaje de terreno disponible

Las métricas actuales son

- Cantidad de casas construidas
- Porcentaje de terreno construido (metros cuadrados construido sobre totales)
- Distancia promedio relativa entre cada casa
- Nivel de acumulación de casas 
- Metros cuadrados disponibles

Para lograr la obtención de estas métricas, la aplcación va a utilizar la API de Google Earth para obtener las imagenes con una vista superior de los barrios privados. Posteriormente, se van a analizar estas imagenes para obtener para obtener las métricas, las cuales se van a mostrar en una página web. Está pagina web ofrece las diferentes interacciones posbiles para realizar comparaciónes u obtener datos actuales, además de un dashboard que demuestra estádisticas del uso de la aplicación y botones para atajo de acciones.

Existe la posibilidad de guardar las métricas de cierta fecha de los barrios privados en una base de datos, para su posterior recuperación sin la necesidad de volver a hacer calculos. El beneficio de esto es evitar el calculo excesivo de datos repetitivos, sumandole el historial de barrios revisados de los mismos en el dashboard.

Para lograr estos requerimientos se van a utilizar las siguientes tecnologías:

- Python
- OpenCV
- Flask 
- Google Earth
- SQL Server
- SQLAlchemy

// OpenCV







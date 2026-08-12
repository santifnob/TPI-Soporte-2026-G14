# TPI-Soporte-2026-G14

----------------------

## Descripción del proyecto

El siguiente proyecto consta del desarrollo de una aplicación que permite visualizar y/o comparar diversas metricas de uno o varios barrios privados. 

Las métricas actuales/historicas de un barrio privado se obtienen a partir de:
- Seleccionar un barrio privado y obtener sus datos del día de hoy
- Ver la situación de cierto barrio privado en una fecha previa al dia de hoy

Las métricas actuales/historicas son las siguientes:

- Cantidad de casas construidas
- Porcentaje de terreno construido (metros cuadrados construido sobre totales)
- Distancia promedio relativa entre cada casa
- Nivel de acumulación de casas 
- Metros cuadrados disponibles

Una vez obtenidas estás metricas, se le da la posibilidad de compararlas con las métricas de otros barrios privados una a una. Además es posible obtener un ranking de los barrios privados según la métrica seleccionada, y evaluar el progreso de uno sobre otra.

Las metricas resultantes de comparaciones con un mismo barrio privado, pero en distintas fechas: 

- Tasa de crecimiento entre las fechas elegidas
- Número de aumento de casas
- Aumento del porcentaje de terreno utilizado
- Disminución del porcentaje de terreno disponible

---------------------- 

## Aplicación funcional

Para la obtención de estas métricas, la aplcación va a utilizar la **API de Google Earth** para obtener las imagenes con una vista superior de los barrios privados. Posteriormente, se van a analizar estas imagenes para obtener para obtener las métricas, las cuales se van a mostrar en una **página web**. Está pagina web ofrece las diferentes interacciones posibles para realizar comparaciónes u obtener datos actuales, además de un **dashboard** que demuestra estádisticas del uso de la aplicación y botones para atajo de acciones, como el de comparar métricas entre barrios.

Existe la posibilidad de guardar los barrios privados juntos con sus métricas calculadas de cierta fecha en una **base de datos**, para su posterior recuperación sin la necesidad de volver a realizar calculos. El beneficio de esto es evitar el calculo excesivo de datos repetitivos, sumandole el historial de barrios revisados de los mismos en el dashboard.

----------------------

## Tecnologías utilizadas

Para lograr estos requerimientos se van a utilizar las siguientes tecnologías:

- **Lenguaje Python**
- **OpenCV**: permite la detección y conteo de las casas, junto con otros parámetros como la distiancia entre ellas, a partir de la imagén obtenida con Google Earth
- **Flask**: permite la creación de la web API y la redirección de la página web
- **Google Earth**: aplicación externa que permite obtener imágenes satelitales de los barrios privados mediante archivos KMZ
- **MySQL**: base de datos relacional que permite almacenar los barrios privados junto con sus métricas historicas y actuales
- **HTML, CSS y JavaScript**: permiten la creación de la página web y el dashboard, además de la interacción con la web API
- **SQLAlchemy**: permite la interacción con la base de datos MySQL desde Python utilizando objetos y clases, evitando el uso de tablas

--------------
## Modelo relacional de la base de datos

Se propone el siguiente modelo relacional para la base de datos, el cual permite almacenar los barrios privados junto con sus métricas historicas y actuales:
- Tabla `barrios_privados`: almacena los barrios privados junto con su id, nombre, ubicación (KMZ)? y fecha de guardado.
- Tabla `metricas_historicas`: depende de `barrios_privados`. Almacena el id del barrio privado, las métricas calculadas de la fecha seleccionada, y dicha fecha de obtención. Se considera métrica actual aquella que tenga la fecha de obtención más reciente.
- Tabla `metricas_comparativas`: depende de `barrios_privados`. Almacena el id del barrio privado, las métricas comparativas calculadas del periodo elegido, fecha de inicio y fecha fin del perido.

---------
## Requerimientos funcionales

- El sistema debe permitir al usuario ingresar el KMZ de un barrio privado, ingresar una fecha y calcular las métricas correspondientes.
- El sistema debe permitir al usuario seleccionar dos barrios privados distintos para comparar sus métricas actuales y/o historicas, mostrando visualmente dinamicas de cambio.
- El sistema debe permitir al usuario visualizar un ranking de los barrios privados según la métrica seleccionada.
- El sistema debe permitir al usuario evaluar el progreso de un barrio privado sobre otro en términos de las métricas calculadas.
- El sistema debe permitir al usuario elegir un peridodo de tiempo para calcular las métricas de desarrollo de un mismo barrio privado en distintas fechas.
- El sistema debe guardar los barrios privados junto con sus métricas calculadas en la base de datos para su posterior recuperación.
- El sistema debe mostrar al usuario un dashboard con estadísticas del uso de la aplicación y botones de atajo para acciones frecuentes, como comparar métricas entre barrios privados.






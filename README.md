# Objetivo

Mi trabajo de Análisis exploratorio de datos se centra en el análisis de los festivales de música que se celebran en España a lo largo de 2023.

## Hipótesis que se plantean

Quiero analizar todos los festivales que se celebran en nuestro país. Las hipótesis que se plantean son:

1. Determinar qué estilos de música son los más programados en los festivales.
2. Identificar los grupos que más actuarán en los festivales.
3. Analizar en qué período del año se programan más festivales.
4. Investigar si hay una concentración de festivales en ciertas provincias o comunidades autónomas, o si sigue una regla en la que las ciudades más grandes tienen más festivales.

Estas preguntas pueden llevar a plantear otras cuestiones interesantes a medida que se avance en el análisis.

## Exploración de las fuentes de datos

### Datos musicales

Primeramente, he realizado una búsqueda en Internet para encontrar fuentes de información sobre los festivales de música en España. Las principales fuentes encontradas son:

- [https://www.dodmagazine.es/festivales/](https://www.dodmagazine.es/festivales/): Esta web proporciona información limitada en el listado de festivales, pero al acceder a la URL de cada festival, la estructura del código HTML varía, lo que dificulta la extracción y limpieza de la información.

- [https://fanmusicfest.com/calendario-festivales](https://fanmusicfest.com/calendario-festivales): Esta web proporciona más información que la anterior. Cuenta con una serie de filtros que permiten clasificar cada festival por estilo de música. La estructura del código HTML de cada festival es más clara, y además, se dispone de un archivo GeoJSON con información adicional.

### Datos demográficos

Para complementar la información de los festivales, se desea obtener datos demográficos, específicamente el número de habitantes de cada localidad donde se celebra un festival. La información demográfica se obtendrá del INE (Instituto Nacional de Estadística) a través de las siguientes fuentes:

- [https://www.ine.es/ss/Satellite?L=es_ES&c=Page&cid=1259952026632&p=1259952026632&pagename=ProductosYServicios%2FPYSLayout](https://www.ine.es/ss/Satellite?L=es_ES&c=Page&cid=1259952026632&p=1259952026632&pagename=ProductosYServicios%2FPYSLayout): Se obtiene un archivo CSV con los municipios y sus respectivos códigos postales y códigos de municipio.

- [https://www.ine.es/dynt3/inebase/es/index.htm?padre=525](https://www.ine.es/dynt3/inebase/es/index.htm?padre=525): Se obtiene un archivo XLS con los municipios, los códigos de municipio y la población en el último censo (2022).

### Datos económicos

Además del análisis de los festivales, se desea analizar el impacto económico en el sector de la organización de eventos musicales. Se encontró una Asociación de Promotores Musicales que publica anualmente un Anuario con información económica del sector. Los datos de facturación neta de la asociación están agrupados por meses, provincias, comunidades autónomas, entre otros.

## Extracción / Tratamiento de los datos

### Datos musicales

Para la extracción de información de las fuentes mencionadas, se utilizó la técnica de web scraping con Beautiful Soup. Se extrajo información musical (nombre del festival, artistas, estilos) y datos de localización (latitud, longitud, provincia, localidad, lugar de los conciertos, fechas de inicio y finalización). La información se estructuró en un dataframe utilizando la librería Pandas de Python.

### Datos demográficos

Antes de poder relacionar los datos demográficos del INE.es con los festivales, fue necesario unir las tablas utilizando el código de municipio como clave de relación.

### Datos económicos

Los datos económicos no estaban disponibles en un archivo, sino en formato PDF. Para extraer los datos, se utilizó la librería de reconocimiento óptico de caracteres (OCR) llamada pytesseract.

## Representación de los datos

Se utilizaron las siguientes herramientas y librerías para representar los datos:

- **Plotly**: Se utilizó la librería Plotly Express para generar gráficos de barras, gráficos circulares y gráficos de líneas.

- **Wordcloud**: Se crearon nubes de palabras para representar gráficamente las diferentes variables de análisis en cada uno de los bloques (datos musicales, económicos y demográficos) utilizando la librería Wordcloud.

- **Folium**: Se utilizó Folium para generar un mapa de España que muestra la ubicación de cada festival agrupado por estilos de música.

## Principales dificultades

Las principales dificultades encontradas durante el análisis exploratorio de datos fueron:

- El proceso de web scraping, ya que la estructura de las diferentes URLs no era consistente, lo que requirió ajustes en el código para asegurar la extracción completa de los datos y evitar valores vacíos en el dataframe.

- El tratamiento de los datos demográficos obtenidos del INE.es, que requirió un esfuerzo adicional para hacer coincidir los datos mediante el código de municipio y luego combinarlos con los códigos postales de los registros de los festivales.

- El proceso de reconocimiento de caracteres en imágenes OCR, que presentó dificultades cuando algunas imágenes no eran claras y las cifras no se reconocían correctamente. Fue necesario verificar visualmente algunos datos en tablas para asegurar su precisión.

## Documentación

Se adjunta la documentación de los anuarios de la Asociación de Promotores Musicales de los años 2014, 2021 y 2023.



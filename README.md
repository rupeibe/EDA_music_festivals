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

Además del análisis de los festivales, se desea analizar el impacto económico en el sector de la organización de eventos musicales. Se



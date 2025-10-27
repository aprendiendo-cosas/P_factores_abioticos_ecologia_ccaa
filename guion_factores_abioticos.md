

# Uso de información de [GBIF](https://www.gbif.org/) para generar mapas de área de distribución de especies en Sierra Nevada

> + **_Tipo de material_**: <span style="display: inline-block; font-size: 12px; color: white; background-color: #4caf50; border-radius: 5px; padding: 5px; font-weight: bold;"> Prácticas</span> 
> + **_Versión_**: 2025-2026
> + **_Asignatura (grado)_**: Ecología (CCAA)
> + **_Autor_**: Curro Bonet-García (fjbonet@uco.es)
> + **_Duración_**: Lo que haya durado esta sesión en la asignatura de SIG más una hora en casa 

![portada](https://raw.githubusercontent.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/refs/heads/main/imagenes/portada.png)



## Objetivos

- Disciplinares para la asignatura de ecología:
  - Comprender en qué medida las condiciones abióticas (altitud, clima, orientación, etc.) condicionan la estructura y funcionamiento de los ecosistemas.
  - Comparar la estructura de los ecosistemas estudiados con las condiciones ambientales que imperan en las zonas en las que están presentes.
  - Entender cómo el cambio en las condiciones climáticas puede afectar a la estructura, composición y funcionamiento de los ecosistemas de Sierra Nevada. 
  
- Competenciales: Relacionados con la adquisición de competencias genéricas (SIG y R en este caso):
  - Practicar las funciones de SIG que permiten extrar datos de capas raster y asociar estadísticas de las mismas a capas poligonales.


Los objetivos de aprendizaje anteriores se materializan en el siguiente objetivo operativo. Es decir, tienes que hacer esto:

> Generar una tabla en la que a cada ecosistema de Sierra Nevada se le asignen valores promedio de: precipitación actual, temperatura actual, precipitación prevista en el futuro, temperatura prevista en el futuro y altitud. Esta tabla puede servirte para:
>
> + Conocer con detalle las condiciones climáticas que hay en los lugares en los que vive tu ecosistema.
> + Conocer cómo cambiarán esas condiciones climáticas.
> + Comparar tanto las condiciones climáticas del presente como las del futuro en los distintos tipos de ecosistema. Contextualizar las de tu ecosistema. ¿hace más o menos frío en mi ecosistema que en los demás?, ¿cómo de variables son las condiciones ambientales en mi ecosistema?, ¿cambia el clima más intensamente en mi ecosistema que en otros?
>
> Además, también se puede generar un mapa de las condiciones abióticas solo en los polígonos de tu ecosistema. Esto nos ayudará a entender cómo cambian las condiciones ambientales en las distintas localidades donde vive el ecosistema en cuestión.



## Contextualización ecológica: influencia del contexto abiótico en los ecosistemas

Las condiciones ambientales condicionan (valga la redundancia) las características de los ecosistemas. La disponibilidad de agua, nutrientes y la temperatura del medio permiten en diferentes grados la ocupación del espacio por seres vivos y por tanto por ecosistemas. Es obvio constatar esto. Por ejemplo, sabemos que para que en un lugar crezcan árboles enormes es necesario que haya un clima benigno y abundantes precipitaciones.

Una montaña es un buen sitio en el que observar cómo el cambio en las condiciones abióticas modifica la capacidad del territorio de albergar diferentes formas de vida. A lo largo de nuestro recorrido por Sierra Nevada veremos cómo en los distintos climas, tipos de suelo y orientaciones hay distintos tipos de ecosistemas.

Así, conocer las características abióticas del territorio es muy importante para entender la estructura y funcionamiento de los ecosistemas. Además, si esas condiciones cambian (como lo está haciendo el clima), podemos inferir de alguna forma la trayectoria de cambio que experimentarán los ecosistemas.

Las condiciones ambientales no actúan de la misma forma sobre los ecosistemas. Normalmente lo que suele ocurrir es que el sistema en su conjunto funciona al ritmo al que le permite la variable ambiental que está presente con menos intensidad en el territorio. Esto se estudia en la denominada [ley del mínimo de Liebig.](https://es.wikipedia.org/wiki/Ley_del_m%C3%ADnimo_de_Liebig) El siguiente dibujo ilustra muy bien esta idea



![liebig](https://raw.githubusercontent.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/refs/heads/main/imagenes/liebig.png)

El tonel de la figura almacenará tanta agua como lo permita la balda más corta. Siguiendo la analogía, un ecosistema funcionará al ritmo que le permita el condicionante abiótico que sea más limitante.

En nuestra zona de estudio los limitantes varían en función de la altura. Con este ejercicio tendrás que identificar el contexto abiótico de cada ecosistema y también interpretar qué variable ambiental puede estar limitando en cada caso. Además, debes tener en cuenta que las condiciones climáticas están cambiando. Es decir, el tamaño de las duelas del tonel están cambiando de tamaño.



## Flujo de trabajo

A continuación se describen los pasos que hay que dar para generar mapas de distribución de las especies de interés. Describiré con menos detalle las cuestiones que ya habéis visto en la asignatura de SIG. Todo lo descrito aquí se puede hacer también con R.

### 1. Descargar los datos que necesitamos 

+ **1.1** [Aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/precip_media_actual.tif) tienes una capa mostrando el promedio de la precipitación total en cada píxel de Sierra Nevada en unas condiciones climáticas históricas. Esta información procede de [este](https://figshare.com/articles/dataset/Spatial_distribution_of_annual_and_seasonal_precipitation_mm_in_Sierra_Nevada_and_surroundings_with_the_accumulated_means_resulting_from_interpolation_raster_format_/14208392/2) producto generado por el [Observatorio de seguimiento del cambio global en Sierra Nevada](https://obsnev.es/).  
+ **1.2.** [Aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/precip_media_70_00.tif) puedes descargar una capa que contiene datos del promedio de la precipitación total prevista para Sierra Nevada en la década de 2070 a 2100. Esta información se ha generado a partir de [este](https://portalrediam.cica.es/descargas/index.php/s/mxHMWXyHfrCxyNK?dir=/04_RECURSOS_NATURALES/03_CLIMA/03_CAMBIO_CLIMATICO/03_PRECIPITACION/06_TREINTENA/ESC_PRECIP_MEDIAS_TREINTENA_2000_2100/InfGeografica/InfRaster/TIFF) proyecto de la REDIAM en el que se simulan las condiciones climáticas de futuro. 







Cargar en QGIS o en R los datos de las variables abióticas


## Resultados esperados e interpretación ecológica

+ 



****

[Aquí](https://github.com/aprendiendo-cosas/P_area_distribucion_especies_ecologia_sig_ccaa/archive/refs/tags/2025_2026.zip) puedes descargar un archivo .zip que contiene este guión en formato html y todo el material que incluye.

****
Haz click [aquí](https://github.com/aprendiendo-cosas/P_area_distribucion_especies_ecologia_sig_ccaa/releases) para ver cómo ha cambiado este guión en los distintos cursos académicos.

****
 <p xmlns:cc="http://creativecommons.org/ns#" >El contenido de este repositorio se puede utilizar bajo la siguiente licencia:  <a  href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1"  target="_blank" rel="license noopener noreferrer"  style="display:inline-block;">CC BY-NC-SA 4.0<img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"  alt=""></a></p> 

<p>Esta licencia no aplica a enlaces a artículos, libros o imágenes no originales. Estos productos tienen su licencia correspondiente.</p>






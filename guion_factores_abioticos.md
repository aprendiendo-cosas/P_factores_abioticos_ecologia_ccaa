

# Caracterización de los factores abióticos de los ecosistemas de Sierra Nevada

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

A continuación se describen los pasos que hay que dar para generar dos tipos de resultados:

+ Una tabla que muestre los valores promedio de las distintas variables abióticas para cada ecosistema.
+ Un mapa que muestre cómo se distribuye cada variable abiótica dentro de cada ecosistema. 

Describiré con menos detalle las cuestiones que ya habéis visto en la asignatura de SIG. Todo lo descrito aquí se puede hacer también con R.



### Creación de una tabla con los valores promedio de las variables abióticas en cada tipo de ecosistema



#### **1. Descargar los datos que necesitamos**

+ **1.1** [Aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/precip_media_actual.tif) tienes una capa mostrando el promedio de la precipitación total en cada píxel de Sierra Nevada en unas condiciones climáticas históricas. Esta información procede de [este](https://figshare.com/articles/dataset/Spatial_distribution_of_annual_and_seasonal_precipitation_mm_in_Sierra_Nevada_and_surroundings_with_the_accumulated_means_resulting_from_interpolation_raster_format_/14208392/2) producto generado por el [Observatorio de seguimiento del cambio global en Sierra Nevada](https://obsnev.es/).  
+ **1.2.** [Aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/precip_media_70_00.tif) puedes descargar una capa que contiene datos del promedio de la precipitación total prevista para Sierra Nevada de 2070 a 2100. Esta información se ha generado a partir de [este](https://portalrediam.cica.es/descargas/index.php/s/mxHMWXyHfrCxyNK?dir=/04_RECURSOS_NATURALES/03_CLIMA/03_CAMBIO_CLIMATICO/03_PRECIPITACION/06_TREINTENA/ESC_PRECIP_MEDIAS_TREINTENA_2000_2100/InfGeografica/InfRaster/TIFF) proyecto de la REDIAM en el que se simulan las condiciones climáticas de futuro. 
+ **1.3** [Esta](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/temp_media_actual.tif) capa muestra la temperatura promedio en cada píxel de Sierra Nevada en un escenario climático histórico (1991-2020). Se ha obtenido a partir de [este](https://portalrediam.cica.es/descargas/index.php/s/mxHMWXyHfrCxyNK?dir=/04_RECURSOS_NATURALES/03_CLIMA/02_CARACTERIZACION_CLIMATICA/02_TEMPERATURA/01_TEMPERATURA/01_MEDIA/01_ANUAL/TEMP_MEDIA_ANUAL_1991_2020/InfGeografica/InfRaster/COG) proyecto de la REDIAM.
+ **1.4**. [Esta](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/temp_media_70_00.tif) capa muestra la temperatura media prevista para Sierra Nevada en de 2070 a 2100. Procede de combinar la anterior con [este](https://portalrediam.cica.es/descargas/index.php/s/mxHMWXyHfrCxyNK?dir=/04_RECURSOS_NATURALES/03_CLIMA/03_CAMBIO_CLIMATICO/03_PRECIPITACION/06_TREINTENA/ESC_PRECIP_MEDIAS_TREINTENA_2000_2100/InfGeografica/InfRaster/TIFF) proyecto de la REDIAM. 
+ **1.5.** [Aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/mde_snev.zip) puedes descargar un modelo digital de elevaciones de Sierra Nevada. Cada píxel de esta capa muestra su altura sobre el nivel del mar. Como puedes ver, está comprimido, así que tienes que descomprimirlo.
+ **1.6** Por último, [aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/ecosistemas_snev_dissolve.zip) puedes bajar la capa con la distribución de los ecosistemas de Sierra Nevada. Y [aquí](https://github.com/aprendiendo-cosas/P_factores_abioticos_ecologia_ccaa/raw/refs/heads/main/geoinfo/bosque_ribera_dissolve.zip) tienes el mapa de distribución de los bosques de ribera, que no aparecen en el mapa anterior. 

#### 2. Cargar las capas anteriores en QGIS

+ **2.1.** Para cargarlas en QGIS solo tienes que arrastrarlas al proyecto que tengas abierto. Recuerda siempre guardar el proyecto en la misma carpeta donde tengas la capas. Esto facilitará el manejo del proyecto.

#### 3 Asignar a cada tipo de ecosistema valores de las capas raster con las variables abióticas

+ **3.1.** Para hacer esto en Qgis tendrás que usar una herramienta llamada `Zonal statistics`. Podrás encontrarla en el menú de procesamientos. Para usar esta herramienta necesitas indicar lo siguiente (ten en cuenta que dependiendo de la versión de QGIS que estés usando, las opciones siguientes pueden tener nombres diferentes):
  + `Raster layer`: Señala aquí la capa de la que quieras extraer los datos. Por ejemplo el modelo digital de elevaciones.
  + `Output column prefix`: Te permite indicar el prefijo que tendrán las nuevas columnas que se creen en la tabla. Sugiero que pongas un prefijo que identifique a la variable con la que estás trabajando. Como tienes que repetir este proceso para cada una de las capas descargadas en el punto 1, es necesario buscar una forma de identificar bien cada uno de los campos creados. Debe de ser un nombre con solo 3 caracteres. Por ejemplo:
    + `ta_` para temperatura actual
    + `tf_`  para temperatura del futuro
    + `pa_` precipitación actual
    + `pf_` precipitación del futuro
    + ` al_` altura
  + `Statistics to calculate`: Permite seleccionar las estadísticas que calculará QGIS. En realidad esta operación es una agrupación espacial. Así que QGIS sumará, contará, hará la media o la operación que le digamos para cada tipo diferente de ecosistema. En nuestro caso es interesante decir que calcule los valores: `mean` (media), y `st dev` (desviación típica, que nos permitirá saber cómo de dispersos están los datos). Esto generará, para cada vez que lo ejecutes, una tabla con dos campos nuevos. Dependiendo de la variable con la que estés trabajando en cada caso, el nombre del campo resultará de combinar el prefijo anterior con `mean` o `stdev`. Quedaría algo así para la variable de la temperatura actual: `ta_mean` y `ta_stdev`. 
  + `save results`: Guarda el resultado en la misma carpeta en la que tengas los datos de entrada. Se generará un archivo con extensión `csv` que puedes abrir fácilmente con excel o con un editor de texto. Dale al archivo un nombre alineado a su contenido. Por ejemplo `precipitacion_actual_x_ecosistema.csv` en el caso de que estés trabajando con la capa de precipitación actual. 

#### 4 Repetir lo anterior para cada variable abiótica

+ **4.1** Necesitamos una tabla como la que obtendrás en el punto anterior para cada variable de las descargadas anteriormente. Así que, repite el proceso tantas veces como sea necesario.
+ **4.2** Al final de todo tendrás varias tablas en formato `csv`. Te recomiendo que las unas todas usando excel, por ejemplo. La idea es tener una única tabla con esta estructura (ojo, los datos numéricos de la tabla son aleatorios, no los uses. Tienes que hacer scroll horizontal para verla completa):



| nombre                                           | Shape_Leng  | Shape_Area  | id_poligon | ta_mean     | ta_stdev    | tf_mean  | tf_stdev    | pa_mean     | pa_stdev    | pf_mean     | pf_stdev    | al_mean     | al_stdev    |
| ------------------------------------------------ | ----------- | ----------- | ---------- | ----------- | ----------- | -------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| Robledales                                       | 5289,213361 | 131694,5414 | 1487       | 2,856571623 | 1,120007784 | 1,633501 | 6,880156837 | 4,052079597 | 4,109339694 | 1,746909448 | 5,281121675 | 5,390148692 | 2,668022494 |
| Pastos de media montaña                          | 3206,648662 | 324801,494  | 461        | 2,126194231 | 1,442313394 | 2,760936 | 0,536124978 | 6,643128883 | 3,262306725 | 8,739225887 | 8,178168308 | 8,250972068 | 3,953220293 |
| Sistemas acuáticos                               | 4539,133812 | 63788,6088  | 1174       | 2,458598944 | 1,263073943 | 1,225111 | 2,761615932 | 4,268426567 | 0,21934249  | 6,868935954 | 8,586095629 | 5,943930956 | 6,672928133 |
| Pastizales, canchales y roquedos de Alta Montaña | 5840,482372 | 412851,1107 | 1          | 1,680155652 | 1,780184566 | 7,348216 | 7,619043048 | 4,36961895  | 6,410329298 | 2,948409443 | 0,801292824 | 9,952286421 | 5,539704037 |
| Encinares                                        | 2563,105023 | 295953,8466 | 79         | 2,733185765 | 1,137250676 | 5,011479 | 1,019444637 | 6,163159001 | 0,330372789 | 3,993890168 | 0,010332039 | 4,06533287  | 8,200077325 |
| Pinares autóctonos sobre dolomías                | 1573,104379 | 81719,54035 | 756        | 3,542568445 | 1,263193743 | 5,258002 | 5,917499285 | 2,127568039 | 1,585572748 | 2,053065273 | 2,333965431 | 7,863666948 | 9,750203691 |
| Enebrales-piornales                              | 1376,37568  | 63688,78775 | 766        | 2,137801415 | 1,454736179 | 4,115798 | 2,654023897 | 6,92372842  | 0,913176429 | 9,088426591 | 8,79790932  | 6,966773412 | 0,696790876 |
| Cultivos de montaña extensivos                   | 994,4622698 | 60263,01713 | 951        | 2,130524017 | 1,475686803 | 4,779599 | 3,192221449 | 6,331009949 | 4,037629761 | 4,565551668 | 7,90780771  | 8,050932092 | 9,703413929 |
| Pinares de repoblación                           | 1492,433443 | 64300,65175 | 1244       | 2,792307664 | 1,124294337 | 0,511311 | 0,975815956 | 0,125740095 | 6,32778589  | 0,926729112 | 5,361922407 | 1,79719063  | 6,726699634 |
| Pinares autóctonos de P. sylvestris              | 7956,790165 | 1014679,953 | 1172       | 4,707723127 | 1,284966339 | 9,375124 | 9,663029326 | 0,95544566  | 7,268674059 | 0,743568128 | 6,364350523 | 8,277224986 | 0,463278587 |
| Borreguiles                                      | 4764,119297 | 65930,61979 | 891        | 1,859918195 | 1,403088638 | 0,094232 | 5,602709677 | 7,205931627 | 2,111744056 | 3,686192995 | 7,194936797 | 3,043538669 | 9,401508228 |
| Matorral media montaña                           | 1768,617734 | 167534,1619 | 208        | 2,305119695 | 1,395373121 | 8,160462 | 4,576051731 | 1,708176984 | 6,955340855 | 6,213173687 | 8,447630413 | 7,528340731 | 9,466060239 |






## Resultados esperados e interpretación ecológica

+ 



****

[Aquí](https://github.com/aprendiendo-cosas/P_area_distribucion_especies_ecologia_sig_ccaa/archive/refs/tags/2025_2026.zip) puedes descargar un archivo .zip que contiene este guión en formato html y todo el material que incluye.

****
Haz click [aquí](https://github.com/aprendiendo-cosas/P_area_distribucion_especies_ecologia_sig_ccaa/releases) para ver cómo ha cambiado este guión en los distintos cursos académicos.

****
 <p xmlns:cc="http://creativecommons.org/ns#" >El contenido de este repositorio se puede utilizar bajo la siguiente licencia:  <a  href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1"  target="_blank" rel="license noopener noreferrer"  style="display:inline-block;">CC BY-NC-SA 4.0<img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"  alt=""></a></p> 

<p>Esta licencia no aplica a enlaces a artículos, libros o imágenes no originales. Estos productos tienen su licencia correspondiente.</p>






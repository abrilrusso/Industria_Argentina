# Industria Argentina: ¿crisis o transformacion?
## Presentacion 
-Integrantes: Abril Russo Bergara y Franco Nicolas Croce

-Materia: Ciencia de Datos para Economía y Negocios

-Profesor: Nicolas Sidicario

-Facultad de Ciencias Económicas - UBA

## Descripción del proyecto💡

Este proyecto surge del trabajo de dos estudiantes de la Facultad de Ciencias Económicas, guiados por nuestro profesor de Ciencia de Datos, con el objetivo de analizar la evolución de la industria argentina a lo largo de las últimas décadas.

A través del análisis de datos, visualizaciones y herramientas estadísticas, buscamos estudiar el comportamiento del sector industrial para identificar patrones, transformaciones y posibles períodos de crecimiento o retroceso. Asimismo, realizamos una comparación con otros países de América Latina con el fin de contextualizar el caso argentino dentro de una dinámica regional más amplia.

Nuestro objetivo es aportar evidencia empírica para comprender las transformaciones productivas de Argentina y evaluar su desempeño industrial en perspectiva regional.

## Hipótesis de trabajo 🕵️‍♀️
### Hipótesis principal 
En los últimos cincuenta años, Argentina experimentó un proceso de desindustrialización que deterioró su capacidad productiva industrial real, alejándola de la trayectoria de crecimiento sostenido que lograron mantener países de la región como Brasil y México.

### Hipótesis complementaria
La reducción del peso de la industria en la economía argentina responde principalmente a un proceso de reprimarización. El crecimiento de sectores primarios (favorecidos por cambios en los precios internacionales y la expansión de actividades como el agro y la energía) habría disminuido la participación relativa de la industria en el PBI, sin implicar necesariamente una caída absoluta de la producción industrial.

## Bases de datos utilizadas 📊
### Fuente principal
- [Argendata](https://argendata.fund.ar/topico/industria/) 

### Fuentes auxiliares
- [Banco Mundial](https://datos.bancomundial.org/indicador/NV.AGR.TOTL.ZS) 
- [Comision Europea](https://composite-indicators.jrc.ec.europa.eu/explorer/indices/cipi/competitive-industrial-performance-index)
### Período trabajado ⏳

1970–2024

### Variables principales
-PBI industrial per cápita

-Participación de la industria en el PBI 

-Participación del sector primario en el PBI 

-Participación de manufacturas en exportaciones totales 

-Importaciones y exportaciones industriales 

-Índice de desempeño industrial competitivo

### Paises trabajados 🌎
- Argentina
- Brasil
- Chile
- México

## Estrategia de análisis 📚
En una primera etapa, estudiamos la evolución del sector industrial argentino a partir de indicadores como la participación de la industria en el PBI y el PBI industrial per cápita.

Luego, comparamos la trayectoria argentina con la de otros países de América Latina para evaluar si su desempeño responde a una tendencia regional o  a  una dinámica particular.

Por último, aplicamos herramientas de análisis temporal e inferencia estadística para distinguir entre cambios estructurales de largo plazo y fluctuaciones temporales asociadas a shocks económicos.

### Librerias requeridas 💻
- tidyverse
- readxl
- scales
- zoo
- dlookr
- naniar

### Herramientas metodológicas 🛠️
- Indexación de series (base 1970 = 100): permite comparar variables con distinta escala.
- Tasas de variación acumuladas: mide cambios por subperíodos.
- Descomposición por promedio movil: permite suavizar fluctuaciones de corto plazo e identificar la tendencia de largo plazo.
- Prueba T de Welch: evalúa diferencias entre países


## Estructura del repositorio 📁
```bash
Industria argentina/
├── raw/        # Bases originales descargadas
├── input/      # Bases limpias y listas
├── auxiliar/   # Bases complementarias
├── output/     # Gráficos, tablas y resultados
├── scripts/    # Scripts del proyecto
└── README.md   # Documentación del proyecto
```

## Instrucciones de reproducción
1. Descargar o clonar el repositorio

2. Abrir el proyecto en RStudio.

3. Instalar las librerías necesarias:
install.packages(c("tidyverse", "readxl", "scales", "zoo","dlookr","naniar"))

4. Ejecutar los scripts en el siguiente orden:

- 00a_instalar_paquetes.R → Instala y verifica las librerías necesarias para ejecutar el proyecto.

- 00b_datos_faltantes_outliers.R → Realiza el diagnóstico inicial de datos faltantes y posibles valores atípicos.

- 01_PBI_industrial_per_capita_comparado.R → Analiza y grafica la evolución del PBI industrial per cápita entre países.

- 02a_share_industrial_y_primario_ARG.R → Calcula y grafica la participación de los sectores industrial y primario en el PBI de Argentina.

- 02b_share_industrial_y_primario_BR.R → Calcula y grafica la participación de los sectores industrial y primario en el PBI de Brasil.

- 02c_share_industrial_y_primario_MEX.R → Calcula y grafica la participación de los sectores industrial y primario en el PBI de México.

- 02d_share_industrial_y_primario_CHI.R → Calcula y grafica la participación de los sectores industrial y primario en el PBI de Chile.

- 03_estadisticas_descriptivas.R → Genera estadísticas descriptivas de las variables analizadas.

- 04_pbi_industrial_comparado.R → Compara la evolución del PBI industrial entre los países seleccionados.

- 05_balanza_comercial_industrial.R → Analiza la balanza comercial industrial (exportaciones e importaciones).

- 06_manufacturas_expo_totales.R → Estudia la participación de las manufacturas en las exportaciones totales.

- 07_descomposicion_por_promedio_movil.R → Aplica promedios móviles para identificar tendencias en las series temporales.

- 08_test_de_welch.R → Realiza el test de Welch para comparar medias entre períodos o grupos.

5. Los gráficos y resultados se guardaran automáticamente en la carpeta "output".



## Conclusiones 📝
La evidencia respalda la hipótesis principal: Argentina atravesó un proceso de desindustrialización estructural, y no una simple transformación hacia otros sectores. Tres resultados lo confirman:

1. Argentina es el único de los cuatro países que en 2024 produce menos industria por habitante que en 1970 (-17,6%), mientras Brasil, México  y Chile crecieron entre 44% y 86% en el mismo período.

2. El promedio móvil muestra que la caída no fue un evento puntual: la tendencia bajó de forma sostenida desde 30,4% en 1973 hasta 17,95% en 2021, sin recuperación duradera en ningún tramo de más de cinco décadas. Las crisis de 1989 y 2001 generaron desvíos fuertes pero acotados en el tiempo, lo que confirma que son shocks puntuales sobre una tendencia que ya venía cayendo, y no la causa de fondo.

3. La hipótesis complementaria de reprimarización se descarta: el sector primario también perdió participación en el PBI (de 9,6% en 1970 a 5,8% en 2024), por lo que el agro no explica el retroceso industrial.

En síntesis, no se trató de una transformación productiva saludable donde la industria cede lugar a otros sectores en crecimiento, sino de una pérdida de capacidad productiva real y sostenida en el tiempo, agravada (pero no causada) por las crisis macroeconómicas del período.


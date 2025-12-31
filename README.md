# RPubs - índice curado

Este repositorio reúne **resúmenes curados** de análisis empíricos y ejercicios macroeconómicos que he publicado en RPubs.  
Su objetivo no es replicar el contenido original, sino **ofrecer un mapa temático** que facilite la navegación por trabajos sobre econometría aplicada, macroeconomía y manejo de datos económicos en R.  
Las entradas están organizadas por **tipo de problema empírico**, no por fecha ni por nivel de dificultad.

## Contenido (Table of contents)

### A) APIs y fuentes de datos
- API del Banco Mundial (`{WDI}`)
- API de Banxico (`{siebanxicor}`)

### B) Manipulación de datos y visualización
- Salario promedio del IMSS
- Índice de Kaitz con datos de la OIT (`{Rilostat}`)
- Rezago habitacional 2020 (CONAVI)

### C) Series de tiempo y modelado
- Desestacionalización de múltiples series en R
- Tidy modeling con datos de la Reserva Federal (API FRED)

### D) Macroeconomía
- Tipo de cambio real de equilibrio (enfoque Rodrik) con PWT
- Descomposición del deflactor del PIB (INEGI)
- JST Macrohistory Database: inflación y tasas reales

## A) APIs y fuentes de datos

### API del Banco Mundial (`{WDI}`)

Uso de la librería `{WDI}` como interfaz sencilla para acceder a la base de *World Development Indicators* del Banco Mundial, una de las fuentes más amplias de indicadores económicos, sociales y demográficos a nivel internacional.  
El énfasis está en la descarga conjunta de múltiples países y periodos en un solo paso, integrando los datos en flujos tidy para su análisis posterior.  
De forma complementaria, se utiliza `{naniar}` para identificar y visualizar valores faltantes, resaltando las limitaciones de cobertura temporal y geográfica sin aplicar imputaciones ni tratamientos adicionales.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/api_wdi>

### API de Banxico

Uso de la API del Banco de México para acceder de forma programática a información monetaria y financiera oficial.  
El ejercicio ilustra la integración de series mediante `{siebanxicor}`, junto con `{tidyverse}` y `{lubridate}`, para el cálculo de un **indicador básico de suficiencia de reservas internacionales**.  
El énfasis está en el acceso a la fuente y la construcción del indicador, más que en una discusión exhaustiva de política monetaria.  
Como referencia conceptual, se remite al libro *Instrumentación de las operaciones monetarias, cambiarias y de administración de reservas* del Banco de México.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/api_banxico>

## B) Manipulación de datos y visualización

### Salario promedio del IMSS

Uso de los **Datos Abiertos del IMSS** sobre empleo asegurado y salario base de cotización promedio (SBC), bases administrativas de **gran volumen**.  
El ejercicio muestra cómo calcular el **empleo asegurado total** y el **SBC promedio** a nivel nacional utilizando `{dplyr}` como herramienta de manipulación de datos.  
De manera adicional, se ilustra la desagregación de estas variables por **sector económico y género**, destacando la flexibilidad del enfoque según el nivel de análisis requerido.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/imss_dplyr>

### Índice de Kaitz con datos de la OIT (`{Rilostat}`)

Uso del paquete `{Rilostat}` como interfaz para acceder a **ILOSTAT**, el repositorio más amplio de estadísticas laborales a nivel mundial.  
El ejercicio muestra la descarga y organización de indicadores laborales para distintos países y años en un solo paso, integrándolos en flujos tidy mediante operaciones básicas de unión (`left_join`) y manejo de identificadores.  
A partir de esta información se calcula el **índice de Kaitz**, definido como la relación entre el salario mínimo y el salario medio.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/rilostats_kaitz>

### Rezago habitacional 2020 (CONAVI)

Replicación en R de la **metodología oficial de CONAVI** para el cálculo del rezago habitacional en México, utilizando exclusivamente el *Censo de Población y Vivienda 2020* del INEGI.  
El ejercicio implementa los criterios de selección y exclusión de viviendas particulares habitadas definidos por CONAVI, procesando microdatos censales mediante flujos tidy con `{tidyverse}`.  
El énfasis está en la **operacionalización transparente de criterios institucionales**, no en la evaluación normativa del rezago.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/rezago2020>

## C) Series de tiempo y modelado

### Desestacionalización de múltiples series en R

Uso de la **API de INEGI** para obtener series económicas y aplicar un ajuste estacional masivo en R.  
El ejercicio se centra en la desestacionalización simultánea de múltiples series mediante `{seasonal}`, interfaz de *X-13-ARIMA-SEATS*, destacando la automatización del proceso y el acceso a salidas estándar del método.  
Tras el relanzamiento del Banco de Información Económica (BIE) de INEGI, el paquete `{inegiR}` **ya no opera**, por lo que el valor del ejercicio reside en la **reproducibilidad y conceptualización del cálculo**, más que en la herramienta específica.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/tidy_modeling_seas>  
📂 Repo: <https://github.com/ecodiegoale/imss-tidy-seasonal>

### Tidy modeling con datos de la Reserva Federal (API FRED)

Uso de la **API de la Reserva Federal de Estados Unidos (FRED)** para acceder a series macroeconómicas y organizarlas en flujos de trabajo tidy.  
El énfasis del ejercicio está en la **programación funcional con `{purrr}`**, utilizando listas para manipular y procesar múltiples series de forma sistemática.  
De manera complementaria, se ilustra la desestacionalización simultánea de múltiples series utilizando `{seasonal}` en conjunto con `{fredr}`, como interfaz para *X-13-ARIMA-SEATS*.  
Finalmente, se presenta una visualización sintética de los datos procesados mediante **gráficos tipo waffle**.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/fred_purrr>

## D) Macroeconomía

### Tipo de cambio real de equilibrio (enfoque Rodrik) con PWT

Implementación en R del **índice de tipo de cambio real** propuesto por Dani Rodrik para el análisis de su relación con el crecimiento económico.  
El ejercicio replica el enfoque original utilizando la **Penn World Table 6.2** y presenta una extensión actualizada empleando la **Penn World Table 10.01**, disponible como librería en R (`{pwt10}`).  
La estimación se realiza mediante un **modelo de panel con efectos fijos**, con énfasis en la reproducibilidad del cálculo.  

🔗 RPubs (pt. 1): <https://rpubs.com/ecodiegoale/rodrik-balassasamuelson>  
🔗 RPubs (pt. 2): <https://rpubs.com/ecodiegoale/rodrikpt2>

### Descomposición del deflactor del PIB (INEGI)

Uso de la **API de INEGI** para descomponer la **tasa de crecimiento del deflactor implícito del PIB de México** en **impuestos**, **excedente de operación (ganancias)** y **remuneraciones al trabajo**.  
El cálculo sigue la **metodología propuesta por la CONASAMI**, priorizando la consistencia conceptual y la trazabilidad del ejercicio.  
El valor del análisis reside en la **reproducibilidad y conceptualización del cálculo**, característico de un procedimiento estándar en macroeconomía aplicada.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/deflactor_API-inegiR>

### JST Macrohistory Database: inflación y tasas reales

Uso de la **Jordà–Schularick–Taylor Macrohistory Database (JSTMD)** para calcular **inflación** y **tasas de interés reales de largo plazo** para el conjunto de países disponibles.  
El ejercicio desarrolla una **función reusable** que automatiza la elaboración de gráficas comparables de las variables construidas.  

🔗 RPubs: <https://rpubs.com/ecodiegoale/JSTMD-ggplot2>

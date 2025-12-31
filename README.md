# RPubs — índice curado

Este repositorio reúne **resúmenes curados** de análisis empíricos y ejercicios macroeconómicos que he publicado en RPubs.  
Su objetivo no es replicar el contenido original, sino **ofrecer un mapa temático** que facilite la navegación por trabajos sobre econometría aplicada, macroeconomía y manejo de datos económicos en R.  
Las entradas están organizadas por **tipo de problema empírico**, no por fecha ni por nivel de dificultad.

## Table of contents

### A) APIs y fuentes de datos
- API del Banco Mundial (WDI)
- API de Banxico

### B) Manipulación de datos y visualización
- Salario promedio del IMSS
- Índice de Kaitz con datos de la OIT (rilostat)
- Rezago habitacional 2020 (CONAVI)

### C) Series de tiempo y modelado
- Desestacionalización de múltiples series en R
- Tidy modeling con datos de la Reserva Federal (API FRED)

### D) Macroeconomía
- Tipo de cambio real de equilibrio (enfoque Rodrik) con PWT
- Descomposición del deflactor del PIB (INEGI)
- JST Macrohistory Database: inflación y tasas reales

## A) APIs y fuentes de datos

### API del Banco Mundial (WDI)

Uso de la librería `{WDI}` como interfaz sencilla para acceder a la base de *World Development Indicators* del Banco Mundial, una de las fuentes más amplias de indicadores económicos, sociales y demográficos a nivel internacional.  
El énfasis está en la descarga conjunta de múltiples países y periodos en un solo paso, integrando los datos en flujos tidy para su análisis posterior.  
De forma complementaria, se utiliza `{naniar}` para identificar y visualizar valores faltantes, resaltando las limitaciones de cobertura temporal y geográfica sin aplicar imputaciones ni tratamientos adicionales.  

→ 🔗 RPubs: <https://rpubs.com/ecodiegoale/api_wdi>




# Dashboard de Inteligencia de Mercado y Farmacovigilancia Analítica: Impacto de Eventos Adversos en el Posicionamiento de Analgésicos

## 📋 Descripción del Proyecto
Este proyecto desarrolla una solución integral de **Farmacovigilancia Analítica** que transforma datos públicos y complejos de salud de la FDA en *Business Intelligence*. El enfoque es de nivel **táctico**, diseñado para apoyar la toma de decisiones estratégicas intermedias en las áreas de **Market Intelligence** y **Risk Management** dentro del sector farmacéutico.

A través de un pipeline automatizado, se analizan las tendencias de seguridad biológica de la competencia, se detectan patrones de riesgo clínico y se generan *insights* comerciales para optimizar el posicionamiento de marca en el mercado de analgésicos.

---

## 🚀 Tecnologías y Herramientas Utilizadas
* **Python (Requests, Pandas):** Ingestión de datos, des anidación (*unnesting*) de JSON complejos y limpieza de datos.
* **SQL Server (SSMS):** Almacenamiento, diseño de arquitectura relacional y esquema en estrella.
* **SQLAlchemy / PyODBC:** Automatización de carga de datos desde Python a SQL.
* **Power BI:** Modelado analítico, cálculos DAX avanzados y visualización interactiva de datos (*Storytelling*).

---

## 📊 Arquitectura del Proyecto (Pipeline ETL & BI)

El proyecto sigue el ciclo clásico de un pipeline de analítica de datos:

1. **Extracción (API Ingestión):** Conexión programática a la API pública openFDA (`drug/event.json`) mediante Python. Se extrajo una muestra de **más de 4,000 registros** de eventos adversos comprendidos entre noviembre de 2013 y junio de 2014.
2. **Transformación (Data Wrangling):** Normalización de texto a mayúsculas, traducción de códigos numéricos, gestión de nulos (*imputation*) y des anidación de estructuras JSON (transformando reportes con múltiples síntomas en filas individuales).
3. **Carga y Modelado (Data Modeling):** Diseño e implementación de un **Modelo en Estrella de 5 tablas** (1 tabla de hechos y 4 dimensiones) en SQL Server con carga automatizada.
4. **Visualización y Analytics:** Conexión de Power BI a SQL Server, creación de tabla calendario nativa y centralización de la lógica de negocio mediante medidas DAX en una tabla única de métricas.

---

## 📐 Variables del Estudio y Metodología
* **Variable Independiente:** Tipo de analgésico / principio activo (Segmentación por competidores: *Ibuprofen, Naproxen, Acetaminophen, Tramadol* y por familias: *AINEs vs Opioides*).
* **Variables Dependientes:** 
  * Reacción adversa / Síntoma (estandarizada bajo terminología internacional **MedDRA**).
  * Gravedad del desenlace (Binarizada en: `provoco_muerte` [sí/no] y `provoco_hospitalizacion` [sí/no]).
* **Variables de Control (Demográficas):** Edad (Geriátrico, Adulto, Pediátrico) y Género (Masculino/Femenino).

---

## 🎯 Objetivos Desarrollados
* [x] **Data Engineering:** Consumo y aplanamiento automatizado de la API openFDA.
* [x] **Modelado SQL:** Implementación de arquitectura relacional optimizada para analítica.
* [x] **Análisis Comercial:** Clasificación de riesgos biológicos para identificar fallas de seguridad en productos de la competencia.
* [x] **Visualizaciones (BI):** Creación de un Dashboard interactivo que exponga ventajas competitivas y recomendaciones claras para el equipo de marketing.

---

## 📂 Vista del Dashboard 
* `/Formato_PBIX/`: Contiene el archivo clásico `.pbix` listo para descargar y ejecutar de forma local.
* `/Formato_PBIP/`: Proyecto estructurado de Power BI en archivos de texto, ideal para el seguimiento detallado de control de versiones y visualización de medidas DAX en código.
* `/Capturas de pantalla y video/`: Para visualización rápida
  
---
*Proyecto Final presentado para la certificación en **Data Analytics**.*

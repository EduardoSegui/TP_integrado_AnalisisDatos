# Sprint 1

## Objetivo

El objetivo principal de este proyecto es aplicar los conocimientos adquiridos en para el versionado de código, la organización, limpieza del código y la utilización de pandas.

## Introducción y Contexto del problema

La localidad llamada Vaalserberg de Bélgica se encuentra en la zona fronteriza y limita con los paises de Países Bajos y Alemania. Esta localidad cuenta con un sistema de radares urbanos para la detección de infracciones por exceso de velocidad. Los registros históricos provienen de sistemas heredados, el cuál presenta errores de formato, faltante de datos generando registros inconsistentes en el nuevo sistema.

Debemos analizar y depurar los datos de viejo sistema para obtener información relevante sobre las infracciones y de está forma en el futuro poder incorporar los datos al nuevo sistema sin inconsistencias.

El dataset contiene información histórica de multas por exceso de velocidad y presenta errores que deberán ser tratados para evitar inconsistencias.




 # Sprint 2 
 ### Objetivo
 El objetivo de este sprint es desarrollar un sistema automatizado que determine qué multas por exceso de velocidad cuentan con evidencia visual válida, utilizando técnicas de procesamiento de imágenes y reconocimiento óptico de caracteres (OCR).
 
 ### Introducción y Contexto
 Los radares urbanos de Vaalserberg generan registros administrativos automáticos. Sin embargo, la consistencia entre la multa y la imagen capturada no siempre es perfecta. Este proyecto busca mitigar errores de detección y asegurar que cada infracción esté debidamente respaldada por una imagen de la patente legible.
 
 ### Metodología y Hallazgos Técnicos
 Para optimizar la lectura de patentes, se exploraron diferentes técnicas de procesamiento de imágenes sobre el dataset:
 * **Escala de Grises:** Estandarización de la información cromática.
 * **Suavizado (Gaussian Blur):** Esta técnica resultó ser la más efectiva para reducir el ruido digital, permitiendo al motor de OCR (`easyocr`) obtener lecturas más precisas.
 * **Detección de Bordes (Canny):** Se utilizó para experimentación de segmentación de caracteres.
 
 ### Resultados Finales
 * **Multas con evidencia válida:** 755 registros vinculados con un match > 80%.
 * **Brecha de Cobro:** Se identificaron 379 multas pendientes de pago que cuentan con evidencia visual sólida para proceder con el reclamo administrativo.

# Sprint 3
### Conclusión del Sprint 3

En este sprint, hemos logrado profesionalizar el sistema de gestión de infracciones de Vaalserberg mediante la implementación de varias tecnologías clave:

1.  **Persistencia Robusta**: Migramos de archivos CSV a una base de datos relacional (SQLite) utilizando **SQLAlchemy**. Esto permite realizar consultas complejas, asegurar la integridad de los datos mediante relaciones (Vehículo-Multa-Radar-Evidencia) y escalar la solución.
2.  **Versionado de Datos**: Implementamos **DVC (Data Version Control)** para gestionar archivos binarios y datasets pesados. Esto separa el ciclo de vida del código del de los datos, permitiendo un repositorio de Git liviano y un historial de cambios en los datos auditable.
3.  **Búsqueda Inteligente**: Integramos una **base de datos vectorial (ChromaDB)** con el modelo **OpenClip**. Esta capacidad permite al sistema identificar vehículos a partir de imágenes de radares por similitud visual, cerrando la brecha entre la evidencia no estructurada y los registros estructurados en SQL.
4.  **Integración de Datos**: La función `buscar_patente_imagen` demuestra el poder de combinar estas herramientas, permitiendo que una simple imagen desencadene una recuperación completa del historial de multas de un ciudadano.
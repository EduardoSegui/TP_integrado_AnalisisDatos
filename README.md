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



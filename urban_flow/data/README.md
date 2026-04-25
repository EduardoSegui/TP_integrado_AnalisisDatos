El análisis del dataset `speeding_fines.csv` reveló la necesidad de una 
limpieza exhaustiva de los datos. Se identificaron y trataron valores nulos en 
columnas críticas como 'patente' y 'velocidad_registrada'. Las fechas y horas 
fueron normalizadas a formatos consistentes, y los valores inválidos fueron 
reemplazados para asegurar la integridad de los datos. Además, se limpiaron y 
estandarizaron las ubicaciones y patentes.

Tras la limpieza, se calcularon las columnas de 'exceso_velocidad_real' y 
'exceso_velocidad', lo que permitió filtrar las filas que no representaban 
infracciones reales. Esto resultó en la eliminación de un número significativo 
de registros, dejando un dataset más preciso y relevante para el análisis.

Los primeros análisis exploratorios mostraron:
*   **Patentes más reincidentes:** Se identificó un ranking de patentes con 
mayor número de infracciones, lo cual podría indicar 
patrones de comportamiento o zonas de control más activas.
*   **Horarios de infracción:** La hora '00:00' (que incluye 
datos originalmente inválidos) y otras horas específicas concentran 
una parte importante de las multas, lo que sugiere 
momentos de mayor actividad o menor vigilancia.
*   **Ubicaciones más comunes:** 'AV LIBERTADOR', 'AV SIEMPRE VIVA' y 'RUTA 9' 
son las ubicaciones con mayor cantidad de multas, señalando puntos 
críticos para la implementación de medidas de control de velocidad.

El dataset inicial contenía inconsistencias significativas pero después 
del proceso de limpieza y normalización, se obtuvo una base de datos más 
confiable que permitió extraer información valiosa sobre las infracciones 
de velocidad, sentando las bases para futuras etapas de análisis 
y toma de decisiones.
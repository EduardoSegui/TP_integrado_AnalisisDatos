El análisis del dataset `speeding_fines.csv` reveló la necesidad de una 
limpieza exhaustiva de los datos. Se identificaron y trataron valores nulos en 
columnas críticas como 'patente' y 'velocidad_registrada'. Las fechas y horas 
fueron normalizadas a formatos consistentes, y los valores inválidos fueron 
reemplazados para asegurar la integridad de los datos. Además, se limpiaron y 
estandarizaron las ubicaciones y patentes.

Tras la limpieza, se calcularon las columnas de 'exceso_velocidad_real' y 'exceso_velocidad', lo que permitió filtrar las filas que no representaban infracciones reales. Tras eliminar los valores nulos de las las columas relevantes el  resultó fue la eliminación de un número significativo de registros, dejando un dataset más preciso y relevante para el análisis.

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



### Conclusión Final del Proyecto Sprint 2

El desarrollo de este sistema de validación visual para infracciones de tránsito permitió demostrar la importancia crítica del pre-procesamiento de datos no estructurados. A continuación, se resumen los puntos clave:

1.  **Optimización del OCR:** Se determinó experimentalmente que la aplicación de un filtro de **suavizado Gaussiano (Blur)** fue la técnica más efectiva, permitiendo que el motor de OCR (`easyocr`) interpretara correctamente las patentes al reducir el ruido digital sin fragmentar los caracteres (como sucedió con Canny).
2.  **Validación de Evidencia:** El sistema logró vincular exitosamente **755 infracciones** con su evidencia visual correspondiente utilizando un criterio de coincidencia (ratio) mayor al 80%, lo que dota de validez legal y administrativa al registro de multas.
3.  **Identificación de Brechas:** El análisis reveló que **848 multas** continúan pendientes de pago, de las cuales **379 cuentan con evidencia visual válida**, lo que representa una oportunidad crítica para la gestión de cobro basada en pruebas sólidas.
4.  **Escalabilidad:** La metodología empleada (limpieza de caracteres, cálculo de ratios de similitud y almacenamiento en JSON) permite que el sistema sea escalable para procesar volúmenes mayores de datos en futuros despliegues del sistema de radares de Vaalserberg.

En conclusión, la integración de técnicas de visión computacional con el análisis de datos administrativos del Sprint 1 ha resultado en una herramienta robusta para la depuración y validación del sistema de gestión de multas urbano.

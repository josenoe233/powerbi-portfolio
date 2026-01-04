===========================================================
                DATA MODEL EXPLANATION (STAR SCHEMA)
           Proyecto: Global Benchmarking Dashboard
           Autor: Jose Noe s.
           Fecha: 2025
===========================================================

1. OBJETIVO DEL MODELO
-----------------------
El modelo estrella permite:
- Optimizar cálculos y rendimiento en Power BI.
- Separar datos descriptivos (dimensiones) de datos medibles (hechos).
- Facilitar análisis por segmentación (país, edad, género, etc.).
- Mantener una arquitectura profesional, escalable y clara.

El objetivo final es tener una tabla central (Fact) conectada a varias tablas Dimensión que enriquecen el análisis.

-----------------------------------------------------------

2. TABLA DE HECHOS (FACT TABLE)
-------------------------------

FACT: FactSurveyResponses
-------------------------
Contiene una fila por encuestado.

Incluye:
- Edad (Q10)
- Salario actual
- Puntajes de felicidad laboral (Q6)
- Lenguaje de programación favorito
- Industria
- País
- Género
- Nivel educativo
- Tiempo de completado de encuesta

Esta es la tabla donde se realizan los cálculos DAX:
- Promedios
- Conteos
- Segmentaciones
- Medidas de satisfacción

Relaciones: Todas las dimensiones se conectan a esta tabla.

-----------------------------------------------------------

3. TABLAS DE DIMENSIÓN
-----------------------

DIMENSION: DimCountry
----------------------
Descripción: País donde vive el encuestado.
Campo clave: Q11 - Which Country do you live in?
Relación: 1 → * con FactSurveyResponses.
Uso: Segmentar resultados por país.

DIMENSION: DimAge
------------------
Descripción: Rango o valor de edad del participante.
Campo clave: Q10 - Current Age.
Relación: 1 → * con FactSurveyResponses.
Uso: Análisis demográfico y comparaciones de salario vs edad.

DIMENSION: DimGender
---------------------
Descripción: Género del encuestado.
Campo clave: Q9 - Male/Female?
Relación: 1 → * con FactSurveyResponses.
Uso: Comparar salario promedio, felicidad y distribución por género.

DIMENSION: DimEducation
------------------------
Descripción: Nivel educativo más alto alcanzado.
Campo clave: Q12 - Highest Level of Education.
Relación: 1 → * con FactSurveyResponses.
Uso: Análisis de salario vs nivel educativo.

DIMENSION: DimEthnicity
------------------------
Descripción: Etnicidad o grupo cultural del encuestado.
Campo clave: Q13 - Ethnicity.
Relación: 1 → * con FactSurveyResponses.
Uso: Diversidad, cultura laboral, salario promedio por etnia.

-----------------------------------------------------------

4. ¿POR QUÉ UN MODELO ESTRELLA?
-------------------------------
Ventajas:
- Rendimiento óptimo en Power BI.
- Relación clara entre dimensiones y hechos.
- Alineado con mejores prácticas de BI.
- Facilita el filtrado y segmentación.
- Evita duplicidad y ambigüedad en los datos.
- Permite crear medidas DAX limpias y sin errores.

Es el estándar utilizado en empresas profesionales y entrevistas de Data Analyst / BI Analyst.

-----------------------------------------------------------

5. TIPOS DE RELACIÓN (TODAS CORRECTAS)
--------------------------------------
- Tipo: 1 → * (Una categoría aplica a muchos registros de la encuesta)
- Dirección del filtro: Single direction (una sola dirección)
- Relación Dim → Fact (las dimensiones filtran a la tabla de hechos)

Regla profesional aplicada:
"Las dimensiones describen; los hechos se calculan."

-----------------------------------------------------------

6. BENEFICIOS DEL MODELO
-------------------------
- Escalable si se agregan más preguntas o encuestas.
- Fácil de entender para gerentes y reclutadores.
- Permite construir dashboards limpios y profesionales.
- Permite añadir nuevas medidas DAX fácilmente.
- Base sólida para análisis avanzados.

-----------------------------------------------------------

7. CONCLUSIÓN
--------------
El modelo estrella del proyecto Global Benchmarking Dashboard es un diseño profesional que separa correctamente:
- Datos descriptivos (Dimensiones)
- Datos medibles (Hechos)
===========================================================

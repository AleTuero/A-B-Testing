PROYECTO A/B TESTING - ANALISIS DE FUNNEL WEB
📌 Descripción

Este proyecto analiza un experimento de A/B Testing a partir de varios datasets que contienen:

Asignación a grupo Control, Test o sin grupo

Datos de navegación web con pasos de un proceso (funnel)

El objetivo es evaluar si la variación Test mejora el rendimiento del proceso digital frente al grupo Control, utilizando métricas de conversión, tiempos, errores y contrastes estadísticos.

El proyecto se ha desarrollado en Python utilizando Visual Studio Code para el procesamiento, limpieza y análisis de datos, y se ha presentado mediante un informe visual en forma de dashboard interactivo en Power BI, donde se muestran las principales métricas, resultados del A/B testing y el análisis del funnel web y el contraste de hipótesis.

👥 Autores

Marta Carballo

Alejandro de Tuero

🗂️ Fuentes de datos

Archivos originales en formato .txt:

df_final_demo.txt → datos demográficos

df_final_experiment_clients.txt → asignación a grupos

df_final_web_data_pt_1.txt y df_final_web_data_pt_2.txt → navegación web

Todos los .txt se convierten a .csv y se limpian antes del análisis.

🔄 Flujo del proyecto

Conversión de archivos TXT a CSV

Corrección de valores erróneos (ej. género “X” → “U”)

Revisión de nulos y duplicados

Unión de datos demográficos + experimento

Unión de datos web (pt1 + pt2)

Creación del funnel web

Cálculo de tiempos entre pasos

Detección de errores y retrocesos

Análisis A/B y contraste de hipótesis

📂 Archivos principales generados

df_final_demo.csv → datos demográficos limpios

df_final_experiment_clients.csv → clientes con grupo asignado

df_master.csv → unión de demografía + experimento

df_final_web_data.csv → navegación web unificada

web_funnel_clean_one_sheet.xlsx → funnel limpio

web_funnel_with_variation.xlsx → funnel con grupo Test/Control

df_master_with_value_category.csv → clientes categorizados por balance

🧹 Limpieza de datos

Eliminación de nulos en variables clave

Reemplazo de valores incorrectos en género

Conversión de tipos numéricos

Eliminación de duplicados

Validación de orden correcto del funnel

🧭 Funnel web

Pasos definidos:

start → step_1 → step_2 → step_3 → confirm


Se realizan:

Eliminación de loops y ruido

Eliminación de sesiones con orden incorrecto

Cálculo de:

Tiempo desde el paso anterior

Tiempo desde el inicio

Tiempo total hasta confirm

📊 Métricas analizadas

Conversión

Número total de sesiones

Sesiones que llegan a confirm

Tasa de finalización

Comparación Test vs Control

Tiempos

Tiempo medio por paso

Tiempo por paso según variación

Errores de navegación

Retrocesos en el proceso

Tasa de error por transición

Pasos donde más se retrocede

Segmentación de clientes

Por edad

Por antigüedad

Por género

Por balance:

High Value (>100.000)

Medium Value (50.000–100.000)

Low Value (<50.000)

🧪 A/B Testing
Hipótesis principal

H0: La tasa de finalización es igual en Test y Control

H1: La tasa de finalización es mayor en Test

Método:

Test de proporciones (Z-test)

Nivel de significación: 5%

Se calcula:

Tasa Test

Tasa Control

Diferencia absoluta

Lift relativo

Intervalo de confianza

Coste-efectividad

Hipótesis adicional

Comparación de edad media entre Test y Control

Welch t-test para medias independientes

📈 Coste-efectividad

Se evalúa si la mejora cumple:

Umbral +5 puntos porcentuales

Umbral +5% relativo

Conclusión basada en criterios estadísticos y de negocio.

▶️ Cómo ejecutar el proyecto

Convertir los archivos TXT a CSV con los scripts iniciales

Ejecutar la limpieza de datos demográficos

Crear df_master.csv

Unir y limpiar datos web

Generar web_funnel_clean_one_sheet.xlsx

Añadir la columna Variation

Ejecutar análisis A/B y contrastes

Ejemplo:

python script_conversion.py
python limpieza_datos.py
python funnel.py
python ab_testing.py


(Ajustar según vuestros archivos reales)

📝 Conclusión

Este proyecto permite:

Analizar el comportamiento de los usuarios en un proceso digital

Evaluar la eficacia de una nueva versión (Test)

Tomar decisiones basadas en datos y estadística

Entender dónde se pierden usuarios y por qué

El enfoque combina limpieza de datos, análisis exploratorio, funnel analytics y A/B testing con rigor estadístico.
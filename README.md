# Análisis de clientes ConnectaTel

## Objetivo
Evaluar el comportamiento de los clientes de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, con datos registrados hasta 2024. El análisis construye un perfil estadístico de los clientes, detecta comportamientos atípicos y crea segmentos por edad y nivel de uso, para sugerir mejoras en los planes y estrategias de retención.

## Datasets utilizados
- `plans.csv`: información de los planes (precio mensual, minutos, mensajes y GB incluidos, costos por extra). 2 filas.
- `users_latam.csv`: información de los clientes (edad, ciudad, fecha de registro, plan, fecha de baja). 4000 filas.
- `usage.csv`: detalle del uso real (llamadas y mensajes por usuario y fecha). 40,000 filas.

## Etapas del análisis
1. **Carga y exploración:** revisión de la estructura, tipos de datos y tamaño de cada dataset.
2. **Calidad de datos:** detección de valores nulos, sentinels (como -999 en edad y "?" en ciudad) y fechas imposibles (registros en 2026).
3. **Limpieza:** reemplazo del sentinel de edad por la mediana, conversión de "?" y fechas fuera de rango a nulos, y verificación de que los nulos de duración y longitud dependen del tipo de registro (MAR).
4. **Métricas por usuario:** agregación del uso (mensajes, llamadas y minutos) y combinación con la tabla de clientes.
5. **Visualización:** histogramas por plan y boxplots para detectar outliers (método IQR).
6. **Segmentación:** grupos por edad (Joven, Adulto, Adulto Mayor) y por nivel de uso (Bajo uso, Uso medio, Alto uso).
7. **Insights ejecutivos:** conclusiones y recomendaciones para el negocio.

## Cómo ejecutar el notebook
1. Descarga el archivo `.ipynb` de este repositorio.
2. Ábrelo en Jupyter Notebook, JupyterLab o Google Colab.
3. Coloca los tres archivos CSV en una carpeta accesible y ajusta las rutas de lectura (por ejemplo `/datasets/plans.csv`) a la ubicación de tus archivos.
4. Ejecuta todas las celdas en orden (**Kernel → Restart & Run All**).

## Guía de reproducción
- Librerías necesarias: `pandas`, `numpy`, `seaborn` y `matplotlib`. Para instalarlas: `pip install pandas numpy seaborn matplotlib`.
- Las celdas dependen unas de otras, por lo que deben ejecutarse de arriba hacia abajo.
- Los datos originales se proporcionan a través de la plataforma del curso y no se incluyen en este repositorio.

## Hallazgos principales
- Se corrigieron sentinels, fechas imposibles y nulos antes del análisis.
- El uso típico de los clientes es moderado, y los usuarios Basico y Premium se comportan de forma muy parecida.
- Se encontraron outliers solo hacia valores altos de uso, que se mantuvieron por representar a los clientes más activos.
- Se recomienda revisar el plan Premium y evaluar planes ajustados al uso real de cada segmento.

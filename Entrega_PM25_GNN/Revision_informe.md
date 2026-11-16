# Revisión editorial del informe PM2.5–GNN

Se revisó el informe completo contra el notebook original, la ejecución guardada, las métricas y la rúbrica. No se entrenaron modelos ni se cambiaron resultados.

- Se reorganizaron referencia, cuatro experimentos, cinco preguntas originales, incertidumbre, conclusiones y referencias.
- Se distribuyeron las tablas por experimento, conservando MAE e intervalos (estos últimos con la precisión del Word anterior).
- Las seis figuras principales se verificaron contra los bytes de las imágenes del notebook y se trasladaron al análisis correspondiente.
- La figura de barras de todos los experimentos se mantiene junto al experimento de K.
- Las curvas de validación se separaron en cuatro gráficos desde los historiales JSON existentes; no son experimentos nuevos. La figura agrupada anterior también se conserva como archivo.
- Se añadieron títulos descriptivos, referencias cruzadas, Arial, texto negro, títulos azul oscuro, paginación y tablas con encabezados repetidos.
- Se distinguieron intervalos GCN−promedio de vecinas de diferencias contra la GCN original. No se hallaron discrepancias numéricas.
- Se conserva la limitación de la ventana temporal: la figura no se presenta como el episodio máximo de contaminación.
- La versión anterior del informe permanece en el historial Git del repositorio.

## Figuras en orden de aparición

- Figura 1. Ubicación geográfica de las 12 estaciones de monitoreo de Pekín, coloreadas por su PM2.5 promedio de 2013–2017.
- Figura 2. Matriz de adyacencia y conexiones entre estaciones para K=3, después de simetrizar.
- Figura 3. Evolución de la pérdida de validación al cambiar la estación objetivo a Huairou y Tiantan.
- Figura 4. Comparación del MAE de la GCN y del promedio de vecinas en la configuración original y los siete experimentos.
- Figura 5. Evolución de la pérdida de validación para K=1, K=5 y K=8.
- Figura 6. Evolución de la pérdida de validación al enmascarar los seis rasgos del nodo objetivo.
- Figura 7. Evolución de la pérdida de validación de la GCN con tres capas de mensajes.
- Figura 8. Evolución temporal de las concentraciones de PM2.5 en Dongsi, Gucheng y Huairou durante la primera semana de 2016.
- Figura 9. Comparación del error de entrenamiento y validación de MLP y GCN durante 200 épocas.
- Figura 10. Comparación del MAE de los tres métodos de estimación en Aotizhongxin.
- Figura 11. Comparación entre concentraciones reales y estimadas de PM2.5: tramo temporal de prueba y dispersión de la GCN en toda la prueba.

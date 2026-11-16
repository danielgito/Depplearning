# Resumen de resultados

Las salidas archivadas presentan MAE de 35,2 para MLP, 8,8 para GCN y 7,6 para promedio de vecinas. La ejecución propia obtuvo, respectivamente, 36.1648, 8.7890 y 7.6399 µg/m³. La reducción de GCN frente al MLP fue de 75.70 %. La referencia espacial debe mantenerse: una ventaja frente al MLP meteorológico no demuestra una ventaja del aprendizaje sobre el promedio espacial. Para t+1, las salidas archivadas fueron 8,2, 9,8 y 11,0 para persistencia, MLP y GCN; la ejecución propia produjo 8.1995, 9.9012 y 10.9533. Las diferencias de entorno y redondeo impiden exigir igualdad binaria con la corrida del autor.

Configuración,Estación,K,Aristas,Vecinas,MAE GCN,MAE vecinas,Δ GCN−vecinas,IC95 inferior,IC95 superior
Original reejecutado,Aotizhongxin,3,25,6,8.789044883024514,7.639902676399026,1.1491422066254884,0.46212099410384033,2.0161715475959228
Huairou,Huairou,3,25,3,17.14457108063961,13.469933958985056,3.674637121654561,1.6612963864727954,5.926551865248095
Tiantan,Tiantan,3,25,4,8.055275061853747,6.693430656934306,1.3618444049194403,0.8005878205506322,1.9629636419818595
K=1,Aotizhongxin,1,8,1,8.977893319320783,8.132429614181438,0.8454637051393442,0.021890768401497458,1.7639888272003805
K=5,Aotizhongxin,5,41,11,9.075759926939671,8.613897051853256,0.4618628750864154,0.0016067587359738836,0.9533895320960639
K=8,Aotizhongxin,8,57,11,9.013791165057356,8.613897051853256,0.3998941132040998,-0.07429526813894263,0.8892217632621623
Sin clima ni contaminantes,Aotizhongxin,3,25,6,8.652388089001176,7.639902676399026,1.0124854126021516,0.35732147927227503,1.8678712764713565
Tres capas,Aotizhongxin,3,25,6,8.825777270974031,7.639902676399026,1.1858745945750053,0.43673680393057435,2.1592750609569626


## Experimento 1. Estación sin sensor
La GCN registró 17.1446 µg/m³ en Huairou y 8.0553 en Tiantan. El mayor error correspondió a Huairou. El mapa permite interpretar la cobertura espacial: Huairou ocupa una posición periférica y las estaciones centrales presentan mayor proximidad. Sin embargo, la distancia por sí sola no determina el MAE: cada estación tiene una distribución y variabilidad propias. Se mantuvieron las mismas horas para evitar confundir localización con cambios de muestra; aun así, comparar estaciones no constituye una prueba causal del aislamiento.

## Experimento 2. Número de vecinas
Los valores K=1, 5 y 8 se compararon con K=3. La tabla muestra el MAE de cada GCN y de su promedio de vecinas correspondiente. K es el número de elecciones antes de simetrizar: el grado final puede ser mayor. Más conexiones incorporan mediciones adicionales, pero también mezclan estaciones lejanas y pueden suavizar variaciones locales. El patrón observado se interpreta con los valores medidos, sin suponer que un grafo más denso deba mejorar. Todas las diferencias entre variantes describen esta prueba; no se eligió un ganador para uso futuro con estas mismas horas.

## Experimento 3. Eliminación de los seis rasgos
Al anular los seis rasgos del nodo objetivo, la GCN obtuvo 8.6524 µg/m³ frente a 8.7890 en la configuración original. El cambio fue de -0.1367 µg/m³. La predicción sigue siendo calculable porque los nodos vecinos conservan sus variables y las multiplicaciones por la adyacencia transportan sus representaciones al objetivo. Un cero normalizado representa la media de entrenamiento, no una ausencia física de contaminación. Se modificó únicamente el enmascaramiento, sin ampliar N_CONTAMINANTES ni cambiar la entrada del MLP.

## Experimento 4. Tercera capa
Con tres capas, el MAE fue 8.8258 µg/m³, un cambio de +0.0367 respecto de dos capas. La tercera capa amplía el alcance a tres saltos y añade parámetros; también puede intensificar el suavizado espacial y dificultar la optimización. El resultado pertenece a una sola inicialización por variante. No permite atribuir causalmente el cambio al sobresuavizado ni afirmar superioridad estable sin nuevas semillas y períodos independientes.

## Revisión final de la rúbrica
1. Hace lo que se pidió (20 %): Cumplido: cuatro experimentos, ambas estaciones alternativas, tres valores K y cinco respuestas; se conservan condiciones y referencia original.

2. Código (5 %): Ejecución completada y salidas visibles; semilla fija. Requiere las dependencias indicadas. Se conservan dos secciones de código: archivo original y ejecución propia.

3. Resultados (15 %): MAE en prueba, tablas, curvas de validación, comparación gráfica y predicciones exportadas; salidas originales conservadas.

4. Comparación honesta (20 %): Referencia espacial y persistencia; intervalos por bloques. Limitación: una semilla, intervalo condicionado al modelo y dependencia temporal residual.

5. Análisis (30 %): Mecanismos de información, agregación, profundidad, topología y riesgos vinculados a las métricas. No se atribuye causalidad no demostrada.

6. Conclusiones (10 %): Conclusiones delimitadas y siguiente experimento con regla de evaluación concreta. No se asigna una nota docente ni se certifica un 5/5.
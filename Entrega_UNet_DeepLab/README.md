# U-Net frente a DeepLab: entrega

- **Demo_UNet_vs_DeepLab_ampliado.ipynb**: conserva las 16 celdas originales con sus salidas y añade el experimento ASPP (1, 3, 6), 30 épocas.
- **Informe_UNet_DeepLab.docx**: cuatro preguntas originales, análisis, figuras reales y conclusiones.
- **Verificacion_rubrica.docx**: verificación de los seis criterios del profesor y sus limitaciones.
- **resultados_experimento.json**: métricas de la ejecución adicional local en CPU.
- **verificacion_integridad.json**: comprobación del prefijo original y hash del archivo fuente.
- **Entrega_UNet_DeepLab.zip**: paquete de los cinco archivos anteriores.

El experimento adicional obtuvo IoU final 0,601611. La referencia original DeepLab conserva su IoU 0,615. La comparación no demuestra un efecto causal del cambio de tasas: las trayectorias aleatorias y las versiones de PyTorch difieren.

Para repetir únicamente el experimento adicional, ejecutar las celdas añadidas al final en un entorno con torch, numpy, matplotlib y pillow y acceso a la descarga Penn-Fudan. No usar «Ejecutar todo» si se desea evitar volver a entrenar las referencias originales. Las figuras nuevas proceden de ejecución local, no de capturas de Colab.

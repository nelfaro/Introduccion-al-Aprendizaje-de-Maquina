# Introduccion-al-Aprendizaje-de-Maquina
Detección No Supervisada de Anomalías en el Consumo de Medicamentos mediante Autoencoders Aplicada a Datos de una Obra Social.

El fraude y el uso indebido de credenciales en la dispensa de medicamentos representan un problema relevante para las obras sociales, con impacto económico y sanitario directo. 
Este trabajo presenta el diseño y la evaluación de un Autoencoder no supervisado, implementado en Keras/TensorFlow, orientado a detectar patrones de sobresaturación temporal en el consumo de medicamentos por afiliado.

A partir de un conjunto de datos real de dispensas de farmacia de una obra social (512.396 registros, distribuidos entre afiliados con cobertura del 50% y 60% según tipo de plan), se construyó un vector de 11 features agregadas por afiliado y ventana semanal (cantidad de farmacias distintas, médicos distintos, principios activos distintos, cantidad y monto acumulados, y patrones de recompra). 

El modelo se entrenó exclusivamente sobre semanas que no violan un conjunto de reglas de negocio predefinidas y recalibradas sobre la distribución real de los datos, y su error de reconstrucción se utilizó como score de anomalía. Sobre el conjunto de prueba (56.977 semanas-afiliado, 1.350 casos positivos), el modelo alcanzó un AUC de 0.968 y un recall de 0.919 frente a las reglas de negocio utilizadas como referencia. 

El proceso de validación permitió además identificar y descartar una regla de evaluación circular,  detectar una limitación de calidad de datos (variable Edad constante en el dataset disponible), documentadas como hallazgos metodológicos del trabajo.

#  🛡️ El Arte de Engañar: Una GAN contra el Modelo Defensor
Una red generativa antagónica (GAN) diseñada para producir tráfico de red malicioso capaz de evadir un modelo binario de detección de intrusiones, con el objetivo final de reforzarlo mediante un reentrenamiento adversarial.

Este proyecto fue desarrollado como el trabajo final para el programa de Inteligencia Artificial de Samsung Innovation Campus y EOI (Escuela de Organización Industrial). Explora el uso de redes generativas antagónicas (GANs) para generar datos sintéticos que desafían un sistema de detección de intrusiones basado en red (IDS), permitiendo su mejora posterior a través de un reentrenamiento guiado adversarialmente.

---

# 🎯 Proyecto Final – Generación de Tráfico Malicioso con GANs para Reforzar Modelos IDS

Este repositorio contiene el **proyecto final** del curso de **Inteligencia Artificial** impartido por **Samsung Innovation Campus y la Escuela de Organización Industrial (EOI)**. El trabajo explora el uso de **Redes Generativas Antagónicas (GANs)** para generar tráfico de red sintético con el objetivo de **evaluar y reforzar un sistema de detección de intrusiones (IDS)**.

---

## 🧠 Objetivo del Proyecto

El objetivo principal es emplear una **GAN para generar muestras maliciosas que parezcan benignas** ante un modelo clasificador binario previamente entrenado. Esto permite:

- Identificar debilidades en el modelo de detección original.
- Reforzarlo mediante **reentrenamiento con datos sintéticos adversarios**.
- Explorar el potencial de las GANs como herramienta defensiva en ciberseguridad.

---

## 🔬 Descripción Técnica

El proyecto se estructura en varias fases:

### 1. **Entrenamiento del clasificador inicial**
- Modelo binario: Benigno vs Malicioso.
- Entrenado con el dataset `NF-UQ-NIDS-V2_Sample-2.csv`.
- Alta precisión (~99%) antes de introducir muestras sintéticas.

### 2. **Implementación de la GAN**
- **Generador**: Red neuronal densa que recibe vectores aleatorios y genera tráfico de red simulado.
- **Discriminador**: Reemplazado por el clasificador original congelado.
- **Función de pérdida**: Basada en la capacidad del generador de engañar al clasificador.
- Bucle de entrenamiento personalizado con early stopping.

### 3. **Evaluación**
- Análisis del número de veces que el clasificador etiqueta erróneamente tráfico malicioso como benigno.
- Estudio del impacto en métricas como la precisión y el recall.

### 4. **Fase de Refuerzo**
- Se añaden los ejemplos generados al dataset original.
- Se reentrena el clasificador para mejorar su resistencia frente a patrones adversarios.

---

## 🧾 Contenido del Repositorio

- `data_preprocessing.py`: Carga y preprocesamiento del dataset.
- `classifier_model.py`: Entrenamiento del modelo binario inicial.
- `gan_generator.py`: Arquitectura y entrenamiento del generador.
- `training_loop.py`: Bucle de entrenamiento personalizado de la GAN.
- `evaluation.py`: Evaluación del generador y análisis de degradación del clasificador.
- `reinforcement.py`: Reentrenamiento del clasificador con datos sintéticos.
- `README.md`: Archivo principal (en inglés).
- `README.es.md`: Versión en español de la documentación.

---

## 🧪 Resultados

- El generador logra crear tráfico malicioso que el clasificador etiqueta como benigno.
- La precisión del modelo original disminuye con la entrada adversaria.
- El reentrenamiento con los ejemplos generados mejora la robustez del clasificador.

---

## 📚 Conclusiones

Este proyecto demuestra cómo la inteligencia artificial generativa puede utilizarse no solo para simular ataques realistas, sino también como **estrategia de defensa**, mediante el uso de ejemplos adversarios para entrenar sistemas de detección más robustos.

---

## 🤖 Tecnologías Utilizadas

- Python
- Pandas, NumPy
- TensorFlow / Keras
- Scikit-learn
- Matplotlib / Seaborn

---

## 📌 Notas Finales

Este proyecto ha sido desarrollado como trabajo final del **curso de Inteligencia Artificial de Samsung y EOI**, aplicando conceptos de aprendizaje profundo, modelos generativos y ciberseguridad.


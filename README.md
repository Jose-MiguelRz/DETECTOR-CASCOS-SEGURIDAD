# 🦺 Detector de Cascos de Seguridad  
**Proyecto Final — Inteligencia Artificial | UDLAP 2025**

---

## 📌 Descripción
Este proyecto implementa un sistema de **visión por computadora** capaz de detectar automáticamente si una persona **porta casco de seguridad o no**, utilizando técnicas modernas de *Deep Learning*.

El sistema está diseñado para aplicaciones en:
- 🏗️ Construcción
- 🏭 Plantas industriales
- ⚠️ Zonas de riesgo

Permite integrarse con cámaras de seguridad para generar **alertas en tiempo real**, mejorando la seguridad laboral y el cumplimiento de normativas.

---

## 🚨 Problemática
Supervisar manualmente el uso de equipo de protección personal (EPP) es:
- Costoso  
- Ineficiente  
- Poco escalable  

Este proyecto automatiza la supervisión mediante inteligencia artificial.

---

## 🧠 Solución
Se construyó un modelo basado en **Transfer Learning** usando:
- `MobileNetV2` (pre-entrenado en ImageNet)
- Clasificación binaria:
  - ✅ Con casco  
  - ❌ Sin casco (alerta)

---

## 🔄 Pipeline del Proyecto

1. 📥 Descarga del dataset desde Kaggle  
2. 🗂️ Organización de datos (PASCAL VOC → clasificación)  
3. 🖼️ Preprocesamiento y Data Augmentation  
4. 🧠 Entrenamiento con Transfer Learning  
5. 📊 Evaluación completa del modelo  
6. ⚖️ Comparación contra SVM (baseline)  
7. 🎯 Predicciones visuales  
8. 🌐 Interfaz interactiva con Gradio  

---

## 📦 Dataset

- **Nombre:** Hard Hat Detection  
- **Fuente:** Kaggle  
- **Formato original:** PASCAL VOC (XML + imágenes)  

**Procesamiento:**
- Conversión a clasificación binaria  
- Balanceo de clases  
- División:
  - 80% entrenamiento  
  - 10% validación  
  - 10% prueba  

---

## 🛠️ Tecnologías utilizadas

- Python 3  
- TensorFlow / Keras  
- Scikit-learn  
- OpenCV / PIL  
- Matplotlib / Seaborn  
- Gradio  

---

## 🧪 Modelo

- Arquitectura: **MobileNetV2**
- Tipo: Transfer Learning  
- Capas agregadas:
  - GlobalAveragePooling  
  - Dense (256)  
  - Dropout  
  - Salida sigmoide  

---

## 📊 Evaluación

El modelo se evalúa usando:

- Accuracy  
- Loss  
- Matriz de confusión  
- Classification report (precision, recall, F1-score)

---

## ⚖️ Comparación de modelos

| Modelo        | Tipo           | Desempeño |
|--------------|----------------|----------|
| SVM          | Tradicional    | Baseline |
| MobileNetV2  | Deep Learning  | Superior |

---

## 📈 Resultados

- Alto accuracy en detección de cascos  
- Mejora significativa respecto a SVM  
- Buen desempeño en imágenes reales  

> Los valores exactos se generan al ejecutar el notebook.

---

## 🖥️ Interfaz interactiva

Se incluye una aplicación con **Gradio** que permite:

- Subir una imagen 📷  
- Detectar automáticamente el estado de seguridad  
- Mostrar alerta en caso de riesgo 🚨  

---

## 📁 Archivos generados

- `detector_cascos_final.h5` → modelo entrenado  
- `muestra_dataset.png` → ejemplos del dataset  
- `curvas_entrenamiento.png` → métricas  
- `matriz_confusion.png` → evaluación  
- `comparacion_svm_cnn.png` → comparación  
- `predicciones.png` → resultados  

---

## ▶️ Cómo ejecutar

### 1. Clonar repositorio
```bash
git clone <tu_repo>
cd <tu_repo>

2. Abrir en Google Colab
Subir el notebook
Activar GPU (T4 recomendado)
3. Configurar Kaggle
Descargar kaggle.json desde Kaggle
Subirlo cuando el notebook lo solicite
4. Ejecutar todas las celdas

El pipeline se ejecuta automáticamente.

📜 Normativa

Este sistema se alinea con:

NOM-115-STPS-2009
(Seguridad e higiene en el trabajo en México)

🚀 Aplicaciones futuras
Detección en tiempo real con video
Integración con CCTV
Alertas automáticas (correo, SMS)
Detección de otros EPP

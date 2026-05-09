# 🌐 Traductor Neuronal Bidireccional (ES ↔ EN)

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

Una aplicación web de traducción automática neuronal bidireccional (Inglés a Español y Español a Inglés) construida desde cero. El núcleo del proyecto es una arquitectura Sequence-to-Sequence (Seq2Seq) con un mecanismo de Atención Global, entrenada con PyTorch y desplegada con una interfaz interactiva en Streamlit.

## ✨ Características Principales

* **Arquitectura Personalizada:** Implementación pura en PyTorch de un modelo Encoder-Decoder utilizando redes LSTM bidireccionales.
* **Mecanismo de Atención:** Incorpora atención global (Dot-Product/Linear) para alinear dinámicamente las palabras de origen y destino, mejorando drásticamente la traducción de oraciones largas.
* **Decodificación Avanzada (Beam Search):** Sustituye la selección codiciosa (Greedy Search) por un algoritmo de Beam Search con penalización por repetición, evaluando múltiples secuencias candidatas para generar traducciones con mayor sentido gramatical.
* **Traducción Bidireccional:** Soporte dinámico para intercambiar la dirección de la traducción cargando los pesos específicos correspondientes en tiempo de ejecución.
* **Interfaz de Usuario:** Despliegue local fluido mediante Streamlit para interacciones en tiempo real.

## 🧠 Detalles Técnicos del Modelo

* **Dimensión de Embeddings:** 512
* **Capas Ocultas (Hidden Size):** 512
* **Optimizador:** Adam (Learning Rate: 0.001)
* **Regularización:** Dropout (0.3)
* **Entrenamiento:** Entrenado mediante Teacher Forcing dinámico y Mixed Precision (AMP) para optimización de memoria en GPU.

### Conjunto de Datos y Pipeline
El modelo fue entrenado manejando grandes volúmenes de datos paralelos (como el dataset ALIA / OpenSubtitles). Para evitar desbordamientos de memoria (OOM) durante el entrenamiento en la nube, se implementó un pipeline de **Data Streaming** utilizando la librería `datasets` de Hugging Face, procesando el corpus masivo de forma iterativa directamente desde la red.

## ⚙️ Instalación y Uso Local

Sigue estos pasos para ejecutar la aplicación en tu máquina local:

### 1. Clonar el repositorio
```bash
git clone [https://github.com/](https://github.com/)[TU_USUARIO]/[NOMBRE_DEL_REPO].git
cd [NOMBRE_DEL_REPO]

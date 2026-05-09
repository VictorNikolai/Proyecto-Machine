# 🌐 Traductor Neuronal Bidireccional (ES ↔ EN)

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

Aplicación web de **traducción automática neuronal bidireccional (Español ↔ Inglés)** desarrollada con **Deep Learning**.

El sistema utiliza un modelo **Sequence-to-Sequence (Seq2Seq) con mecanismo de Atención Global**, implementado en **PyTorch**, entrenado en **Kaggle** y desplegado mediante una interfaz interactiva con **Streamlit**.

---

# ✨ Características

- Modelo **Encoder–Decoder con LSTM bidireccionales**
- **Mecanismo de Atención Global** para mejorar traducciones largas
- **Beam Search** para generar traducciones más naturales
- **Traducción bidireccional** (ES → EN / EN → ES)
- Interfaz web simple usando **Streamlit**
- Notebook de **entrenamiento completo en Kaggle**

---

# 🧠 Arquitectura del Modelo

El modelo está basado en la arquitectura **Seq2Seq con atención** utilizada en tareas modernas de **Procesamiento de Lenguaje Natural (NLP)**.

Componentes principales:

- **Encoder**
  - LSTM bidireccional
  - Embeddings entrenables
  - Codificación del contexto de la oración

- **Decoder**
  - LSTM
  - Atención global
  - Generación palabra por palabra

---

# ⚙️ Hiperparámetros del Modelo

| Parámetro | Valor |
|---|---|
| Embedding Size | 512 |
| Hidden Size | 512 |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Dropout | 0.3 |
| Beam Search | Activado |
| Mixed Precision | AMP |

---

# 📊 Dataset Utilizado

El modelo fue entrenado con **datasets paralelos de traducción**:

- **ALIA**
- **OpenSubtitles**

Para manejar grandes volúmenes de datos se utilizó:

- **Streaming de datos**
- Librería **HuggingFace Datasets**

Esto permitió entrenar el modelo sin cargar todo el dataset en memoria.

---

# 🏋️ Entrenamiento del Modelo

El proceso de entrenamiento se realizó en **Kaggle utilizando GPU**.

Archivo incluido:

```
codigo-machine-entrenamiento.ipynb
```

El notebook contiene:

- carga del dataset
- preprocesamiento del texto
- construcción del modelo Seq2Seq
- entrenamiento del encoder y decoder
- guardado de pesos del modelo

---

# 📁 Estructura del Proyecto

```
translator-seq2seq/

│
├── app.py
├── codigo-machine-entrenamiento.ipynb
├── vocabularios.json
├── Pasos.txt
│
├── encoder_es_en.pt
├── decoder_es_en.pt
│
├── encoder_en_es.pt
├── decoder_en_es.pt
│
└── README.md
```

Descripción:

| Archivo | Descripción |
|------|------|
| `app.py` | Aplicación web con Streamlit |
| `codigo-machine-entrenamiento.ipynb` | Notebook de entrenamiento del modelo |
| `vocabularios.json` | Vocabulario del modelo |
| `encoder_es_en.pt` | Encoder Español → Inglés |
| `decoder_es_en.pt` | Decoder Español → Inglés |
| `encoder_en_es.pt` | Encoder Inglés → Español |
| `decoder_en_es.pt` | Decoder Inglés → Español |

---

# 🚀 Instalación

### 1 Clonar repositorio

```bash
git clone https://github.com/tu-usuario/translator-seq2seq-attention.git

cd translator-seq2seq-attention
```

---

### 2 Crear entorno virtual

```bash
python -m venv env
```

Activar entorno:

Windows

```bash
env\Scripts\activate
```

Linux / Mac

```bash
source env/bin/activate
```

---

### 3 Instalar dependencias

```bash
pip install -r requirements.txt
```

---

### 4 Ejecutar la aplicación

```bash
streamlit run app.py
```

Abrir en navegador:

```
http://localhost:8501
```

---

# 🖥 Interfaz

La aplicación permite:

- escribir una oración
- seleccionar dirección de traducción
- obtener traducción generada por el modelo

---

# 🛠 Tecnologías Utilizadas

- Python
- PyTorch
- Streamlit
- HuggingFace Datasets
- Kaggle GPU

---

# 👨‍💻 Autor

**Víctor Nikolai Huarcaya Pumacayo**

Estudiante de **Ingeniería de Sistemas** interesado en:

- Inteligencia Artificial
- Deep Learning
- NLP
- Machine Learning aplicado

---

# 📄 Licencia

Proyecto bajo licencia **MIT**.

# 🎧 iask_me — Audio Processing with Generative AI

**iask_me** es un sistema de procesamiento de audio impulsado por **inteligencia artificial generativa (GenAI)**.  
Su objetivo es transformar audios en texto útil y comprensible, permitiendo generar preguntas, traducciones y resúmenes automáticos del contenido transcrito.

---

## 🚀 Descripción general

El proyecto está diseñado para **convertir audio en texto** mediante modelos de IA y ofrecer una **interfaz inteligente de consulta** sobre los datos obtenidos.  
Permite a los usuarios subir archivos de audio, transcribirlos automáticamente y generar respuestas o resúmenes con modelos de lenguaje.

---

## 🧠 Modelos de IA utilizados

| Tarea | Modelo | Descripción |
|-------|---------|-------------|
| **Transcripción de audio** | 🗣️ `Whisper-1` (OpenAI) | Modelo de reconocimiento automático de voz (ASR) utilizado para convertir audio en texto. |
| **Traducción y resumen** | 💬 `GPT-4` (OpenAI) | Modelo generativo de lenguaje usado para traducir y sintetizar la información transcrita. |

**👉 En resumen:**  
Todas las **peticiones de transcripción** en `iask_me` usan el modelo **Whisper-1**, mientras que las **peticiones de traducción o resumen** usan **GPT-4**.

---

## ⚙️ Endpoints principales (según `swagger.yaml`)

| Endpoint | Método | Descripción |
|-----------|---------|-------------|
| `/upload` | `POST` | Subida de archivo de audio. |
| `/transcribe/{job_id}` | `POST` | Transcripción con Whisper-1. |
| `/translate/{job_id}` | `POST` | Traducción generativa. |
| `/summarize/{job_id}` | `POST` | Resumen del contenido transcrito. |
| `/jobs/{job_id}` | `GET` | Estado del procesamiento. |

---

## 🧩 Arquitectura del sistema

- **Frontend:** Interfaz web para subir y consultar audios.
- **Backend:** API REST documentada en [`swagger.yaml`](./swagger.yaml).
- **Motor de IA:** Whisper-1 + GPT-4.
- **Almacenamiento:** Base de datos vectorial para búsquedas semánticas.
- **Infraestructura:** Docker + Python + FastAPI.

---

## 🧪 Ejemplo de flujo

1. El usuario sube un archivo de audio (`/upload`).
2. El sistema lo transcribe con **Whisper-1** (`/transcribe`).
3. El texto resultante se traduce o resume usando **GPT-4**.
4. Las respuestas se almacenan en una base vectorial para futuras consultas.

---

## 🧰 Tecnologías principales

- Python 3.10+
- FastAPI
- OpenAI Whisper
- OpenAI GPT-4
- Docker
- FAISS / ChromaDB

---

## 📄 Licencia
Este proyecto se distribuye bajo licencia MIT.

---

## 👩‍💻 Autora
**Isabel Najarro** — [GitHub: isabelnajarro](https://github.com/isabelnajarro)

---

### 🗣️ Nota para desarrolladores
Si utilizas este proyecto desde el **orchestrator**, recuerda que las peticiones usan:
- **`Whisper-1`** para transcripción de audio  
- **`GPT-4`** para generación de texto, traducción y resumen

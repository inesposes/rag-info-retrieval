# Creación de Sistemas RAG sobre Bases de Datos Vectoriales

## 📜 Descripción
Este proyecto forma parte de una entrega para la asignatura Big Data Aplicado del curso de especialización en IA y Big Data.

El objetivo es desarrollar un sistema **RAG** (*Retrieved Augmented Generation*), que consiste en la recuperación de información y generación de texto para producir respuestas más precisas al integrar datos externos relevantes. En este caso he creado un RAG que recibe información de un artículo web y otro que la recibe de tres documentos PDF.

Para los dos RAGs se realiza el siguiente proceso:
1. Procesa y divide la información en fragmentos más pequeños (splits).
2. Inicializa un modelo de embeddings de texto de Hugging Face 
3. Se conecta a la base de datos vectorial de MongoDBAtlas. 
4. Introduce la información con su correspondiente embedding en la base de datos. 
5. Integra el uso de un **LLM** (*Large Language Model*) de Ollama para responder preguntas basadas en el contexto de la información proporcionada.



---

## 📁 Estructura del proyecto

```plaintext
📂 practica-rag
├── 📁 pdfs
│   ├── arboles.pdf
│   ├── flores.pdf
│   ├── plantas.pdf
├── 🛠️env.example
├── 🔗 .gitignore
├── 📚 1. RAG from web - ENG.ipynb
├── 📚 2. RAG from pdfs - ESP.ipynb
├── 📄README.md
├── 📦requirements.txt
```
---

## ⚙️ Requisitos
- Python 3.13.3
- Una cuenta en MongoDBAtlas con una base de datos y una colección para guardar los vectores.
- Un entorno Docker con una imagen de [Ollama](https://hub.docker.com/r/ollama/ollama) corriendo y el modelo "llama3.2" instalado.
- Entorno que permita ejecutar Jupyter Notebooks
---

## 💻 Instalación
1. Clona este repositorio:
   ```bash
   git clone https://github.com/inesposes/practica-rag
   cd practica-rag
   ```
2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Crea un .env copiando el .env.example y cubre con los datos de tu clúster.

---

## 📝  RAGs

### RAG en inglés desde datos de una página web
- **Descripción:** este RAG utiliza la información de un [artículo](https://towardsdatascience.com/3-business-skills-you-need-to-progress-your-data-science-career-in-2025-146f841d1a1e) sobre cómo progresar en tu carrera en la Ciencia de Datos. Responde a las preguntas en inglés por lo que utiliza un modelo de embeddings que funciona en este idioma.
- **Ejecución:** según tu entorno, clicar en el botón que ejecute todas las celdas del Notebook.
- **Adicional:** implementación de una Interfaz Gráfica de Usuario (GUI) para facilitar el uso de este RAG. Se puede acceder a ella a tráves de http://127.0.0.1:7860 una vez ejecutado el Notebook.

### RAG en castellano desde archivos PDF
- **Descripción:** este RAG utiliza la información sobre tres pdfs que se encuentran en la carpeta "/pdfs" sobre plantas, árboles y flores. Responde a las preguntas en castellano, por lo que utiliza un modelo de embeddings plurilingüe.
- **Ejecución:** según tu entorno, clicar en el botón que ejecute todas las celdas del Notebook.


---


NuevaMente – Sistema Inteligente de Adaptación y Generación de Contenido Educativo

<div align="center">

**Hackathon ONE G10 (Oracle Next Education & Alura)**  
*Equipo 48*

</div>

---

## Descripción del Proyecto
**NuevaMente** es una solución inteligente diseñada para ingerir documentaciones técnicas densas, manuales de software o bases de conocimiento y transformarlas automáticamente en contenidos educativos personalizados y estructurados. 

La plataforma adapta el material didáctico según el perfil del destinatario (principiante, junior, líder técnico, etc.) y el formato pedagógico de salida elegido (flashcards, quizzes interactivos, guías paso a paso o resúmenes ejecutivos), garantizando fidelidad técnica mediante técnicas avanzadas de **RAG (Retrieval-Augmented Generation)** y orquestación de agentes.

---

## Arquitectura de la Solución
*(Aquí puedes insertar un diagrama visual del flujo de la arquitectura)*

El flujo general del sistema comprende:
1. **Ingestión:** Carga de documentos técnicos en formato PDF, Markdown o texto plano.
2. **Procesamiento y RAG:** Segmentación del texto (*chunking*), generación de embeddings y almacenamiento en un Vector Store (ChromaDB / FAISS).
3. **Orquestación Inteligente:** Uso de LLMs (Google Gemini / OpenAI) combinados con flujos multi-agente (LangGraph) para redactar, estructurar y revisar el contenido sin alucinaciones.
4. **Persistencia en la Nube:** Almacenamiento obligatorio de los documentos originales y los artefactos JSON generados en **OCI Object Storage (Capa Always Free)**.
5. **Interfaz de Usuario:** Aplicación interactiva desarrollada en Streamlit / Gradio.

---

## Tecnologías y Stack Utilizado
* **Lenguaje Principal:** Python
* **Orquestación de IA y RAG:** LangChain, LangGraph
* **Modelos de Lenguaje (LLMs):** Google Gemini / OpenAI GPT
* **Vector Store:** ChromaDB / FAISS
* **Backend y Validación:** FastAPI / Flask, Pydantic (tipado estricto de salidas JSON)
* **Interfaz Gráfica:** Streamlit / Gradio
* **Cloud & Almacenamiento:** Oracle Cloud Infrastructure (OCI) - Object Storage (Always Free)

---

## Estructura del Repositorio
```text
G10_Nuevamente_Equipo48/
├── agents/              # Lógica de agentes autónomos y grafos de decisión (LangGraph)
├── rag_core/            # Pipeline de ingesta, chunking, embeddings y Vector Store
├── backend/             # API del servidor y validadores de esquemas (Pydantic)
├── frontend/            # Interfaz de usuario interactiva (Streamlit/Gradio)
├── oci_integration/     # Scripts de conexión con OCI Object Storage
├── data/                # Corpus de documentos técnicos de prueba (raw y processed)
├── requirements.txt     # Dependencias del proyecto
└── .env.example         # Variables de entorno necesarias
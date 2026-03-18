# 🤖 Generative AI with Large Language Models — Course Labs

> **DeepLearning.AI × AWS** | Coursera | Ibai Mutiloa Aliaga

Repositorio personal con los laboratorios y notas del curso **"Generative AI with Large Language Models"** de DeepLearning.AI en colaboración con AWS. El curso cubre desde los fundamentos de los LLMs hasta técnicas avanzadas de fine-tuning, RLHF y despliegue en producción.

---

## 📚 Contenido del curso

### Semana 1 — Fundamentos de LLMs y Prompt Engineering
- Arquitectura Transformer (encoder, decoder, self-attention)
- Casos de uso de LLMs: summarization, traducción, NER, code generation
- Prompt Engineering: zero-shot, one-shot y few-shot inference
- Parámetros de configuración generativa: temperature, top-k, top-p
- Ciclo de vida de un proyecto de IA generativa

### Semana 2 — Fine-Tuning
- Preentrenamiento de LLMs y leyes de escalado
- Fine-tuning supervisado para tareas específicas
- PEFT (Parameter Efficient Fine-Tuning)

### Semana 3 — Alineación y Despliegue
- Reinforcement Learning with Human Feedback (RLHF)
- Optimización de modelos para producción
- Integración con APIs externas y RAG

---

## 🧪 Laboratorios

### Week 1

#### Lab 1 — Generative AI Use Case: Dialogue Summarization
[`Week_1_Lab/Lab_1_summarize_dialogue.ipynb`](Week_1_Lab/Lab_1_summarize_dialogue.ipynb)

Exploración de la tarea de **resumen de diálogos** usando el modelo **FLAN-T5** en AWS SageMaker. El laboratorio cubre:

- **Zero-shot inference** — el modelo resume sin ningún ejemplo previo
- **One-shot inference** — se proporciona un ejemplo completo en el prompt
- **Few-shot inference** — múltiples ejemplos para mejorar el output
- Comparación del impacto de cada técnica en la calidad del resumen
- Primeros pasos en **Prompt Engineering** con templates estructurados

**Modelo usado:** `google/flan-t5-base`  
**Dataset:** [DialogSum](https://huggingface.co/datasets/knkarthick/dialogsum) (Hugging Face)  
**Entorno:** AWS SageMaker via Vocareum (Coursera)

---

## 🛠️ Stack técnico del curso

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_SageMaker-FF9900?style=flat&logo=amazonaws&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat&logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)

---

## 👤 Autor

**Ibai Mutiloa Aliaga** — Software Developer · AI Systems · Backend  
[github.com/ibai-mutiloa](https://github.com/ibai-mutiloa) · [LinkedIn](https://linkedin.com/in/ibai-mutiloa-aliaga)

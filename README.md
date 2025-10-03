# Senior R&D Engineer, Computer Vision & AI

## About Me

A Senior R&D Engineer with over 10 years of experience in image analysis, I specialize in bridging classical, battle-tested techniques with state-of-the-art Deep Learning architectures. I have been dedicated to solving complex real-world problems in demanding sectors like healthcare and industrial inspection.

This repository documents my recent deep dive into the engineering of modern AI systems.

---

## My Journey Through Modern Computer Vision: A Portfolio

This portfolio is structured as a four-act journey. Each section explores a core area of modern computer vision, moving from foundational pipelines to state-of-the-art applications.

---

### Act I: The Foundation - Mastering End-to-End Vision Pipelines

This section covers the essential steps for creating and rigorously evaluating robust vision systems.

*   **Large-Scale Defect Detection Pipeline**
    *   **Synopsis:** A complete pipeline to classify concrete cracks on a dataset of 40,000 images. This project methodically compares a CNN trained from scratch against a Transfer Learning approach, demonstrating the process of model selection and large-scale data handling.
    *   **Core Concepts:** Large-Scale Data Engineering, Transfer Learning, Rigorous Model Evaluation.

*   **Model Interpretability with Class Activation Mapping**
    *   **Synopsis:** An implementation of Grad-CAM, a key technique to visualize the regions an image classification model focuses on to make its predictions. This is crucial for debugging models and building trust in their outputs.
    *   **Core Concepts:** Model Interpretability, Explainable AI (XAI), Debugging, Validation.
---

### Act II: The Innovation - Prototyping with State-of-the-Art Models

This act explores how cutting-edge research can be translated into functional prototypes, enabling new and flexible AI capabilities.

*   **Open-Vocabulary Object Detection with Grounding DINO**
    *   **Synopsis:** A proof-of-concept system that detects objects in images based on natural language descriptions (e.g., "a dog on a skateboard"). This zero-shot capability eliminates the need for task-specific training data.
    *   **Core Concepts:** Open-Vocabulary Detection, Rapid Prototyping from Research Papers, State-of-the-Art Model Implementation.

*   **Multimodal AI for Similarity Search & Zero-Shot Classification**
    *   **Synopsis:** This project leverages deep feature **embeddings** for semantic similarity search and clustering, a core technique for Re-Identification. It also uses the multimodal model **CLIP** for zero-shot classification based on text prompts.
    *   **Core Concepts:** Feature Extraction, Semantic Search, Multimodal (Text-Image) AI, Zero-Shot Learning.
---

### Act III: The Optimization - Engineering for Production & Scale

This section focuses on the engineering challenges of deploying large models, addressing real-world constraints of cost, memory, and agility.

*   **Efficient Fine-Tuning of Large Models with QLoRA**
    *   **Synopsis:** An implementation of a Parameter-Efficient Fine-Tuning (PEFT) strategy using **QLoRA**. This method achieves high performance while training less than 1% of a large model's parameters, drastically reducing computational costs.
    *   **Core Concepts:** Production-Oriented Optimization, PEFT. This universal technique is directly transferable from LLMs to large vision models.

*   **Deploying an AI Model via a Flask REST API**
    *   **Synopsis:** A practical example of packaging a trained model into a web service using **Flask**, creating a REST API endpoint that returns a prediction from an input.
    *   **Core Concepts:** Software Engineering for ML, Model Deployment, Bridging R&D with Production.

---

### Act IV: From Perception to Action - Building Autonomous Systems

This final act explores the next frontier: building systems that not only perceive the world but can also reason and act upon that perception.

*   **Building a Knowledge-Based Reasoning System with RAG**
    *   **Synopsis:** Development of a system using the **Retrieval-Augmented Generation (RAG)** paradigm. This combines a retriever with a Large Language Model to answer questions based on a private knowledge base, demonstrating how to build AI that can **reason** with specific information.
    *   **Core Concepts:** Complex AI System Design, Knowledge Retrieval, Reasoning.

*   **Combining Vision and Language for Automated Reporting**
    *   **Synopsis:** A project that first **classifies** visual defects on an aircraft and then uses a language model to **generate a descriptive text report** of the findings.
    *   **Core Concepts:** Multimodal Pipelines, Perception-to-Language Generation, Automated Task Execution. This is a foundational step towards an agent that can perceive, understand, and report on its environment.

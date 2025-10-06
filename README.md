# Senior R&D Engineer, Computer Vision & AI

## About Me

A Senior R&D Engineer with over 10 years of experience in image analysis, I specialize in bridging classical, battle-tested techniques with state-of-the-art Deep Learning architectures. I have been dedicated to solving complex real-world problems in demanding sectors like healthcare and industrial inspection.

This repository showcases approaches I take when engineering modern AI systems.

---


Each section explores a core area of modern computer vision, moving from foundational pipelines to state-of-the-art applications.

## Act I: Foundations - End-to-End Vision Pipelines

This section covers some of the essential steps for creating and evaluating vision systems.

*   **Large-Scale Defect Detection Pipeline**
    *   A complete pipeline to classify concrete cracks on a dataset of 40,000 images. This project methodically compares a CNN trained from scratch against a Transfer Learning approach, demonstrating the process of model selection and large-scale data handling.
    *   **Core Concepts:** Large-Scale Data Engineering, Transfer Learning, Rigorous Model Evaluation.
   [tlearning_resnet18_PyTorch](https://github.com/madelezhia/vision-systems-lab/blob/main/I-Foundations/tlearning_resnet18_PyTorch.ipynb)

*   **Model Interpretability with Class Activation Mapping**
    *   An implementation of Grad-CAM, a key technique to visualize the regions an image classification model focuses on to make its predictions. This is crucial for debugging models and building trust in their outputs.
    *   **Core Concepts:** Model Interpretability, Explainable AI (XAI), Debugging, Validation.
---

## Act II: Innovations - Prototyping with State-of-the-Art Models

This act explores how cutting-edge research can be translated into functional prototypes, enabling new and flexible AI capabilities.

*   **Open-Vocabulary Object Detection with Grounding DINO**
    *   A proof-of-concept system that detects objects in images based on natural language descriptions (e.g., "a dog on a skateboard"). This zero-shot capability eliminates the need for task-specific training data.
    *   **Core Concepts:** Open-Vocabulary Detection, Rapid Prototyping from Research Papers, State-of-the-Art Model Implementation.

*   **Multimodal AI for Similarity Search & Zero-Shot Classification**
    *   This project leverages deep feature embeddings for semantic similarity search and clustering, a core technique for Re-Identification. It also uses the multimodal model **CLIP** for zero-shot classification based on text prompts.
    *   **Core Concepts:** Feature Extraction, Semantic Search, Multimodal (Text-Image) AI, Zero-Shot Learning.
---

## Act III: Optimization - Engineering for Production & Scale

This section focuses on the engineering challenges of deploying large models, addressing real-world constraints of cost, memory, and agility.

*   **Efficient Fine-Tuning of Large Models with QLoRA**
    *   An implementation of a Parameter-Efficient Fine-Tuning (PEFT) strategy using QLoRA. This method achieves high performance while training less than 1% of a large model's parameters, drastically reducing computational costs.
    *   **Core Concepts:** Production-Oriented Optimization, PEFT. This universal technique is directly transferable from LLMs to large vision models.

*   **Deploying an AI Model via a Flask REST API**
    *   A practical example of packaging a trained model into a web service using Flask, creating a REST API endpoint that returns a prediction from an input.
    *   **Core Concepts:** Software Engineering for ML, Model Deployment, Bridging R&D with Production.
   [image-classifier-app](https://github.com/madelezhia/image-classifier-app)

---

## Act IV: Action - Building Autonomous Systems

This final act explores the next frontier: building systems that not only perceive the world but can also reason and act upon that perception.

*   **Building a Knowledge-Based Reasoning System with RAG**
    *   Development of a system using the Retrieval-Augmented Generation (RAG) paradigm. This combines a retriever with a Large Language Model to answer questions based on a private knowledge base, demonstrating how to build AI that can reason with specific information.
    *   **Core Concepts:** Complex AI System Design, Knowledge Retrieval, Reasoning.
   [qa-bot](https://github.com/madelezhia/qa-bot)

*   **Combining Vision and Language for Automated Reporting**
    *   A project that first classifies visual defects on an aircraft and then uses a language model to generate a descriptive text report of the findings.
    *   **Core Concepts:** Multimodal Pipelines, Perception-to-Language Generation, Automated Task Execution. This is a foundational step towards an agent that can perceive, understand, and report on its environment.

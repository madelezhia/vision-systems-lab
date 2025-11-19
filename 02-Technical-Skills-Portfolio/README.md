# Modern Computer Vision & AI Techniques Portfolio

---

## 📚 Context: Strategic Upskilling Initiative (2024-2025)

Following a strategic sabbatical dedicated to AI advancement, I developed this portfolio of projects demonstrating hands-on proficiency in modern computer vision, deep learning, and AI techniques. Each implementation reflects current best practices and state-of-the-art approaches used in production environments.

Goal: Bridge my 10+ years of production experience with the latest advancements in AI/ML, particularly in Vision-Language Models, Transformers, and efficient training techniques.

---

## 🎯 Objectives & Outcomes

### Vision-Language Models (VLMs)
- Master modern multimodal architectures (CLIP, GroundingDINO)  
- Understand cross-attention mechanisms  
- Implement zero-shot classification and detection  

### Production Optimization
- Implement parameter-efficient fine-tuning (LoRA, QLoRA)  
- Understand quantization techniques (4-bit, 8-bit)  
- Balance performance vs. computational constraints  

### End-to-End Systems
- Build complete pipelines from data to deployment  
- Integrate multiple models (vision + language)  
- Design for production constraints (speed, memory, cost)  

---

## 🏗️ Act I: Foundations - Classical Computer Vision Pipelines

Solid understanding of fundamental CV tasks and evaluation methodologies

### Project 1: Large-Scale Defect Detection Pipeline

**Challenge:** Compare training strategies on real-world dataset (40,000 images)

**Implementation:**
- CNN trained from scratch vs. Transfer Learning (ResNet18)
- Data loading and augmentation pipelines
- Training loop with validation
- Performance comparison and analysis

**Key Technical Points:**
- Transfer learning benefits on limited data
- Data engineering for large-scale datasets
- Model evaluation best practices

**Technologies:** PyTorch, torchvision, Google Colab

📓 [**View Notebook**](./I-Foundations/tlearning_resnet18_PyTorch.ipynb)

---

### Project 2: Model Interpretability with CAM

**Challenge:** Understand and visualize CNN decision-making process. Critical for medical imaging applications where model trust is essential (cf. PET-MR project in Career Highlights)

**Implementation:**
- CAM (Class Activation Mapping)
- Activation map generation and overlay

**Key Technical Points:**
- Model interpretability techniques
- Hook-based feature extraction in PyTorch
- XAI (Explainable AI) importance in production

**Technologies:** PyTorch, Computer Vision, Visualization

📓 [**View Notebook**](./I-Foundations/CAM.ipynb)

---

## 🚀 Act II: State-of-the-Art - Modern Vision-Language Models

Cutting-edge multimodal AI and zero-shot capabilities

### Project 1: Open-Vocabulary Object Detection with GroundingDINO

**Challenge:** Detect objects using natural language descriptions, no training required -> Rapid prototyping of detection systems without annotation costs

**Implementation:**
- GroundingDINO model integration (HuggingFace)
- Text-based object detection
- Confidence thresholding and NMS
- Visualization of detections with bounding boxes

**Key Technical Points:**
- Zero-shot detection (no task-specific training)
- Natural language as query interface
- Cross-modal attention mechanisms

**Technologies:** Transformers, HuggingFace, Vision-Language Models

📓 [**View Notebook**](./II-SoTA/OpenVocab_OD_GroundingDINO.ipynb)

---

### Project 2: Zero-Shot Classification with CLIP

**Challenge:** Classify images using text prompts, explore semantic similarity. Extends classical classification approaches (cf. Corn phenotyping) to open-vocabulary scenarios

**Implementation:**
- CLIP model for zero-shot classification
- Feature embedding extraction
- Semantic similarity search
- Temperature scaling for calibration

**Key Technical Points:**
- Contrastive learning principles
- Multimodal embedding spaces
- Zero-shot transfer capabilities

**Technologies:** CLIP (OpenAI), HuggingFace, PyTorch

📓 [**View Notebook**](./II-SoTA/CLIP_Classification.ipynb)

---

### Project 3: Vision Transformers for Classification

**Challenge:** Implement and understand modern attention-based architectures

**Implementation:**
- Vision Transformer (ViT) architecture
- Patch embedding and positional encoding
- Self-attention mechanisms
- Fine-tuning strategies

**Key Technical Points:**
- Transformer architectures for vision
- Attention visualization
- Scaling laws and model sizes

**Technologies:** PyTorch, Vision Transformers

📓 [**View Notebook**](./II-SoTA/PyTorch_classification_ViT_hybrid.ipynb)

---

## ⚡ Act III: Optimization - Production-Ready Techniques

Efficient training and deployment strategies for resource-constrained environments. Critical for deploying large models in cost-constrained environments

### Project 1: Efficient Fine-Tuning with QLoRA

**Challenge:** Fine-tune large models with minimal compute and memory

**Implementation:**
- QLoRA (Quantized Low-Rank Adaptation)
- 4-bit quantization with bitsandbytes
- LoRA adapter training (<1% parameters)
- PEFT (Parameter-Efficient Fine-Tuning) techniques

**Key Results:**
- 84% accuracy on sentiment analysis (IMDB)
- Train only 1.2% of parameters
- Significant memory reduction (8GB → 3GB)
- 10-minute training on consumer GPU

**Technologies:** HuggingFace PEFT, bitsandbytes, LoRA, Quantization

📓 [**View Notebook**](./III-Optimization/QLoRA_with_Hugging_Face.ipynb)

---

### Project 2: Flask REST API Deployment

**Challenge:** Package trained model as production web service. Bridges R&D and production deployment (required skill for senior roles)

**Implementation:**
- Flask API with prediction endpoint
- Model serialization and loading
- Input validation and preprocessing
- JSON response formatting

**Key Technical Points:**
- ML model deployment patterns
- API design for ML services
- Production considerations (error handling, logging)

**Technologies:** Flask, Python, REST APIs

🔗 [**View Repository**](https://github.com/madelezhia/image-classifier-app)

---

## 🤖 Act IV: Action - Autonomous AI Systems

Building systems that perceive, reason, and act

### Project 1: Knowledge-Based Reasoning with RAG

**Challenge:** Build AI system that answers questions using private knowledge base. Foundation for enterprise knowledge management systems.

**Implementation:**
- RAG (Retrieval-Augmented Generation) architecture
- Document chunking and embedding
- Vector database for semantic search
- LLM integration for answer generation

**Key Technical Points:**
- Combines retrieval + generation
- Grounded responses (not hallucinated)
- Scalable to large document collections

**Technologies:** LangChain, Vector DBs, LLMs, RAG

🔗 [**View Repository**](https://github.com/madelezhia/qa-bot)

---

### Project 2: Vision-Language Pipeline for Automated Reporting

**Challenge:** Classify visual defects and generate descriptive text reports. Extends quality control projects (cf. Luxury mold detection) with automated reporting.

**Implementation:**
- Aircraft defect classification (VGG16 + Transfer Learning)
- BLIP model for image captioning
- Multi-stage pipeline integration
- Automated report generation

**Key Technical Points:**
- Multi-model pipeline orchestration
- Vision → Language translation
- Production workflow design

**Technologies:** TensorFlow/Keras, BLIP, Multimodal AI

📓 [**View Notebook**](./IV-Action/Classification_and_Captioning.ipynb)

---

## 🛠️ Technical Stack Summary

### Frameworks & Libraries
- **Deep Learning:** PyTorch, TensorFlow/Keras, HuggingFace Transformers
- **Computer Vision:** OpenCV, torchvision, timm
- **Specialized:** PEFT, bitsandbytes, LangChain
- **Deployment:** Flask, Streamlit, Docker

### Models & Architectures
- **Vision:** ResNet, VGG, EfficientNet, Vision Transformers
- **Vision-Language:** CLIP, BLIP, GroundingDINO
- **Language:** BERT, GPT, T5 (via transformers)
- **Techniques:** LoRA, QLoRA, Quantization, Transfer Learning

### Development Tools
- **Environments:** Google Colab, Jupyter, VS Code
- **Version Control:** Git, GitHub
- **Compute:** GPU (CUDA), Cloud (Colab)

---

## 🎓 Professional Certifications Completed

### Generative AI & Modern Architectures

**[IBM Generative AI Engineering Professional Certificate](https://www.coursera.org/professional-certificates/generative-ai-engineering)** (2025)  
**Key Skills Acquired:**
- Transformer architectures and attention mechanisms
- LangChain for building AI applications
- HuggingFace ecosystem (models, datasets, pipelines)
- Prompt engineering and in-context learning
- RAG (Retrieval-Augmented Generation) systems

**Relevance:** Essential for modern multimodal AI systems combining vision and language

---

### Computer Vision with PyTorch

**[OpenHPI Practical Computer Vision with PyTorch](https://open.hpi.de/courses/pytorch2024)** (2025)  
**Key Skills Acquired:**
- Modern CV architectures (Vision Transformers)
- PyTorch implementation best practices
- Data augmentation strategies
- Transfer learning techniques

**Relevance:** Updated from TensorFlow/Keras background to PyTorch ecosystem

---

### Deep Learning Foundations

**[IBM Deep Learning Professional Certificate](https://www.coursera.org/professional-certificates/deep-learning-keras-pytorch-tensorflow)** (2025)  
**Key Skills Acquired:**
- CNNs for computer vision
- Transfer learning strategies
- Model optimization and quantization
- Cross-framework implementation (PyTorch, Keras, TensorFlow)

**Relevance:** Comprehensive coverage of deep learning fundamentals with modern tools

---

**[Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning)** - DeepLearning.AI (2020)  
**Key Skills Acquired:**
- Neural network architectures and training
- Hyperparameter tuning and optimization
- Convolutional and sequence models
- Practical ML strategies

**Relevance:** Foundational knowledge that underpins all subsequent work

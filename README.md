
# AI-Powered Student Assistant

An AI-powered student assistant developed as a diploma thesis project. The system combines **fine-tuning a Transformer-based language model** with **Retrieval-Augmented Generation (RAG)** to support responses grounded in a separate retrieval dataset.

The project covers the full workflow from preparing training data and adapting a language model to retrieving relevant information at inference time and evaluating generated responses.

## Key Features

- **LoRA fine-tuning:** Adapted a Transformer model using Low-Rank Adaptation (LoRA) through the PEFT library.
- **Custom data preparation interface:** Built an interface to create data.
- **Separate dataset for RAG:** Prepared a distinct dataset for retrieval during inference, separate from the model's fine-tuning data.
- **Semantic retrieval:** Used **BERT CLS pooling** to obtain text representations and **FAISS** for similarity-based retrieval.
- **Response evaluation:** Used **ROUGE** to compare generated responses with reference answers and assess their lexical overlap during evaluation. And BERTscore which measures contextual semantic similarity.

## System Workflow

### 1. Data Preparation

A custom interface supports creating and modifying the training data. The data is then transformed into model-compatible input for fine-tuning.

### 2. Model Fine-Tuning

A Transformer-based model is fine-tuned using **LoRA (Low-Rank Adaptation)** via **PEFT**, allowing parameter-efficient adaptation.

### 3. Retrieval-Augmented Generation

A **separate dataset for RAG** is used during inference:

1. Text is represented using **BERT CLS pooling**.
2. **FAISS** is used to search for similar representations and retrieve relevant information.
3. The retrieved information supports the model's response-generation process.

### 4. Evaluation

Generated answers are compared with reference answers using the **ROUGE** metric (implemented with `rouge_score`). ROUGE measures lexical overlap, providing a reproducible way to assess how closely the generated text matches expected responses. It is useful for comparing outputs during development, although it does not by itself measure factual correctness or semantic quality. For that purpose BERTscore was used to evaluate contextual semantic similarity.

## Technologies and Libraries

| Technology | Role |
| --- | --- |
| Python | Main programming language |
| PyTorch (`torch`) | Deep learning framework |
| Hugging Face `transformers` | Transformer model tooling |
| Hugging Face `peft` | LoRA-based fine-tuning |
| Hugging Face `datasets` | Dataset handling |
| FAISS | Similarity search for retrieval |
| `rouge_score` | ROUGE-based response evaluation |
| `BERTscore` | BERTscore-based response evaluation |
| Tkinter | GUI tooling |
| Gradio | Interface tooling used in the project |

## Project Highlights

This project brings together several practical software and machine learning tasks:

- Preparing and transforming custom datasets for model training.
- Fine-tuning a language model with parameter-efficient techniques.
- Implementing a retrieval workflow using vector representations and similarity search.
- Evaluating generated text against reference answers.
- Developing tools to support data creation and maintenance.


## About

Developed as a diploma thesis project in **Electrical and Electronic Engineering** at the **University of West Attica**.

**Author:** Christos Tsagkas

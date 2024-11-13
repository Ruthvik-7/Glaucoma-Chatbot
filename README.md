# Glaucoma Chatbot

This Glaucoma Chatbot project provides answers to glaucoma-related questions by using two different embedding models: **BioBERT** and **BioWordVec**. The chatbot returns two responses—one from each model—along with confidence scores for each answer. This project demonstrates how to leverage pretrained embeddings to match questions and answers in a conversational chatbot.

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Setup](#setup)
- [Usage](#usage)
- [Acknowledgments](#acknowledgments)

---

## Features
- **BioBERT Model** for biomedical question-answering tasks.
- **BioWordVec Model** for fast and efficient word embeddings in the biomedical domain.
- **Cosine Similarity** to find the most relevant answer for user questions.
- **Confidence Scores** for BioBERT and BioWordVec responses to evaluate answer relevance.

## Project Structure
```plaintext
.
├── Combined_Dataset.xlsx    # Dataset containing questions and answers related to glaucoma
├── bio_embedding_intrinsic   # BioWordVec model file (should be in binary format)
├── precomputed_embeddings.pkl # (Optional) File for storing precomputed embeddings
└── chatbot.py               # Main script to run the chatbot
